# APS 210 Live Liquidity Ticker: Implementation Plan

This document is a complete handoff. It tells an agent with access to the bank's
Snowflake data how to recreate the working prototype, connect it to real data,
prove the numbers, and then extend it. The full source of the prototype is in
the appendix, so nothing else is needed to start.

**Files kept alongside this plan:** `rules.csv` (the APS 210 factor table) and
`index.html` (the dashboard page) are kept in the same folder as this document
and should travel with it. Use those copies rather than retyping them. The
other six files (`liquidity.py`, `feeds.py`, `server.py`, `positions.sql`,
`ladder.sql`, `concentration.sql`) exist only in the appendix and must be
created from it.

## 1. What you are building

A live dashboard for a bank Treasury team showing liquidity under APRA
Prudential Standard APS 210 (July 2025 version, Federal Register of Legislation
ID F2025L00653, published on legislation.gov.au). The bank is an **LCR ADI**,
so the measures are:

- **LCR**: HQLA divided by 30-day net cash outflows. Minimum 100%.
- **NSFR**: available stable funding divided by required stable funding. Minimum 100%.

The dashboard shows headline tiles (LCR, NSFR, HQLA, net cash outflows, HQLA
surplus), an LCR chart for the session, feed freshness, a contractual maturity
ladder, funding concentration (top 10), and breakdown tables for HQLA, outflows,
inflows, available stable funding and required stable funding.

## 2. Ground rules for the implementing agent

1. **APS 210 is the source of truth.** Obtain the standard (F2025L00653) before
   changing any factor. Every row in `rules.csv` cites its paragraph in the `ref`
   column (A = Attachment A, LCR; C = Attachment C, NSFR). Never change a factor
   without citing the paragraph that justifies it. In this document, "Att A
   para N" and "Att C para N" mean the attachments; "main body para N" means the
   numbered paragraphs of the standard before the attachments.
2. **Do not guess table or column meanings.** Inspect the Snowflake schema, and
   where a classification is ambiguous (for example which deposits are
   "operational"), ask the user or the regulatory reporting team. Record every
   mapping decision in comments in the SQL.
3. **No credentials in the project.** Use a named connection in
   `~/.snowflake/connections.toml` with a read-only role. Never write passwords,
   keys or tokens into any file or command.
4. **Fail loudly.** An unmapped category, or a category arriving on the wrong
   feed, raises an error. A silently missing balance makes the ratio wrong.
5. **Keep it small.** Python standard library only, plus
   `snowflake-connector-python`. No web framework, no front-end build, no
   database of its own until Phase 5 calls for one. (Phase 6 may put a reverse
   proxy in front for sign-on.)
6. **The server binds to 127.0.0.1 and has no login.** Do not expose it on a
   network until Phase 6.
7. All amounts are **AUD millions**. Convert foreign currency to AUD in the SQL.
8. **All files are UTF-8 without a byte-order mark.** `index.html` contains
   non-ASCII characters. On Windows PowerShell 5.1, `Set-Content` writes ANSI
   by default; pass `-Encoding utf8` or write the files another way.

## 3. Architecture

```
Snowflake --(3 queries, polled)--> feeds.py --> liquidity.py --> server.py --(SSE)--> index.html
                                                   ^
                                               rules.csv
```

| File | Purpose |
|---|---|
| `rules.csv` | One row per APS 210 category: label, feed, LCR side and factor, NSFR side and factor, paragraph reference. The only place factors live. |
| `liquidity.py` | Pure function `calculate(positions)` returning LCR, NSFR and line detail. Applies the HQLA2 caps (40% and 15%) and the 75% inflow cap. `python liquidity.py` runs its self-check. |
| `feeds.py` | Two sources with the same output shape: `sim()` (random-walk sample data) and `snowflake()` (runs the three SQL files). |
| `positions.sql` | Returns `(FEED, CATEGORY, AMOUNT, AS_OF)`, one row per feed and category. All classification and aggregation happens here, in Snowflake. |
| `ladder.sql` | Returns exactly 7 rows of `(BUCKET, INFLOWS, OUTFLOWS)` for the contractual maturity ladder. |
| `concentration.sql` | Returns `(NAME, AMOUNT)` for the largest funding providers. |
| `server.py` | Polls the source while a browser is connected, calculates, and pushes each snapshot over server-sent events. Serves `index.html`. |
| `index.html` | Single page, no dependencies. Renders tiles, chart and tables from each snapshot. |

Environment variables:

| Variable | Meaning | Default |
|---|---|---|
| `LIQ_SOURCE` | `snowflake` for real data; anything else is simulated | simulated |
| `SNOWFLAKE_CONNECTION` | Named connection in `connections.toml` | required for Snowflake |
| `LIQ_POLL_SECONDS` | Seconds between polls | 2 simulated, 300 Snowflake |
| `LIQ_AS_AT` | `YYYY-MM-DD`; sets the `$as_at` session variable the queries filter on | today |
| `PORT` | Port to listen on | 8210 |

Design decisions to keep:

- **Aggregate in Snowflake.** The Python side only ever sees a few dozen rows.
- **Rules are data.** A change in the standard is a row edit, not a code change.
- **Polling, not streaming.** Snowflake is not a push source. The server polls
  only while at least one browser is connected. Set the interval to the rate the
  underlying feeds actually load; each poll runs three queries and wakes the warehouse.
- **Stock rows and flow rows.** Most categories are balances (stocks). A few are
  30-day cash flows that overlap a stock: `loan_due30_*` are the repayments due
  within 30 days on loans whose balances also appear in `loan_mortgage`,
  `loan_lt1y` and so on. This double appearance is deliberate: the flow row
  feeds the LCR and the stock row feeds the NSFR. Flow categories are the ones
  with `nsfr_side = none`.
- **Feed names come from `rules.csv`.** The SQL must emit, for each category,
  the feed that `rules.csv` gives it. The server rejects a mismatch. Every feed
  named in `rules.csv` appears in the freshness row; one with no rows or no load
  time shows as stale "no data".

## 4. Phase 1: Recreate the prototype

1. Create an empty project folder. Python 3.9 or later (tested on 3.13).
2. Copy the kept `rules.csv` and `index.html` into the project folder. Create
   the other six files exactly as given in the appendix, saved as UTF-8 without
   a byte-order mark. Verify all eight against the SHA-256 list at the end of
   the appendix (computed over the file with LF line endings).
   - If a kept file is missing, create it from the appendix instead.
   - If a kept file's checksum differs from the list, stop and ask the user
     which version is intended before continuing; `rules.csv` holds the
     regulatory factors, so do not pick one silently.
3. Run `python liquidity.py`. Expected output: `ok`.
4. Run `python server.py` and open `http://127.0.0.1:8210`. If the port is
   taken, set `PORT` to another one.

**Done when:** the page shows LCR around 120 to 125% and NSFR around 125 to 130%
on simulated data, values tick every 2 seconds, all ten feeds show as fresh, and
the browser console has no errors.

## 5. Phase 2: Connect Snowflake

### 5.1 Setup

1. `pip install "snowflake-connector-python>=3.1"` (named connections in
   `connections.toml` need a recent connector; confirm the installed version
   supports `connect(connection_name=...)`).
2. Ask the user to create a named connection in `~/.snowflake/connections.toml`
   using a **read-only role** and a small warehouse with auto-suspend. Do not
   handle the credentials yourself. The connection must use a non-interactive
   method (key pair or a programmatic access token): the server connects from a
   background thread, so browser-based single sign-on will not work.
3. Smoke test before anything else:
   `python -c "import os, snowflake.connector as s; c=s.connect(connection_name=os.environ['SNOWFLAKE_CONNECTION']); print(c.cursor().execute('SELECT CURRENT_ROLE(), CURRENT_WAREHOUSE()').fetchone())"`.
   Confirm with the user that the role shown has no write privileges.
4. Set `LIQ_SOURCE=snowflake`, `SNOWFLAKE_CONNECTION=<name>` and
   `LIQ_POLL_SECONDS` (agree the value with the user; see section 7).

### 5.2 Discover the data

1. List the tables behind each feed (deposits, loans, securities, loan
   facilities, collateral, and whatever exists for wholesale debt, capital,
   repos, derivatives, trade finance and guarantees) using `INFORMATION_SCHEMA`.
2. For each table record: grain (account, deal, position), balance column and
   currency, maturity date, counterparty type, product type, load timestamp and
   its time zone, and whether the table holds history or only the current day.
3. Record the source of foreign exchange rates used to convert to AUD.
4. Write the findings into a short `DATA_MAPPING.md` and confirm with the user
   before writing SQL.

### 5.3 Write `positions.sql`

The file in the appendix is an **illustrative template**; its table names,
column names and CASE logic are placeholders. Replace it. It must return one
row per `(FEED, CATEGORY)`:

- `FEED`: the feed `rules.csv` gives that category.
- `CATEGORY`: a value from `rules.csv`.
- `AMOUNT`: AUD millions, converted from foreign currency at the as-at rate,
  never NULL (use `COALESCE`).
