# SQL Server to Snowflake Reconciliation: Implementation Plan

This document is a handoff. It tells an agent with access to both databases how
to build the real comparison behind the mock-up in `comparison.html`, which is
kept in the same folder as this plan and should travel with it. The mock-up
uses static sample values; this plan replaces them with real results.

It is deliberately tool-agnostic: it specifies what to compare, how to decide a
match, and what to output. Use whatever the environment already has to run
queries against both databases.

## 1. Context

- The DAL (core layer) liquidity tables are being migrated from SQL Server to
  Snowflake.
- So far only the **tier 1 tables** have moved: the tables that load from the
  silver layer into the DAL. Their load now also runs in Snowflake.
- All later processing stays in SQL Server for now. A separate tool will copy
  the Snowflake tier 1 data back to SQL Server to feed it. Later, the SQL
  Server code may be replicated in Snowflake.
- The question to answer: **does each tier 1 table built in Snowflake equal the
  same table built in SQL Server, and if not, where, why and by how much?**

## 2. What is compared

Three copies of each table can exist. Compare them in this order:

| Comparison | Left | Right | Proves |
|---|---|---|---|
| **A. Load equivalence** (this plan's core) | Tier 1 table built in SQL Server | Same table built in Snowflake | The Snowflake load logic reproduces the SQL Server load |
| **B. Transfer fidelity** | Tier 1 table in Snowflake | Its copy landed in SQL Server by the transfer tool | The transfer tool does not alter data |
| **C. Downstream impact** | Tier 2+ outputs run on the SQL Server tier 1 | Same outputs run on the landed Snowflake copy | The differences in A and B do not move the final liquidity numbers |

A and B use the same method (sections 4 to 6). C is Phase 4.

### Tables in scope

These are the names used in the mock-up. **They are placeholders**: confirm the
real table names, keys, money columns and groupings with the user before
writing any query (section 8).

| Table | Used in liquidity for | Key | Key money column | Business grouping |
|---|---|---|---|---|
| `DAL.DEPOSIT` | Cash outflows, stable funding | `DEPOSIT_ID` | `BALANCE_AUD` | Product type |
| `DAL.LOAN` | Cash inflows, required stable funding | `LOAN_ID` | `BALANCE_AUD` | Loan type |
| `DAL.SECURITY` | HQLA, required stable funding | `SECURITY_ID` | `MARKET_VALUE_AUD` | HQLA class |
| `DAL.LOAN_FACILITY` | Undrawn commitment outflows | `FACILITY_ID` | `UNDRAWN_AUD` | Customer and facility type |
| `DAL.COLLATERAL` | Encumbrance (removes HQLA) | `COLLATERAL_ID` | `PLEDGED_VALUE_AUD` | Collateral purpose |
| `DAL.REPO` | Secured funding outflows and inflows | `TRADE_ID` | `CASH_AMOUNT_AUD` | Direction |
| `DAL.DERIVATIVE` | Derivative and collateral outflows | `DEAL_ID` | `MTM_AUD` | Product |
| `DAL.WHOLESALE_DEBT` | Debt outflows, stable funding | `ISSUE_ID` | `OUTSTANDING_AUD` | Instrument type |
| `DAL.TRADE_FINANCE` | Contingent outflows | `EXPOSURE_ID` | `EXPOSURE_AUD` | Product |
| `DAL.COUNTERPARTY` | Classification of every other table | `COUNTERPARTY_ID` | none | none |

Add any other tier 1 table that feeds liquidity. A table with no money column
is compared by row and column only.

## 3. Ground rules

1. **Read-only on both databases.** Write results only to a dedicated
   reconciliation schema or to files. Never modify a DAL table.
2. **No credentials in the project.** Use the environment's existing
   connection mechanism.
3. **Same as-at point on both sides.** A comparison is only valid if both
   tables were built from the same silver-layer snapshot. Record the as-at date
   and the load completion time of each side in every result. If the two loads
   used different cut-offs, say so in the output rather than reporting breaks.
4. **Compare every row, not a sample.** Sampling hides the rare rows that
   carry the money. Use hashing (section 5) to make full comparison cheap.
5. **Never hide a difference by normalising it away silently.** Each
   normalisation in section 5 is applied in a second pass and reported as its
   own cause, so the user can see how many rows it affected.
6. **Do not guess keys or meanings.** If a table has no reliable unique key,
   stop and ask.

## 4. The five levels of output

The mock-up shows five levels. Produce exactly these, per table, per run.

### Level 1: Table summary

One row per table.

| Field | Definition |
|---|---|
| `table_name`, `as_at`, `run_ts` | Identification |
| `rows_left`, `rows_right`, `rows_diff` | `COUNT(*)` each side; right minus left |
| `measure_column` | The key money column, or null |
| `sum_left`, `sum_right`, `sum_diff` | Sum of the money column each side; right minus left |
| `rows_that_differ` | Count of keys in any break category (Level 5) |
| `result` | `Match`, `Within tolerance` or `Break` (section 6) |

### Level 2: Bridge by cause

One row per table and cause. The impacts must sum exactly to `sum_diff`, and
the row effects must explain `rows_diff`.

| Field | Definition |
|---|---|
| `cause` | From the cause list in section 5.4 |
| `kind` | `only_left`, `only_right`, `value_differs` or `duplicate` |
| `rows` | Keys affected |
| `impact` | Effect on the money total, right minus left |
| `action` | Suggested fix, one sentence |

### Level 3: Business grouping

One row per table and group: `sum_left`, `sum_right`, `diff`, `diff_pct`,
`result`. Group by the dimension the downstream liquidity logic uses (product,
counterparty type, HQLA class). Group totals must add to the Level 1 sums.
Group on the **left** side's value of the dimension when the two sides disagree,
and report that disagreement as a column break.

### Level 4: Column profile

One row per table and column.

| Field | Definition |
|---|---|
| `type_left`, `type_right` | Declared data type each side |
| `nulls_left`, `nulls_right` | Count of NULLs |
| `distinct_left`, `distinct_right` | Count of distinct values |
| `rows_that_differ` | Among keys present on both sides, rows where this column differs |
| `result` | `Break` if any of nulls, distinct or rows differ; else `Match` |

For numeric columns also record `min`, `max` and `sum` each side; for dates,
`min` and `max`. The profile catches type, precision and collation problems
that row counts and totals miss.

### Level 5: Row breaks

One row per differing key and column: `key`, `kind`, `column`, `value_left`,
`value_right`, `cause`. Store all of them; the page shows a sample with a count
of the total. For `only_left` and `only_right`, store one row with the money
value. For `duplicate`, store the key with the row count each side.

## 5. Method

### 5.1 Key check first

For each side, confirm the key is unique and not null. Duplicates on either
side are reported as the `duplicate` kind and those keys are excluded from the
value comparison (a join on a duplicated key multiplies rows and corrupts every
later number).

### 5.2 Match rows

Full outer join on the key:

- Key only on the left: `only_left`.
- Key only on the right: `only_right`.
- Key on both: compare values.

Because the two tables live in different databases, do not try to join across
them directly. On each side compute, per key, a hash of every non-key column
rendered to a canonical text form (5.3), plus the money column. Bring only
`(key, row_hash, money)` to one place and compare there. For keys whose hashes
differ, fetch the full rows from both sides and compare column by column.

Use the same hash function and the same canonical text on both sides (for
example SHA-256 over the columns joined with a separator that cannot occur in
the data, with a fixed marker for NULL). Verify the two implementations agree
on a handful of hand-built rows before trusting any result.

### 5.3 Two passes: strict, then normalised

**Pass 1, strict.** Canonical text with no forgiveness: exact decimals as
stored, exact text including trailing spaces and case, timestamps as stored.
Rows equal in this pass are true matches.

**Pass 2, normalised.** For rows that differ in pass 1, apply these rules one
at a time. A row whose difference disappears under a rule is assigned that
rule's cause.

| Rule | Normalisation | Why it arises in this migration |
|---|---|---|
| Rounding | Round both to the smaller of the two declared scales | Different decimal scale or float-to-decimal conversion |
| Trailing spaces | Right-trim text | SQL Server `char(n)` pads; Snowflake `VARCHAR` does not |
| Empty vs NULL | Treat empty string and NULL as equal | Loads and tools differ on empty strings |
| Text case | Compare upper-cased | SQL Server collations are usually case-insensitive; Snowflake compares case-sensitively. This also causes **missing rows** when a filter or join on text silently drops them |
| Time zone | Compare as dates, or shift by the session offset | `datetime` loaded into a timestamp with a UTC conversion |
| Boolean form | Map `1/0`, `true/false`, `Y/N` to one form | `bit` to `BOOLEAN` |
| Unicode | Normalise to one form | `nvarchar` to `VARCHAR`, different encodings |

Rows still different after every rule are **genuine value differences**.
Investigate these individually; typical reasons are a late-arriving update
(different cut-off), a different reference rate (for example an FX rate date),
or a logic difference in the load.

### 5.4 Cause list

Use these cause names so the page and the plan agree. Assign exactly one cause
per differing key and column, in this priority order:

1. Row loaded twice (duplicate key)
2. Row only in SQL Server
3. Row only in Snowflake
4. Rounding
5. Trailing spaces in text
6. Empty text vs NULL
7. Text case
8. Date shifted by time zone
9. Boolean or Unicode form
10. Different reference rate used (derived columns such as an AUD amount)
11. Value differs (unexplained)

For rows on one side only, add the reason in brackets once known, for example
"Row only in SQL Server (status text case)".

## 6. Deciding the result

| Result | Rule |
|---|---|
| **Match** | Row counts equal, no key in any break category |
| **Within tolerance** | Row counts equal, every break is cause 4 (rounding), every row difference is under the row tolerance, and the total difference is under the table tolerance |
| **Break** | Anything else, including differences with no money impact (text, dates) |

Mock-up tolerances are 0.01 per row and 1.00 per table. Agree the real ones
with the user (section 8). A text or date difference is always a Break even at
zero money impact, because downstream joins and filters can behave differently.

## 7. Phases

### Phase 1: Agree scope and definitions

1. Confirm with the user the list of tier 1 tables, and for each: real name on
   both sides, unique key, money column, business grouping column.
2. Confirm tolerances, the as-at date, and how to tell that both loads used the
   same silver snapshot.
3. Record all of it in `RECON_CONFIG` (a small table or file): one row per
   table. Everything later reads from this config; no table name is hard-coded.

**Done when:** the user has approved the config.

### Phase 2: Build the comparison for one table

Start with the deposit table.

1. Implement the key check, the hash extract on each side, the match, and both
   passes.
2. Write results into five result sets matching Levels 1 to 5.
3. Check internal consistency (these are the acceptance tests):
   - Bridge impacts sum to `sum_diff` to the cent.
   - Rows only on the right, plus duplicates, minus rows only on the left,
     equals `rows_diff`.
   - Group totals sum to the Level 1 sums on each side.
   - Each column's `rows_that_differ` equals the count of Level 5 rows for it.
4. Prove the comparison detects problems: on a scratch copy, deliberately
   change one value, delete one row, duplicate one row and pad one text value,
   and confirm each appears under the right cause.

**Done when:** all four consistency checks pass and the planted differences are
all found.

### Phase 3: Roll out to every table and feed the page

1. Run for every table in the config.
2. Export the results to the page. `comparison.html` reads a `TABLES` array;
   replace the static array with generated data of the same shape:

   ```
   { name, used, keyName, measure,          // measure null if no money column
     rowsSql, rowsSf, st,                   // st: "match" | "tol" | "brk"
     groups:  [{ g, sql, sf }],
     bridge:  [{ cause, kind, rows, impact, act }],   // kind: "sql" | "sf" | "diff" | "dup"
     columns: [{ c, tSql, tSf, nSql, nSf, dSql, dSf, diff }],  // diff null for the key column
     rows:    [{ key, kind, col, sql, sf, cause }] }  // a sample, at most a few hundred
   ```

   Keep the page's rendering code unchanged. The header line should show the
   real as-at date and run time instead of "sample values".
3. Store every run with its `run_ts`, so results can be compared day to day
   and a break that appears or disappears is visible.

**Done when:** the page shows real results for every table and the user can
select each table and see all five levels.

### Phase 4: Transfer fidelity and downstream impact

1. **Comparison B:** run the same method between the Snowflake table and its
   copy landed in SQL Server. Expect the type-conversion causes (rounding,
   trailing spaces, empty vs NULL, time zone) to matter most here.
2. **Comparison C:** run the downstream SQL Server processing twice, once on
   the original tier 1 tables and once on the landed copy, into separate output
   schemas. Compare the output tables with the same method, and report the
   difference in the final liquidity figures (HQLA, cash outflows, cash
   inflows, LCR, NSFR). This is the "impact" view: it shows which tier 1 breaks
   actually move a reported number.
3. Add a selector to the page for comparison A, B or C.

**Done when:** the user can see, for the same as-at date, whether tier 1
differences flow through to the final liquidity numbers.

### Phase 5: Make it routine

1. Schedule the comparison to run after both loads complete.
2. Define sign-off: for example, every table Match or Within tolerance for a
   set number of consecutive business days, with each remaining Break explained
   and accepted in writing.
3. Keep the run history until the SQL Server load is decommissioned.

## 8. Questions for the user before starting

| Question | Why it matters |
|---|---|
| Real table names, keys, money columns and groupings | The mock-up names are placeholders |
| Which other tier 1 tables feed liquidity | Scope |
| Are both loads built from the same silver snapshot, and how is that proven | Otherwise timing differences look like breaks |
| Row and table tolerances | Decides Match vs Within tolerance |
| Which side is the reference | The plan assumes SQL Server is the reference until cut-over |
| Where may results be written | A reconciliation schema on one side, or files |
| Is the SQL Server database collation case-insensitive | Predicts the text-case and missing-row breaks |
| How are AUD amounts derived, and from which rate date | Explains reference-rate differences |
| Who signs off, and on what criteria | Phase 5 |

## 9. Final acceptance checklist

- [ ] Every in-scope table is in the config with a confirmed unique key.
- [ ] Every comparison is a full-row comparison, not a sample.
- [ ] As-at date and load completion times are recorded on every run.
- [ ] The four consistency checks in Phase 2 pass for every table.
- [ ] Planted differences are detected and correctly classified.
- [ ] Every Break has a cause, and every "Value differs (unexplained)" row has been investigated.
- [ ] The page shows real data for all five levels for every table.
- [ ] Nothing was written to any DAL table, and no credentials are in the project.