- `AS_OF`: latest load time of that feed as a UTC `TIMESTAMP_TZ`. A timestamp
  without a time zone is assumed to be UTC by `feeds.py`, so convert in SQL.
- Filter on `$as_at` wherever a table holds history.

Classification rules to implement, each from the standard:

| Area | Rule | Reference |
|---|---|---|
| Retail deposits, stable | Fully covered by the Financial Claims Scheme AND (established relationship OR transactional account) | Att A para 37 |
| Retail deposits, less stable | Score each balance: over the FCS limit (AUD 250,000) = 2, online account = 2, no established relationship = 1, heavily rate-driven = 1. Score 0 to 2 gives 10% (`dep_retail_less_stable`); 3 or more gives 25% (`dep_retail_high_runoff`) | Att A para 40 |
| SME as retail | Non-financial SME managed as retail with total funding under AUD 2 million | Att A para 46 |
| Term deposits | Excluded from outflows only if residual maturity or notice is over 30 days AND there is no legal right to withdraw or a significant penalty. One year or more goes to `dep_term_gt1y` | Att A paras 41 to 43; Att C para 11 |
| Operational deposits | Only clearing, custody or cash management balances under a binding agreement; excess balances do not qualify | Att A paras 47 to 50 |
| Intermediated deposits | Treated as financial institution deposits unless all four look-through conditions hold | Att A para 35 |
| Liquidity vs credit facility | Liquidity facility only for the amount backstopping customer debt maturing within 30 days; working capital facilities are credit facilities; facilities to hedge funds, money market funds and SPVs are liquidity facilities to financial institutions in full | Att A paras 51 to 52 |
| HQLA eligibility | Unencumbered, under Treasury control, and meeting the operational requirements | Att A paras 22 to 25 |
| Encumbered securities | No LCR credit. Emit on the `collateral` feed: one year or more `sec_encumbered` (100%); HQLA six months to one year `hqla_enc_6m_1y` (50%); HQLA under six months `hqla1_enc_lt6m`, `hqla2a_enc_lt6m`, `hqla2b_enc_lt6m` (same NSFR factor as unencumbered). Non-HQLA encumbered under one year stays in its normal securities category | Att A para 22; Att C para 23 |
| Loans | Emit the balance as a stock row and the repayments due within 30 days as a separate flow row (`loan_due30_*`) | Att A paras 60 to 62; Att C paras 34 to 37 |
| Inflows | Only contractual inflows from fully performing exposures within 30 days; no inflow for open-maturity loans beyond minimum payments | Att A paras 54, 60 |
| Derivatives | Net payable and receivable by counterparty only under a valid master netting agreement | Att A Table 3 footnote 5 |
| Trade finance, guarantees | AMOUNT is the average of actual monthly net outflows over a recent 12 months | Att A Table 3 |
| NSFR maturities | Assets use the latest possible maturity; no defined maturity means one year or more | Att C paras 20 to 21 |

Where the source data lacks an attribute needed for a rule (for example no
"online account" flag), take the conservative category, note it in
`DATA_MAPPING.md`, and tell the user.

### 5.4 Write `ladder.sql` and `concentration.sql`

- **Ladder:** exactly 7 rows in this order: Overnight, 2-7 days, 8-30 days,
  31-90 days, 91-180 days, 181-365 days, Over 1 year. An empty bucket returns 0,
  not a missing row. Contractual maturity. A liability with no maturity
  (at-call deposit) falls due Overnight; an asset with no maturity goes to Over
  1 year. Outflows must include deposits, wholesale debt and repos; inflows
  loans, securities and reverse repos.
- **Concentration:** group by ultimate parent or connected group, not by
  account. Top 10 by amount. The page divides by total deposits and wholesale
  funding (every liability category except capital, other liabilities and net
  derivative liabilities), so this query must cover the same population.

### 5.5 Agree thresholds before sign-off

Before judging Phase 2, agree with the user the stale threshold for each feed
(`STALE_MS_BY_FEED` in `index.html`). The default of one hour would show a
daily batch feed as permanently stale.

**Done when:**

- The page runs against Snowflake with no error banner.
- Every feed shows a load time consistent with its real schedule.
- **Control totals reconcile for the stock feeds.** For deposits, securities
  plus collateral, loans and balance sheet: the sum of AMOUNT over stock
  categories (those with `nsfr_side` not `none`) equals the source table total
  in AUD millions for the same as-at date. Flow categories and the
  off-balance-sheet feeds (facilities, derivatives, contingent) are excluded
  from this test; check those against whatever source report the bank already
  trusts and record how in `DATA_MAPPING.md`.

## 6. Phase 3: Prove the numbers

1. Pick the date of the most recent LCR and NSFR returns lodged with APRA.
2. Run with `LIQ_AS_AT=<that date>`. If the tables do not hold history, ask the
   user how to reach that date's data (a snapshot schema or Snowflake Time
   Travel) and adapt the queries; do not reconcile today's data to an old return.
3. Ask the user for the lodged figures as `lodged.csv` with columns
   `form_line, amount` (AUD millions), one row per line of the lodged LCR and
   NSFR return forms.
4. With regulatory reporting, create `form_lines.csv` mapping each `rules.csv`
   category to a `form_line`. Several categories may map to one line. This file
   defines "line by line"; do not invent the mapping.
5. Write `reconcile.py`: run the source once, sum weighted and unweighted
   amounts by `form_line`, and print a table of dashboard, lodged and difference
   per line plus the headline ratios. It must be repeatable after any rule or
   query change.
6. Explain every difference; fix mapping errors; document legitimate differences.

**Done when:** LCR and NSFR match the lodged returns to within a tolerance the
user agrees (suggest 0.5 percentage points), and regulatory reporting has
reviewed the mapping.

## 7. Open items to resolve with the user

| Item | Current state | Needed |
|---|---|---|
| Affiliated dealer and other non-contractual contingent obligations | In `rules.csv` at 0% | The bank's own rates (APS 210 leaves them to the ADI) |
| Repos backed by HQLA2B RMBS | 25% run-off | Confirm against Att A Table 3; the PDF table extracted poorly |
| HQLA cap adjustment | Caps use unadjusted amounts | Att A paras 7 to 8 require unwinding repos, reverse repos and collateral swaps maturing within 30 days first. Needs cash and collateral value per transaction. Only matters when an HQLA2 cap binds |
| Committed Liquidity Facility | Not modelled | Confirm whether the bank has one |
| Early-warning triggers | Placeholders: LCR 110%, NSFR 105%, in `index.html` | Board-approved limits |
| Concentration threshold | 1% of deposits and wholesale funding | The bank's policy threshold |
| Stale-feed thresholds | 1 hour default, per-feed override map in `index.html` | Each feed's real load schedule (resolve in Phase 2, section 5.5) |
| Poll interval | 300 seconds for Snowflake | Agree against feed load frequency and warehouse cost |

## 8. Later phases, in priority order

Each is a separate piece of work. Do not start one until Phase 3 is done.

**Phase 4: Currency and entity split.** Main body para 55 requires both an AUD
LCR and an all-currencies LCR of at least 100%; main body para 43 requires
monitoring by significant currency; the standard applies at Level 1 and Level 2.
This changes the row contract, so these edits are required together:
- `positions.sql` returns `(FEED, CATEGORY, AMOUNT, AS_OF, CURRENCY, ENTITY_LEVEL)`.
- `feeds.snowflake()` and `feeds.sim()` return the two extra fields.
- `server.snapshot()` groups rows by slice and calls `calculate` once per slice
  (`calculate` itself still takes `(category, amount)` pairs and does not change).
- The page gets a slice selector.
- The AUD LCR uses only AUD-denominated HQLA and AUD cash flows; confirm the
  treatment of foreign-currency HQLA with regulatory reporting.

**Phase 5: History and movement.** Store each snapshot (SQLite is enough) so the
chart survives reloads and shows days, not minutes. Add a "what moved" view:
change in each weighted line since the previous close, sorted by impact on LCR.

**Phase 6: Limits, alerts and sharing.** Load limits and early warning
indicators from a config file (main body paras 37 and 39), alert when crossed,
and put the server behind the bank's single sign-on before anyone else uses it.
A reverse proxy that handles sign-on is acceptable; do not hand-roll
authentication.

**Phase 7: Stress scenarios.** Main body paras 62 to 66 require the bank's own
stress tests. Allow alternative factor sets (extra `rules_<scenario>.csv` files)
and a scenario switch showing LCR under each. A "survival days" figure (days
until cumulative stressed net outflows exceed HQLA) needs a daily cash-flow
projection the current model does not have; it requires a new query returning
contractual flows by day, so scope it as part of this phase.

**Phase 8: Intraday liquidity.** Main body para 41. Needs a payments or ESA
feed, which Snowflake polling will not provide. Scope separately.

## 9. Final acceptance checklist

- [ ] `python liquidity.py` prints `ok`.
- [ ] Every category returned by `positions.sql` exists in `rules.csv` and arrives on its `rules.csv` feed (the server raises otherwise).
- [ ] `AS_OF` values are UTC and the freshness row shows real load times.
- [ ] Control totals for the stock feeds match the source tables (section 5.5).
- [ ] LCR and NSFR reconcile to the last lodged returns within tolerance.
- [ ] No credentials in the project folder: a search for `password`, `token`, `secret`, `private_key` and `authenticator` across the folder finds nothing but this plan.
- [ ] Poll interval agreed with the user and warehouse auto-suspend confirmed.
- [ ] All items in section 7 resolved or explicitly accepted by the user.

## Appendix: prototype source

Create each file with exactly this content. Each block is fenced with four
backticks; the fence lines are not part of the file.

### `rules.csv`

````csv
category,label,feed,lcr_side,lcr_factor,nsfr_side,nsfr_factor,ref
cash_esa,"Notes, coin and central bank balances",securities,hqla1,1.00,rsf,0.00,A9(a)-(b); C29
claims_cb_lt6m,Other claims on central banks under 6 months,securities,none,0,rsf,0.00,C29(c)
hqla1_gov,HQLA1 securities (0% risk-weight sovereign and PSE),securities,hqla1,1.00,rsf,0.05,A9(c); C30
hqla2a,HQLA2A securities,securities,hqla2a,0.85,rsf,0.15,A10; C33(a)
hqla2b_rmbs,HQLA2B eligible RMBS,securities,hqla2b,0.75,rsf,0.50,A12(a); C34(a)
hqla2b,HQLA2B corporate debt and equities,securities,hqla2b,0.50,rsf,0.50,A12(b)-(c); C34(a)
hqla1_enc_lt6m,HQLA1 encumbered for under 6 months,collateral,none,0,rsf,0.05,A22; C23; C30
hqla2a_enc_lt6m,HQLA2A encumbered for under 6 months,collateral,none,0,rsf,0.15,A22; C23; C33(a)
hqla2b_enc_lt6m,HQLA2B encumbered for under 6 months,collateral,none,0,rsf,0.50,A22; C23; C34(a)
hqla_enc_6m_1y,HQLA encumbered for 6 months to 1 year,collateral,none,0,rsf,0.50,C34(b)
sec_encumbered,Assets encumbered for 1 year or more,collateral,none,0,rsf,1.00,C23; C37(a)
sec_other,Non-HQLA securities over 1 year,securities,none,0,rsf,0.85,C36(c)
sec_other_lt1y,Non-HQLA securities under 1 year (not maturing in 30 days),securities,none,0,rsf,0.50,C34(f)
sec_maturing_30d,Non-HQLA securities maturing within 30 days,securities,inflow,1.00,rsf,0.50,A62; C34(f)
equities_asx200,ASX200 non-financial equities (not HQLA),securities,none,0,rsf,0.50,C34(e)
equities_commodities,Other exchange-traded equities and traded commodities,securities,none,0,rsf,0.85,C36(c)-(d)
dep_retail_stable,Retail and SME deposits - stable,deposits,outflow,0.05,asf,0.95,A37; A Table 3; C12
dep_retail_less_stable,Retail deposits - less stable (score 0-2),deposits,outflow,0.10,asf,0.90,A40 Table 2; C13
dep_retail_high_runoff,Retail deposits - higher run-off (score 3+),deposits,outflow,0.25,asf,0.90,A40 Table 2; C13
dep_sme,Qualifying SME deposits under $2m - less stable,deposits,outflow,0.10,asf,0.90,A46; A Table 3; C13
dep_term_gt30d_stable,Retail term deposits over 30 days and under 1 year - stable,deposits,outflow,0.00,asf,0.95,A41; C12
dep_term_gt30d,Retail term deposits over 30 days and under 1 year - less stable,deposits,outflow,0.00,asf,0.90,A41; C13
dep_term_gt1y,Term deposits with 1 year or more to maturity,deposits,outflow,0.00,asf,1.00,A41; C11(c)
dep_operational_insured,Operational deposits - fully insured,deposits,outflow,0.05,asf,0.50,A Table 3; C14(b)
dep_operational,Operational deposits - not fully insured,deposits,outflow,0.25,asf,0.50,A Table 3; C14(b)
dep_corp_insured,"Non-financial corporate, sovereign and PSE deposits - fully insured",deposits,outflow,0.20,asf,0.50,A Table 3; C14(a)
dep_corp,"Non-financial corporate, sovereign and PSE deposits",deposits,outflow,0.40,asf,0.50,A Table 3; C14(a)
dep_corp_gt30d,"Non-financial corporate, sovereign and PSE funding over 30 days and under 1 year",deposits,outflow,0.00,asf,0.50,A45; C14(a)
dep_fi,Financial institution deposits callable within 30 days,deposits,outflow,1.00,asf,0.00,A Table 3; C15(a)
dep_fi_30d_6m,Financial institution funding over 30 days and under 6 months,deposits,outflow,0.00,asf,0.00,A45; C15(a)
dep_fi_6m_1y,Financial institution funding 6 months to 1 year,deposits,outflow,0.00,asf,0.50,A45; C14(f)
debt_lt30d,Unsecured debt maturing within 30 days,balance_sheet,outflow,1.00,asf,0.00,A Table 3; C15(a)
debt_30d_6m,Wholesale debt over 30 days and under 6 months,balance_sheet,none,0,asf,0.00,C15(a)
debt_6m_1y,Wholesale debt 6 months to 1 year,balance_sheet,none,0,asf,0.50,C14(f)
debt_gt1y,"Borrowings, secured and unsecured, with 1 year or more to maturity",balance_sheet,none,0,asf,1.00,C11(c)
capital,Regulatory capital,balance_sheet,none,0,asf,1.00,C11(a)
other_liabilities,Other liabilities without a stated maturity,balance_sheet,none,0,asf,0.00,C15(b)
abs_maturing,"Own ABCP, ABS and covered bonds maturing within 30 days",balance_sheet,outflow,1.00,asf,0.00,A Table 3; C15(a)
spv_funding_loss,"Loss of funding on SPVs, conduits and SIVs",balance_sheet,outflow,1.00,none,0,A Table 3
other_outflows,Other contractual cash outflows,balance_sheet,outflow,1.00,none,0,A Table 3
repo_hqla1,Repos maturing in 30 days - backed by HQLA1,secured_funding,outflow,0.00,asf,0.00,A Table 3; C15(a)
repo_clf,Repos maturing in 30 days - backed by CLF-eligible securities,secured_funding,outflow,0.00,asf,0.00,A Table 3; C15(a)
repo_hqla2a,Repos maturing in 30 days - backed by HQLA2A,secured_funding,outflow,0.15,asf,0.00,A Table 3; C15(a)
repo_sov_cpty,"Repos maturing in 30 days - other collateral, domestic sovereign, PSE or MDB counterparty",secured_funding,outflow,0.25,asf,0.00,A Table 3; C15(a)
repo_hqla2b_rmbs,Repos maturing in 30 days - backed by HQLA2B RMBS,secured_funding,outflow,0.25,asf,0.00,A Table 3; C15(a)
repo_hqla2b,Repos maturing in 30 days - backed by other HQLA2B,secured_funding,outflow,0.50,asf,0.00,A Table 3; C15(a)
repo_other,Repos maturing in 30 days - all other,secured_funding,outflow,1.00,asf,0.00,A Table 3; C15(a)
repo_30d_6m,Secured funding over 30 days and under 6 months,secured_funding,none,0,asf,0.00,C15(a)
repo_6m_1y,Secured funding 6 months to 1 year,secured_funding,none,0,asf,0.50,C14(f)
deriv_outflow,Derivatives cash outflows (net by counterparty),derivatives,outflow,1.00,none,0,A Table 3
coll_downgrade,Collateral to post on a 3-notch downgrade,derivatives,outflow,1.00,none,0,A Table 3
coll_excess,Excess non-segregated collateral callable by counterparties,derivatives,outflow,1.00,none,0,A Table 3
coll_due,Contractually required collateral not yet demanded,derivatives,outflow,1.00,none,0,A Table 3
coll_substitution,HQLA collateral substitutable to non-HQLA,derivatives,outflow,1.00,none,0,A Table 3
coll_valuation,Largest net 30-day collateral flow in past 24 months,derivatives,outflow,1.00,none,0,A Table 3
coll_posted_non_hqla1,Posted non-HQLA1 collateral (valuation change),derivatives,outflow,0.20,none,0,A Table 3
deriv_inflow,Derivatives cash inflows (net by counterparty),derivatives,inflow,1.00,none,0,A65
nsfr_deriv_net_asset,Derivative assets net of derivative liabilities (if positive),derivatives,none,0,rsf,1.00,C37(b)
nsfr_deriv_net_liab,Derivative liabilities net of derivative assets (if positive),derivatives,none,0,asf,0.00,C15(c)
nsfr_deriv_liab_gross,Derivative liabilities before variation margin,derivatives,none,0,rsf,0.20,C37(d)
im_posted,Initial margin posted and CCP default fund contributions,derivatives,none,0,rsf,0.85,C36(a)
fac_retail,Undrawn committed facilities - retail and SME,facilities,outflow,0.05,rsf,0.05,A Table 3; C41
fac_corp_credit,"Undrawn credit facilities - corporates, sovereigns and PSEs",facilities,outflow,0.10,rsf,0.05,A Table 3; C41
fac_corp_liquidity,"Undrawn liquidity facilities - corporates, sovereigns and PSEs",facilities,outflow,0.30,rsf,0.05,A Table 3; C41
fac_adi,Undrawn facilities - banks and other supervised ADIs,facilities,outflow,0.40,rsf,0.05,A Table 3; C41
fac_fi_credit,Undrawn credit facilities - other financial institutions,facilities,outflow,0.40,rsf,0.05,A Table 3; C41
fac_fi,Undrawn liquidity facilities - other financial institutions,facilities,outflow,1.00,rsf,0.05,A Table 3; C41
fac_other_legal,Undrawn facilities - other legal entities,facilities,outflow,1.00,rsf,0.05,A Table 3; C41
fac_revocable,Revocable credit and liquidity facilities,facilities,outflow,0.05,rsf,0.01,A Table 3; C41
trade_finance,Trade finance - average monthly net outflow (12 months),contingent,outflow,1.00,none,0,A Table 3
guarantees,Guarantees and letters of credit - average monthly net outflow (12 months),contingent,outflow,0.50,none,0,A Table 3
tf_guarantee_12m,"Trade finance, guarantees and letters of credit - net outflows over 12 months",contingent,none,0,rsf,1.00,C42
buyback_st,Own domestic short-term debt securities on issue (buyback),contingent,outflow,0.10,none,0,A Table 3
buyback_lt,Own domestic long-term debt securities on issue (buyback),contingent,outflow,0.05,none,0,A Table 3
structured_products,Non-contractual obligations - structured products and managed funds,contingent,outflow,0.05,none,0,A Table 3
affiliated_dealer,Affiliated dealer or market maker obligations (set your own rate),contingent,outflow,0.00,none,0,A Table 3
other_contingent,Other non-contractual contingent obligations (set your own rate),contingent,outflow,0.00,none,0,A Table 3
revrepo_hqla1,Reverse repos maturing in 30 days - backed by HQLA1,secured_lending,inflow,0.00,rsf,0.10,A Table 4; C31
revrepo_clf,Reverse repos maturing in 30 days - backed by CLF-eligible securities,secured_lending,inflow,0.00,rsf,0.15,A Table 4; C33(b)
revrepo_hqla2a,Reverse repos maturing in 30 days - backed by HQLA2A,secured_lending,inflow,0.15,rsf,0.15,A Table 4; C33(b)
revrepo_hqla2b_rmbs,Reverse repos maturing in 30 days - backed by HQLA2B RMBS,secured_lending,inflow,0.25,rsf,0.15,A Table 4; C33(b)
revrepo_hqla2b,Reverse repos maturing in 30 days - backed by other HQLA2B,secured_lending,inflow,0.50,rsf,0.15,A Table 4; C33(b)
margin_lending,Margin lending maturing in 30 days - non-HQLA collateral,secured_lending,inflow,0.50,rsf,0.50,A Table 4; C34(f)
revrepo_other,Reverse repos maturing in 30 days - all other collateral,secured_lending,inflow,1.00,rsf,0.15,A Table 4; C33(b)
revrepo_short_cover,Reverse repos maturing in 30 days - collateral covering short positions,secured_lending,inflow,0.00,rsf,0.15,A56; C33(b)
loan_due30_retail,Loan repayments due within 30 days - retail and SME,loans,inflow,0.50,none,0,A61
loan_due30_corp,Loan repayments due within 30 days - non-financial wholesale,loans,inflow,0.50,none,0,A62(b)
loan_due30_fi,Loan repayments due within 30 days - financial institutions,loans,inflow,1.00,none,0,A62(a)
other_inflows,Other contractual cash inflows,balance_sheet,inflow,1.00,none,0,A66
dep_placed_operational,Operational deposits held at other institutions,loans,inflow,0.00,rsf,0.50,A63; C34(d)
loan_mortgage,"Standard residential mortgages, LVR 80% or below, over 1 year",loans,none,0,rsf,0.65,C35(a)
loan_low_rw_gt1y,Other loans over 1 year with 35% or lower risk weight,loans,none,0,rsf,0.65,C35(b)
loan_other_gt1y,Other performing loans over 1 year,loans,none,0,rsf,0.85,C36(b)
loan_lt1y,"Loans under 1 year - retail, SME, corporates, sovereigns and PSEs",loans,none,0,rsf,0.50,C34(f)
loan_fi_lt6m,Unsecured loans to financial institutions under 6 months,loans,none,0,rsf,0.15,C33(b)
loan_fi_6m_1y,Loans to financial institutions and central banks 6 months to 1 year,loans,none,0,rsf,0.50,C34(c)
loan_fi_gt1y,Loans to financial institutions over 1 year,loans,none,0,rsf,1.00,C37(c)
loan_npl,Non-performing loans,loans,none,0,rsf,1.00,C37(c)
other_assets,"Other assets (fixed assets, capital deductions, unlisted equities)",balance_sheet,none,0,rsf,1.00,C37(c)
````

### `liquidity.py`

````python
"""APS 210 LCR and NSFR from aggregated positions. Factors live in rules.csv,
checked against APS 210 (July 2025, F2025L00653). The ref column cites the
paragraph: A = Attachment A (LCR), C = Attachment C (NSFR).

Run `python liquidity.py` for the self-check.
"""
import csv
import pathlib

with open(pathlib.Path(__file__).with_name("rules.csv"), newline="", encoding="utf-8") as f:
    RULES = {r["category"]: r for r in csv.DictReader(f)}


def calculate(positions):
    """positions: iterable of (category, amount). Amounts in AUD millions."""
    balances = {}
    for category, amount in positions:
        if category not in RULES:
            # Fail loudly: a silently dropped balance makes the ratio wrong.
            raise ValueError(f"category {category!r} is not in rules.csv")
        balances[category] = balances.get(category, 0.0) + float(amount)

    lcr = dict.fromkeys(("hqla1", "hqla2a", "hqla2b", "outflow", "inflow"), 0.0)
    nsfr = {"asf": 0.0, "rsf": 0.0}
    lines = []
    for category, amount in balances.items():
        r = RULES[category]
        lcr_w = amount * float(r["lcr_factor"])
        nsfr_w = amount * float(r["nsfr_factor"])
        if r["lcr_side"] in lcr:
            lcr[r["lcr_side"]] += lcr_w
        if r["nsfr_side"] in nsfr:
            nsfr[r["nsfr_side"]] += nsfr_w
        lines.append({**r, "amount": amount, "lcr_weighted": lcr_w, "nsfr_weighted": nsfr_w})

    # HQLA2B capped at 15% of HQLA, total HQLA2 capped at 40% of HQLA (Att A paras 6-7).
    # ponytail: caps use unadjusted amounts. Att A para 8 requires unwinding
    # repos, reverse repos and collateral swaps maturing within 30 days first;
    # that needs cash and collateral value per transaction, not category totals.
    # Only matters when an HQLA2 cap binds.
    l1, l2a, l2b = lcr["hqla1"], lcr["hqla2a"], lcr["hqla2b"]
    cut15 = max(l2b - 15 / 85 * (l1 + l2a), l2b - 15 / 60 * l1, 0.0)
    cut40 = max(l2a + l2b - cut15 - 2 / 3 * l1, 0.0)
    hqla = l1 + l2a + l2b - cut15 - cut40

    # Inflows capped at 75% of outflows.
    inflows_capped = min(lcr["inflow"], 0.75 * lcr["outflow"])
    net_outflows = lcr["outflow"] - inflows_capped

    return {
        "lcr": 100 * hqla / net_outflows if net_outflows else None,
        "nsfr": 100 * nsfr["asf"] / nsfr["rsf"] if nsfr["rsf"] else None,
        "hqla": hqla,
        "hqla_cap_cut": cut15 + cut40,
        "outflows": lcr["outflow"],
        "inflows": lcr["inflow"],
        "inflows_capped": inflows_capped,
        "net_outflows": net_outflows,
        "surplus": hqla - net_outflows,
        "asf": nsfr["asf"],
        "rsf": nsfr["rsf"],
        "lines": lines,
    }


if __name__ == "__main__":
    # Outflow 1000 x 5% = 50; inflow 100 x 50% = 50, capped at 37.5; net 12.5.
    r = calculate([("cash_esa", 100), ("dep_retail_stable", 1000), ("loan_due30_retail", 100)])
    assert abs(r["net_outflows"] - 12.5) < 1e-9 and abs(r["lcr"] - 800) < 1e-9, r
    assert r["nsfr"] is None  # cash has 0% RSF, so no ratio
    # HQLA2A 100 x 85% = 85, capped at 2/3 of HQLA1 (60) = 40; HQLA = 100.
    r = calculate([("cash_esa", 60), ("hqla2a", 100), ("dep_fi", 50)])
    assert abs(r["hqla"] - 100) < 1e-9 and abs(r["lcr"] - 200) < 1e-9, r
    # HQLA2B 100 x 50% = 50, capped at 15/85 of HQLA1 (85) = 15; HQLA = 100.
    r = calculate([("cash_esa", 85), ("hqla2b", 100), ("dep_fi", 50)])
    assert abs(r["hqla"] - 100) < 1e-9, r
    # NSFR: ASF 1000 x 95% = 950; RSF 1000 x 65% = 650.
    r = calculate([("dep_retail_stable", 1000), ("loan_mortgage", 1000)])
    assert abs(r["nsfr"] - 100 * 950 / 650) < 1e-9, r
    try:
        calculate([("typo", 1)])
        raise AssertionError("unknown category must raise")
    except ValueError:
        pass
    print("ok")
````

### `feeds.py`

````python
"""Data sources. Each returns a dict:
  positions   rows of (feed, category, amount, as_of_iso)
  ladder      rows of (bucket, inflows, outflows), contractual, in bucket order
  depositors  rows of (name, amount), largest funding providers
Amounts in AUD millions.
"""
import os
import pathlib
import random
from datetime import datetime, timezone

HERE = pathlib.Path(__file__).parent

# Made-up balances for a mid-sized bank.
_sim = {
    "cash_esa": 6000, "hqla1_gov": 12000, "hqla2a": 800, "hqla2b": 300,
    "sec_encumbered": 2500, "sec_other": 3000,
    "dep_retail_stable": 30000, "dep_retail_less_stable": 14000, "dep_sme": 6000,
    "dep_operational": 5000, "dep_corp": 7000, "dep_fi": 4000, "dep_term_gt30d": 9000,
    "debt_lt30d": 1500, "debt_gt1y": 12000, "capital": 9000,
    "fac_retail": 12000, "fac_corp_credit": 6000, "fac_corp_liquidity": 1000, "fac_fi": 500,
    "loan_due30_retail": 1200, "loan_due30_corp": 900, "loan_due30_fi": 600,
    "loan_mortgage": 60000, "loan_other_gt1y": 12000, "loan_lt1y": 7000,
    "loan_fi_lt6m": 1500, "other_assets": 3000,
    # secured funding and lending
    "repo_hqla1": 3000, "repo_hqla2a": 300, "repo_other": 200,
    "revrepo_hqla1": 2000, "revrepo_other": 300,
    # derivatives and collateral
    "deriv_outflow": 900, "deriv_inflow": 800, "coll_downgrade": 250, "coll_valuation": 400,
    "coll_posted_non_hqla1": 500, "nsfr_deriv_net_asset": 200, "nsfr_deriv_liab_gross": 1500,
    "im_posted": 300,
    # contingent obligations
    "trade_finance": 60, "guarantees": 80, "tf_guarantee_12m": 700,
    "buyback_st": 3000, "buyback_lt": 12000, "fac_revocable": 4000,
}
# bucket: [contractual inflows, contractual outflows]. At-call deposits sit in Overnight.
_sim_ladder = {
    "Overnight": [6500, 62000], "2-7 days": [900, 2500], "8-30 days": [2700, 6000],
    "31-90 days": [4000, 9000], "91-180 days": [5000, 7000], "181-365 days": [8000, 6000],
    "Over 1 year": [80000, 21000],
}
_sim_depositors = {
    "Super fund A": 1900, "State treasury B": 1500, "Insurer C": 1200, "Corporate D": 950,
    "Bank E": 800, "Fund manager F": 700, "Corporate G": 600, "Council H": 450,
    "University I": 400, "Corporate J": 350,
}


def sim():
    from liquidity import RULES
    now = datetime.now(timezone.utc).isoformat()
    walk = lambda v: v * (1 + random.gauss(0, 0.003))  # random walk per tick
    for k in _sim:
        _sim[k] = walk(_sim[k])
    for k in _sim_ladder:
        _sim_ladder[k] = [walk(v) for v in _sim_ladder[k]]
    for k in _sim_depositors:
        _sim_depositors[k] = walk(_sim_depositors[k])
    return {
        "positions": [(RULES[k]["feed"], k, v, now) for k, v in _sim.items()],
        "ladder": [(k, i, o) for k, (i, o) in _sim_ladder.items()],
        "depositors": list(_sim_depositors.items()),
    }


_conn = None


def _utc_iso(t):
    """Load timestamp as a UTC ISO string; '' when the feed has none (shown as stale)."""
    if t is None:
        return ""
    if t.tzinfo is None:  # TIMESTAMP_NTZ: assumed to already be UTC
        t = t.replace(tzinfo=timezone.utc)
    return t.astimezone(timezone.utc).isoformat(timespec="seconds")


def snowflake():
    """Runs positions.sql, ladder.sql and concentration.sql.
    Needs: pip install snowflake-connector-python and a named connection in
    ~/.snowflake/connections.toml (set SNOWFLAKE_CONNECTION to its name).
    No credentials live in this project.
    LIQ_AS_AT=YYYY-MM-DD sets the session variable $as_at the queries filter on
    (default: today), so a past date can be reconciled.
    """
    global _conn
    import snowflake.connector
    if _conn is None or _conn.is_closed():
        _conn = snowflake.connector.connect(connection_name=os.environ["SNOWFLAKE_CONNECTION"])
        with _conn.cursor() as cur:
            as_at = os.environ.get("LIQ_AS_AT") or datetime.now().date().isoformat()
            cur.execute("SET as_at = %s", (as_at,))
            role, wh = cur.execute("SELECT CURRENT_ROLE(), CURRENT_WAREHOUSE()").fetchone()
            print(f"Snowflake connected: role={role} warehouse={wh} as_at={as_at}")

    def run(name):
        with _conn.cursor() as cur:
            return cur.execute((HERE / name).read_text(encoding="utf-8")).fetchall()

    return {
        "positions": [(f, c, float(a or 0), _utc_iso(t)) for f, c, a, t in run("positions.sql")],
        "ladder": [(b, float(i or 0), float(o or 0)) for b, i, o in run("ladder.sql")],
        "depositors": [(n, float(a or 0)) for n, a in run("concentration.sql")],
    }


def get_source():
    return snowflake if os.environ.get("LIQ_SOURCE") == "snowflake" else sim
````

### `positions.sql`

````sql
-- ILLUSTRATIVE TEMPLATE. Every table and column name is a placeholder, and the
-- CASE logic is a starting shape, not a finished classification. Replace it
-- using the classification rules in IMPLEMENTATION_PLAN.md section 5.3.
--
-- Must return one row per (feed, category):
--   FEED      must equal the feed that rules.csv gives the category (the server
--             rejects a mismatch). Feeds: deposits | loans | securities |
--             facilities | collateral | balance_sheet | secured_funding |
--             secured_lending | derivatives | contingent
--   CATEGORY  a category from rules.csv
--   AMOUNT    AUD millions. Convert foreign currency to AUD here. Never NULL.
--   AS_OF     when that feed last loaded, as a UTC TIMESTAMP_TZ
--
-- $as_at is a session variable (YYYY-MM-DD) set by feeds.py from LIQ_AS_AT,
-- defaulting to today. Filter on it if the tables hold history.
--
-- Stock and flow rows: a loan appears TWICE, by design. Its balance goes to a
-- stock category (loan_mortgage, loan_lt1y, ...) for the NSFR, and the
-- repayments due within 30 days go to a flow category (loan_due30_*) for the
-- LCR. Flow categories are the ones with nsfr_side = none.
--
-- Classify and GROUP BY here so Snowflake aggregates millions of accounts and
-- the dashboard only receives a few dozen rows.

SELECT 'deposits' AS feed,
       CASE
         WHEN customer_type = 'RETAIL' AND days_to_maturity >= 365 AND NOT early_withdrawal_allowed
              THEN 'dep_term_gt1y'
         WHEN customer_type = 'RETAIL' AND days_to_maturity > 30 AND NOT early_withdrawal_allowed
              THEN IFF(fcs_covered AND (established_relationship OR transactional),
                       'dep_term_gt30d_stable', 'dep_term_gt30d')
         WHEN customer_type = 'RETAIL' AND fcs_covered AND (established_relationship OR transactional)
              THEN 'dep_retail_stable'
         WHEN customer_type = 'RETAIL'
              THEN IFF(  IFF(balance_aud > 250000, 2, 0)          -- scorecard, Att A para 40
                       + IFF(online_account, 2, 0)
                       + IFF(NOT established_relationship, 1, 0)
                       + IFF(rate_driven, 1, 0) >= 3,
                       'dep_retail_high_runoff', 'dep_retail_less_stable')
         WHEN customer_type = 'SME' AND group_funding_aud < 2000000 THEN 'dep_sme'
         WHEN is_operational AND fcs_covered                        THEN 'dep_operational_insured'
         WHEN is_operational                                        THEN 'dep_operational'
         WHEN customer_type = 'FINANCIAL'                           THEN 'dep_fi'
         ELSE 'dep_corp'
       END AS category,
       COALESCE(SUM(balance_aud), 0) / 1e6 AS amount,
       CONVERT_TIMEZONE('UTC', MAX(load_ts))::TIMESTAMP_TZ AS as_of
FROM   treasury.deposits                       -- placeholder
WHERE  as_at_date = TO_DATE($as_at)            -- if the table holds history
GROUP  BY 1, 2

UNION ALL

-- Unencumbered securities. Cash and ESA balances (cash_esa) also belong to the
-- securities feed in rules.csv.
SELECT 'securities',
       CASE
         WHEN hqla_class = 'HQLA1'     THEN 'hqla1_gov'
         WHEN hqla_class = 'HQLA2A'    THEN 'hqla2a'
         WHEN hqla_class = 'HQLA2B'    THEN 'hqla2b'
         ELSE 'sec_other'
       END,
       COALESCE(SUM(market_value_aud), 0) / 1e6,
       CONVERT_TIMEZONE('UTC', MAX(load_ts))::TIMESTAMP_TZ
FROM   treasury.securities                     -- placeholder
WHERE  NOT encumbered
   OR  (encumbered_days < 365 AND hqla_class IS NULL)   -- non-HQLA encumbered under 1 year keeps its own factor
GROUP  BY 1, 2

UNION ALL

-- Encumbered securities go on the collateral feed: no LCR credit, and an NSFR
-- factor that depends on how long they stay encumbered (Att C para 23).
SELECT 'collateral',
       CASE
         WHEN encumbered_days >= 365                              THEN 'sec_encumbered'
         WHEN encumbered_days >= 180 AND hqla_class IS NOT NULL   THEN 'hqla_enc_6m_1y'
         WHEN hqla_class = 'HQLA1'                                THEN 'hqla1_enc_lt6m'
         WHEN hqla_class = 'HQLA2A'                               THEN 'hqla2a_enc_lt6m'
         WHEN hqla_class = 'HQLA2B'                               THEN 'hqla2b_enc_lt6m'
       END,
       COALESCE(SUM(market_value_aud), 0) / 1e6,
       CONVERT_TIMEZONE('UTC', MAX(load_ts))::TIMESTAMP_TZ
FROM   treasury.securities                     -- placeholder; join the collateral table
WHERE  encumbered AND (encumbered_days >= 365 OR hqla_class IS NOT NULL)
GROUP  BY 1, 2

-- UNION ALL ... loans, stock rows (loan_mortgage, loan_low_rw_gt1y, loan_other_gt1y, loan_lt1y,
--               loan_fi_lt6m, loan_fi_6m_1y, loan_fi_gt1y, loan_npl)
-- UNION ALL ... loans, flow rows (loan_due30_retail, loan_due30_corp, loan_due30_fi)
-- UNION ALL ... facilities (fac_*)
-- UNION ALL ... balance sheet (debt_*, capital, other_assets, other_liabilities, abs_maturing)
-- UNION ALL ... secured funding (repo_*) and secured lending (revrepo_*, margin_lending), by collateral class
-- UNION ALL ... derivatives (deriv_outflow, deriv_inflow, coll_*, nsfr_deriv_*, im_posted)
--               Net derivative flows by counterparty before they reach this query.
-- UNION ALL ... contingent (trade_finance, guarantees, tf_guarantee_12m, buyback_*, structured_products)
--               trade_finance and guarantees take the 12-month AVERAGE monthly net outflow as AMOUNT.
;
````

### `ladder.sql`

````sql
-- ILLUSTRATIVE TEMPLATE: table and column names are placeholders.
-- Must return exactly 7 rows of (BUCKET, INFLOWS, OUTFLOWS) in AUD millions,
-- in bucket order, with 0 (not NULL, not a missing row) for an empty bucket.
-- Contractual maturity. A NULL maturity means at-call or open maturity:
--   liabilities with no maturity (at-call deposits) fall due Overnight (day 0);
--   assets with no maturity are treated as Over 1 year.
-- Outflows must cover every liability that funds the bank: deposits, wholesale
-- debt and repos. Inflows: loans, securities and reverse repos.

WITH flows AS (
  SELECT COALESCE(days_to_maturity, 9999) AS d, balance_aud AS inflow, 0 AS outflow
  FROM   treasury.loans                        -- placeholder
  UNION ALL
  SELECT COALESCE(days_to_maturity, 9999), market_value_aud, 0
  FROM   treasury.securities                   -- placeholder
  UNION ALL
  SELECT COALESCE(days_to_maturity, 0), 0, balance_aud
  FROM   treasury.deposits                     -- placeholder
  -- UNION ALL wholesale debt, repos (outflows) and reverse repos (inflows)
),
buckets (ord, bucket, lo, hi) AS (
  SELECT * FROM VALUES
    (1, 'Overnight',     0,     1),
    (2, '2-7 days',      2,     7),
    (3, '8-30 days',     8,    30),
    (4, '31-90 days',   31,    90),
    (5, '91-180 days',  91,   180),
    (6, '181-365 days', 181,  365),
    (7, 'Over 1 year',  366, 999999)
)
SELECT b.bucket,
       COALESCE(SUM(f.inflow), 0) / 1e6  AS inflows,
       COALESCE(SUM(f.outflow), 0) / 1e6 AS outflows
FROM   buckets b
LEFT   JOIN flows f ON f.d BETWEEN b.lo AND b.hi
GROUP  BY b.ord, b.bucket
ORDER  BY b.ord;
````

### `concentration.sql`

````sql
-- ILLUSTRATIVE TEMPLATE: table and column names are placeholders.
-- Must return (NAME, AMOUNT) in AUD millions: the largest funding providers.
-- Group by the ultimate parent / connected group, not the account.
-- The dashboard divides each amount by total deposits and wholesale funding
-- (every liability category in positions.sql except capital), so this query
-- must cover the same population: deposits AND wholesale debt and repo
-- counterparties where the holder is known.

SELECT counterparty_group_name            AS name,
       COALESCE(SUM(balance_aud), 0) / 1e6 AS amount
FROM   treasury.deposits                  -- placeholder; UNION wholesale funding by holder
GROUP  BY 1
ORDER  BY 2 DESC
LIMIT  10;
````

### `server.py`

````python
"""Live liquidity ticker. Run: python server.py  then open http://127.0.0.1:8210

Env: LIQ_SOURCE=snowflake (default: simulated), LIQ_POLL_SECONDS (default 2 sim,
300 Snowflake), PORT (default 8210), LIQ_AS_AT (Snowflake only, see feeds.py).
Polls only while a browser is connected, so an idle dashboard costs nothing.
Binds to localhost only: there is no login, so do not expose it on the network as is.
"""
import json
import os
import pathlib
import threading
import time
from http.server import BaseHTTPRequestHandler, ThreadingHTTPServer

from feeds import get_source
from liquidity import RULES, calculate

HERE = pathlib.Path(__file__).parent
SNOWFLAKE = os.environ.get("LIQ_SOURCE") == "snowflake"
POLL = float(os.environ.get("LIQ_POLL_SECONDS", 300 if SNOWFLAKE else 2))
ALL_FEEDS = sorted({r["feed"] for r in RULES.values()})
# Funding concentration denominator: deposits and wholesale funding, i.e. every
# liability category except capital and non-funding liabilities.
NOT_FUNDING = {"capital", "other_liabilities", "nsfr_deriv_net_liab"}

cond = threading.Condition()
latest = {"seq": 0, "data": "{}"}
clients = [0]


def snapshot(data):
    rows = data["positions"]
    feeds = dict.fromkeys(ALL_FEEDS, "")  # '' = no rows or no load time: shown as stale
    for feed, cat, _, as_of in rows:
        if cat in RULES and feed != RULES[cat]["feed"]:
            raise ValueError(f"{cat!r} arrived on feed {feed!r}; rules.csv says {RULES[cat]['feed']!r}")
        feeds[feed] = max(feeds[feed], as_of)
    snap = calculate((cat, amt) for _, cat, amt, _ in rows)
    snap.update(
        feeds=feeds,
        source="Snowflake" if SNOWFLAKE else "Simulated data",
        ladder=data["ladder"],
        depositors=sorted(data["depositors"], key=lambda d: -d[1])[:10],
        funding_total=sum(a for _, c, a, _ in rows
                          if RULES[c]["nsfr_side"] == "asf" and c not in NOT_FUNDING),
    )
    return json.dumps(snap, allow_nan=False)


def poll_loop():
    source = get_source()
    while True:
        with cond:
            cond.wait_for(lambda: clients[0] > 0)
        try:
            data = snapshot(source())
        except Exception as e:  # keep ticking; show the error on the page
            data = json.dumps({"error": f"{type(e).__name__}: {e}"})
        with cond:
            latest["seq"] += 1
            latest["data"] = data
            cond.notify_all()
        time.sleep(POLL)


class Handler(BaseHTTPRequestHandler):
    def do_GET(self):
        if self.path == "/":
            body = (HERE / "index.html").read_bytes()
            self.send_response(200)
            self.send_header("Content-Type", "text/html; charset=utf-8")
            self.send_header("Content-Length", str(len(body)))
            self.end_headers()
            self.wfile.write(body)
        elif self.path == "/stream":
            self.send_response(200)
            self.send_header("Content-Type", "text/event-stream")
            self.send_header("Cache-Control", "no-cache")
            self.end_headers()
            seen = 0
            with cond:
                clients[0] += 1
                cond.notify_all()
            try:
                while True:
                    with cond:
                        cond.wait_for(lambda: latest["seq"] != seen, timeout=15)
                        changed, seen, data = latest["seq"] != seen, latest["seq"], latest["data"]
                    self.wfile.write(f"data: {data}\n\n".encode() if changed else b": keepalive\n\n")
                    self.wfile.flush()
            except OSError:
                pass  # browser closed the tab
            finally:
                with cond:
                    clients[0] -= 1
        else:
            self.send_error(404)

    def log_message(self, *args):
        pass


if __name__ == "__main__":
    threading.Thread(target=poll_loop, daemon=True).start()
    server = ThreadingHTTPServer(("127.0.0.1", int(os.environ.get("PORT", 8210))), Handler)
    server.daemon_threads = True
    print("Liquidity ticker on http://127.0.0.1:%d" % server.server_port)
    server.serve_forever()
````

### `index.html`

````html
<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Liquidity Ticker</title>
<style>
:root {
  color-scheme: light dark;
  --page: #f9f9f7; --surface: #fcfcfb; --ink: #0b0b0b; --ink2: #52514e; --muted: #898781;
  --grid: #e1e0d9; --axis: #c3c2b7; --border: rgba(11,11,11,.10); --series: #2a78d6;
  --good: #0ca30c; --warning: #fab219; --critical: #d03b3b; --neg: #e34948;
}
@media (prefers-color-scheme: dark) {
  :root {
    --page: #0d0d0d; --surface: #1a1a19; --ink: #f0efec; --ink2: #c3c2b7;
    --grid: #2c2c2a; --axis: #383835; --border: rgba(255,255,255,.10); --series: #3987e5; --neg: #e66767;
  }
}
* { box-sizing: border-box; }
body { margin: 0; padding: 16px; background: var(--page); color: var(--ink);
       font: 14px/1.4 system-ui, -apple-system, "Segoe UI", sans-serif; }
header { display: flex; flex-wrap: wrap; gap: 8px 16px; align-items: baseline; margin-bottom: 12px; }
h1 { font-size: 18px; margin: 0; }
h2 { font-size: 13px; margin: 0 0 8px; color: var(--ink2); font-weight: 600; }
.meta { color: var(--muted); }
#error { display: none; padding: 8px 12px; margin-bottom: 12px; border: 1px solid var(--critical); border-radius: 8px; }
.tiles { display: grid; grid-template-columns: repeat(auto-fit, minmax(170px, 1fr)); gap: 12px; margin-bottom: 12px; }
.card { background: var(--surface); border: 1px solid var(--border); border-radius: 10px; padding: 12px 14px; }
.tile .label { color: var(--ink2); font-size: 12px; }
.tile .value { font-size: 30px; font-weight: 600; line-height: 1.2; }
.tile .sub { color: var(--muted); font-size: 12px; }
.status { display: inline-flex; gap: 5px; align-items: center; font-size: 12px; color: var(--ink2); }
.dot { width: 9px; height: 9px; border-radius: 50%; }
.chart { position: relative; margin-bottom: 12px; }
.plot { position: relative; height: 140px; margin-right: 44px; }
.plot svg { width: 100%; height: 100%; display: block; overflow: visible; }
.ylab { position: absolute; right: -44px; width: 40px; font-size: 11px; color: var(--muted); transform: translateY(-50%); font-variant-numeric: tabular-nums; }
#tip { position: absolute; display: none; pointer-events: none; background: var(--surface); border: 1px solid var(--border);
       border-radius: 6px; padding: 4px 8px; font-size: 12px; white-space: nowrap; transform: translate(-50%, -110%); }
.grid2 { display: grid; grid-template-columns: repeat(auto-fit, minmax(340px, 1fr)); gap: 12px; }
.scroll { overflow-x: auto; }
table { width: 100%; border-collapse: collapse; font-variant-numeric: tabular-nums; }
th, td { padding: 4px 6px; text-align: right; border-bottom: 1px solid var(--grid); white-space: nowrap; }
th { color: var(--muted); font-weight: 500; font-size: 12px; }
th:first-child, td:first-child { text-align: left; white-space: normal; }
tr.total td { font-weight: 600; border-bottom: 0; }
td.barcell { width: 30%; min-width: 90px; padding: 4px 0 4px 10px; }
.track { position: relative; height: 12px; }
.track.mid { border-left: 0; background: linear-gradient(var(--axis), var(--axis)) 50% 0 / 1px 100% no-repeat; }
.bar { position: absolute; top: 0; bottom: 0; border-radius: 3px; background: var(--series); }
.bar.neg { background: var(--neg); }
.note { color: var(--muted); font-size: 12px; margin-top: 8px; }
.feeds { display: flex; flex-wrap: wrap; gap: 8px; }
.feed { border: 1px solid var(--border); border-radius: 999px; padding: 2px 10px; font-size: 12px; color: var(--ink2); }
</style>
</head>
<body>
<header>
  <h1>APS 210 Liquidity Ticker</h1>
  <span class="meta" id="source">Connecting…</span>
  <span class="meta" id="clock"></span>
  <span class="meta">AUD millions</span>
</header>
<div id="error" role="alert"></div>

<section class="tiles" id="tiles"></section>

<section class="card chart">
  <h2>LCR this session (%)</h2>
  <div class="plot" id="plot">
    <svg id="svg" viewBox="0 0 600 140" preserveAspectRatio="none" role="img" aria-label="LCR over this session"></svg>
    <div id="tip"></div>
  </div>
</section>

<section class="card" style="margin-bottom:12px">
  <h2>Feed freshness</h2>
  <div class="feeds" id="feeds"></div>
</section>

<section class="grid2" id="risk" style="margin-bottom:12px"></section>

<section class="grid2" id="tables"></section>

<script>
// Internal early-warning triggers above the 100% regulatory minimum. Set to your board limits.
const AMBER = { lcr: 110, nsfr: 105 };
const STALE_MS = 60 * 60 * 1000;   // a feed older than this is flagged stale
const STALE_MS_BY_FEED = {};       // per-feed override, e.g. { loans: 26 * 3600e3 } for a daily batch
const MAX_POINTS = 900;

const $ = id => document.getElementById(id);
const esc = s => String(s).replace(/[&<>"]/g, c => ({ "&": "&amp;", "<": "&lt;", ">": "&gt;", '"': "&quot;" }[c]));
const num = v => Math.round(v).toLocaleString("en-AU");
const pct = v => v == null ? "n/a" : v.toFixed(1) + "%";
const history = [];

function status(value, amber) {
  if (value == null) return ["var(--muted)", "–", "No ratio"];
  if (value < 100) return ["var(--critical)", "✕", "Below 100% minimum"];
  if (value < amber) return ["var(--warning)", "▲", "Below " + amber + "% trigger"];
  return ["var(--good)", "✓", "Above " + amber + "% trigger"];
}

function tile(label, value, sub, st) {
  const s = st ? `<div class="status"><span class="dot" style="background:${st[0]}"></span>${st[1]} ${esc(st[2])}</div>` : "";
  return `<div class="card tile"><div class="label">${esc(label)}</div><div class="value">${esc(value)}</div>` +
         `<div class="sub">${esc(sub)}</div>${s}</div>`;
}

function table(title, lines, factorKey, weightedKey, totalLabel, total, extraRows = "") {
  const rows = lines.sort((a, b) => b[weightedKey] - a[weightedKey]).map(l =>
    `<tr title="APS 210 ${esc(l.ref)}"><td>${esc(l.label)}</td><td>${num(l.amount)}</td><td>${(100 * l[factorKey]).toFixed(0)}%</td><td>${num(l[weightedKey])}</td></tr>`).join("");
  return `<div class="card"><h2>${esc(title)}</h2><div class="scroll"><table>` +
    `<tr><th>Line</th><th>Balance</th><th>Factor</th><th>Weighted</th></tr>${rows}${extraRows}` +
    `<tr class="total"><td>${esc(totalLabel)}</td><td></td><td></td><td>${num(total)}</td></tr></table></div></div>`;
}

function ladderCard(ladder) {
  let cum = 0;
  const rows = ladder.map(([bucket, inflow, outflow]) => ({ bucket, inflow, outflow, net: inflow - outflow, cum: cum += inflow - outflow }));
  const max = Math.max(1, ...rows.map(r => Math.abs(r.cum)));
  const body = rows.map(r => {
    const w = Math.abs(r.cum) / max * 50, side = r.cum < 0 ? `right:50%` : `left:50%`;
    return `<tr><td>${esc(r.bucket)}</td><td>${num(r.inflow)}</td><td>${num(r.outflow)}</td><td>${num(r.net)}</td><td>${num(r.cum)}</td>` +
      `<td class="barcell"><div class="track mid" title="${esc(r.bucket)}: cumulative gap ${num(r.cum)}">` +
      `<div class="bar${r.cum < 0 ? " neg" : ""}" style="${side};width:${w.toFixed(1)}%"></div></div></td></tr>`;
  }).join("");
  return `<div class="card"><h2>Maturity ladder (contractual)</h2><div class="scroll"><table>` +
    `<tr><th>Bucket</th><th>Inflows</th><th>Outflows</th><th>Net gap</th><th>Cumulative</th><th>Cumulative gap</th></tr>${body}</table></div>` +
    `<div class="note">Bars left of the centre line are a cumulative shortfall. Contractual, so at-call deposits fall due overnight.</div></div>`;
}

function concentrationCard(depositors, total) {
  const max = Math.max(1, ...depositors.map(d => d[1]));
  const top = depositors.reduce((s, d) => s + d[1], 0);
  const share = v => total ? (100 * v / total).toFixed(1) + "%" : "n/a";
  const body = depositors.map(([name, amt]) =>
    `<tr><td>${esc(name)}</td><td>${num(amt)}</td><td>${share(amt)}${total && amt / total > 0.01 ? " ▲" : ""}</td>` +
    `<td class="barcell"><div class="track" title="${esc(name)}: ${num(amt)}"><div class="bar" style="left:0;width:${(amt / max * 100).toFixed(1)}%"></div></div></td></tr>`).join("");
  return `<div class="card"><h2>Funding concentration (top ${depositors.length})</h2><div class="scroll"><table>` +
    `<tr><th>Counterparty</th><th>Amount</th><th>% of funding</th><th></th></tr>${body}` +
    `<tr class="total"><td>Top ${depositors.length} total</td><td>${num(top)}</td><td>${share(top)}</td><td></td></tr></table></div>` +
    `<div class="note">▲ marks a counterparty above 1% of deposits and wholesale debt.</div></div>`;
}

function render(d) {
  $("error").style.display = d.error ? "block" : "none";
  if (d.error) { $("error").textContent = "Feed error, showing last good values. " + d.error; return; }
  $("source").textContent = d.source;
  $("clock").textContent = "Updated " + new Date().toLocaleTimeString();

  $("tiles").innerHTML =
    tile("LCR", pct(d.lcr), "HQLA ÷ 30-day net outflows", status(d.lcr, AMBER.lcr)) +
    tile("NSFR", pct(d.nsfr), "Available ÷ required stable funding", status(d.nsfr, AMBER.nsfr)) +
    tile("HQLA", num(d.hqla), "After haircuts and caps") +
    tile("Net cash outflows", num(d.net_outflows), "30-day stress") +
    tile("HQLA surplus", num(d.surplus), "Above 100% LCR");

  const now = Date.now();
  $("feeds").innerHTML = Object.entries(d.feeds).map(([f, t]) => {
    const age = now - Date.parse(t), stale = !t || age > (STALE_MS_BY_FEED[f] ?? STALE_MS);
    const txt = !t ? "no data" : age < 90e3 ? Math.max(0, Math.round(age / 1e3)) + "s ago" : Math.round(age / 60e3) + " min ago";
    return `<span class="feed"><span class="dot" style="display:inline-block;background:${stale ? "var(--critical)" : "var(--good)"}"></span> ` +
           `${esc(f.replace("_", " "))}: ${stale ? "✕ stale, " : "✓ "}${txt}</span>`;
  }).join("");

  $("risk").innerHTML = ladderCard(d.ladder) + concentrationCard(d.depositors, d.funding_total);

  const by = (key, sides) => d.lines.filter(l => sides.includes(l[key]));
  const cut = d.hqla_cap_cut > 0 ? `<tr><td>Less HQLA2 cap excess</td><td></td><td></td><td>-${num(d.hqla_cap_cut)}</td></tr>` : "";
  const cap = d.inflows > d.inflows_capped ? `<tr><td>Less excess over 75% cap</td><td></td><td></td><td>-${num(d.inflows - d.inflows_capped)}</td></tr>` : "";
  $("tables").innerHTML =
    table("HQLA", by("lcr_side", ["hqla1", "hqla2a", "hqla2b"]), "lcr_factor", "lcr_weighted", "Total HQLA", d.hqla, cut) +
    table("Cash outflows (30 days)", by("lcr_side", ["outflow"]), "lcr_factor", "lcr_weighted", "Total outflows", d.outflows) +
    table("Cash inflows (30 days)", by("lcr_side", ["inflow"]), "lcr_factor", "lcr_weighted", "Inflows counted", d.inflows_capped, cap) +
    table("Available stable funding", by("nsfr_side", ["asf"]), "nsfr_factor", "nsfr_weighted", "Total ASF", d.asf) +
    table("Required stable funding", by("nsfr_side", ["rsf"]), "nsfr_factor", "nsfr_weighted", "Total RSF", d.rsf);

  if (d.lcr != null) {
    history.push({ t: now, v: d.lcr });
    if (history.length > MAX_POINTS) history.shift();
    drawChart();
  }
}

let scale = null;
function drawChart() {
  const W = 600, H = 140, vals = history.map(p => p.v);
  let lo = Math.min(100, ...vals), hi = Math.max(100, ...vals);
  const pad = (hi - lo) * 0.1 || 1; lo -= pad; hi += pad;
  const x = i => history.length < 2 ? W : i * W / (history.length - 1);
  const y = v => H - (v - lo) / (hi - lo) * H;
  scale = { x, y, W, H };
  const pts = history.map((p, i) => x(i).toFixed(1) + "," + y(p.v).toFixed(1)).join(" ");
  $("svg").innerHTML =
    `<line x1="0" x2="${W}" y1="${y(100)}" y2="${y(100)}" stroke="var(--axis)" stroke-dasharray="4 4" vector-effect="non-scaling-stroke"/>` +
    `<polyline points="${pts}" fill="none" stroke="var(--series)" stroke-width="2" stroke-linejoin="round" vector-effect="non-scaling-stroke"/>` +
    `<line id="cross" y1="0" y2="${H}" stroke="var(--axis)" vector-effect="non-scaling-stroke" visibility="hidden"/>`;
  const last = vals[vals.length - 1];
  $("plot").querySelectorAll(".ylab").forEach(e => e.remove());
  const labels = [[100, "100%"]];
  if (Math.abs(y(last) - y(100)) > 14) labels.push([last, last.toFixed(1) + "%"]);
  for (const [v, text] of labels) {
    const el = document.createElement("div");
    el.className = "ylab"; el.textContent = text; el.style.top = (y(v) / H * 100) + "%";
    $("plot").appendChild(el);
  }
}

$("plot").addEventListener("mousemove", e => {
  if (!scale || !history.length) return;
  const r = $("svg").getBoundingClientRect();
  const i = Math.max(0, Math.min(history.length - 1, Math.round((e.clientX - r.left) / r.width * (history.length - 1))));
  const p = history[i], cross = $("cross"), tip = $("tip");
  if (cross) { cross.setAttribute("x1", scale.x(i)); cross.setAttribute("x2", scale.x(i)); cross.setAttribute("visibility", "visible"); }
  tip.style.display = "block";
  tip.style.left = (scale.x(i) / scale.W * r.width) + "px";
  tip.style.top = (scale.y(p.v) / scale.H * r.height) + "px";
  tip.textContent = p.v.toFixed(1) + "% at " + new Date(p.t).toLocaleTimeString();
});
$("plot").addEventListener("mouseleave", () => {
  $("tip").style.display = "none";
  const c = $("cross"); if (c) c.setAttribute("visibility", "hidden");
});

const es = new EventSource("/stream");
es.onmessage = e => render(JSON.parse(e.data));
es.onerror = () => { $("source").textContent = "Disconnected, retrying…"; };
</script>
</body>
</html>
````

### SHA-256 checksums

Computed over each file as UTF-8 with LF line endings and one trailing newline.

```
21b205e7428198a566732763072a2b715b47c00baf3a3173696f4fecec57ce9f  rules.csv
016b8eb11679dd67a99be71be65d64d96bece8d2afa0737ce5c5708a610ddfda  liquidity.py
843103994dc8a7933b09d82a8a78e1bb6b1707d84f8d7c51d2aebbb69dcc5054  feeds.py
803d57467c28c2a6e42d60f3792d2cc521677141791a6db167aa2a0a9f7837d4  positions.sql
7c0a3e83d1b338945b18950dee0fdfd0f3f78228d031131028d8ef14bc552810  ladder.sql
d6547eaa0942c00d4e330453f52cf97c0387f26b2583644b53511379ede88401  concentration.sql
b2b0509092edf31153afb78b17952cc9572756854e36523af36877fb1ce7a82f  server.py
8131e56dcd7f1dfec9b096899356e908a99ec12427ffd6b730cd410d9eef2f10  index.html
```
