# Understanding Bank Liquidity in Australia

A guide to how liquidity is measured and managed under APRA Prudential Standard
APS 210 Liquidity (July 2025 version), written for someone with no banking
background.

## How to use this guide

The chapters build on each other, but each can be read alone.

| If you want to... | Read |
|---|---|
| Understand what liquidity is and why banks fail without it | Chapter 1 |
| Know who the regulators are and how the rules are organised | Chapter 2 |
| Read a bank's balance sheet and annual report | Chapter 3 |
| Look up an instrument or market term (repo, covered bond, margin) | Chapter 4 |
| Follow the Liquidity Coverage Ratio line by line | Chapter 5 |
| Follow the Net Stable Funding Ratio line by line | Chapter 6 |
| Understand the simpler regime for smaller institutions | Chapter 7 |
| Know what else APS 210 requires beyond the ratios | Chapter 8 |
| See how a Treasury team uses all of this day to day | Chapter 9 |
| Look up any term or acronym | Chapter 10 |
| Connect the guide to the dashboard's rules table | Appendix A |
| See what was and was not verified | Appendix B |

**Suggested paths**

- **One hour:** Chapter 1, the Example Bank section of Chapter 3, then the
  worked examples in Chapters 5 and 6.
- **One day:** Chapters 1 to 6 in order, then Chapter 9.
- **As a reference:** the quick reference tables at the end of Chapters 5 and
  6, and the glossary in Chapter 10.

## The whole subject on one page

A bank borrows money that can leave quickly (deposits) and lends it for a long
time (mortgages). Liquidity is its ability to pay what it owes, when it is due,
without taking unacceptable losses. APS 210 sets three kinds of requirement.

**1. Hold enough liquid assets to survive a 30-day stress.** This is the
Liquidity Coverage Ratio, for the larger banks.

```
LCR = stock of high-quality liquid assets (HQLA)
      -------------------------------------------------   must be at least 100%
      total net cash outflows over the next 30 days

net cash outflows = outflows - min(inflows, 75% of outflows)
```

**2. Fund long-term assets with stable funding.** This is the Net Stable
Funding Ratio, a one-year view, also for the larger banks.

```
NSFR = available stable funding (ASF)
       --------------------------------   must be at least 100%
       required stable funding (RSF)
```

**3. Manage liquidity risk properly.** Board oversight, a risk tolerance,
limits, stress tests, a funding strategy and a contingency funding plan.
Smaller institutions replace the two ratios with a simpler rule: hold liquid
assets of at least 9% of liabilities (Minimum Liquidity Holdings).

Each ratio is built the same way: take every balance on and off the balance
sheet, put it in a category defined by the standard, multiply it by that
category's factor, and add up. Most of the skill is in the classification.

## The running example

Every chapter uses the same fictional bank, **Example Bank**, with total assets
of A$100 billion. Its balance sheet is introduced in Chapter 3. Its LCR works
out to **147.2%** (Chapter 5) and its NSFR to **136.3%** (Chapter 6).

## Conventions

- References look like this: `(APS 210 para 55)` for the main body of the
  standard, `(Att A para 37)` for Attachment A (LCR), `(Att B para 2)` for
  Attachment B (Minimum Liquidity Holdings), `(Att C para 12)` for Attachment C
  (NSFR).
- Money is in Australian dollars. "bn" is billions, "m" is millions.
- Statements that come from outside APS 210 and could not be checked against an
  official source are worded cautiously and listed in Appendix B.
- This guide explains the rules. It is not legal, accounting or investment
  advice, and the standard itself always takes precedence.

## Contents

- Chapter 1: Banking and liquidity from first principles
- Chapter 2: Who regulates Australian banks, and the rulebook
- Chapter 3: How to read a bank balance sheet
- Chapter 4: Instruments and market terms
- Chapter 5: The Liquidity Coverage Ratio, line by line
- Chapter 6: The Net Stable Funding Ratio, line by line
- Chapter 7: The Minimum Liquidity Holdings regime
- Chapter 8: The rest of APS 210: governance and risk management
- Chapter 9: How Treasury manages liquidity day to day
- Chapter 10: Glossary, acronyms and common confusions
- Appendix A: Connecting the guide to the dashboard's rules table
- Appendix B: What was checked, and what was not

---

# Chapter 1: Banking and liquidity from first principles

## What a bank does

A **bank** takes money from people and businesses and lends it to other people and businesses. The money it takes in is a **deposit**: a sum a customer places with the bank, which the bank must hand back on the terms agreed. The money it lends out is a **loan**. The bank earns the difference between the interest it charges on loans and the interest it pays on deposits and other funding. That difference, expressed as a percentage of the bank's earning assets, is the **net interest margin**.

Two accounting words appear straight away.

- An **asset** is something the bank owns or is owed. A loan is an asset: the borrower owes the bank money.
- A **liability** is something the bank owes. A deposit is a liability: the bank owes the customer money.

Your deposit is therefore the bank's liability, and your mortgage is the bank's asset. The list of all of a bank's assets, liabilities and equity at one moment is its **balance sheet**. **Equity** is what is left when liabilities are subtracted from assets. It belongs to the shareholders, and it is the bank's cushion for absorbing losses. (Chapter 3 walks through a real balance sheet line by line.)

In Australia, the bodies that may take deposits from the public are called **authorised deposit-taking institutions (ADIs)**. They include banks, building societies and credit unions. Chapter 2 explains who authorises them and how they are regulated.

### Example Bank

This guide uses a fictional bank, Example Bank, throughout. Its balance sheet (A$ billions) is:

| Assets | A$bn | Liabilities and equity | A$bn |
|---|---|---|---|
| Cash and balances with the RBA | 5.0 | Retail deposits, stable (at call) | 25.0 |
| Government and semi-government securities | 12.0 | Retail deposits, less stable (at call, scorecard 0 to 2) | 15.0 |
| Other debt securities (non-HQLA, over 1 year) | 3.0 | Retail term deposits (over 30 days, under 1 year, no early withdrawal, less stable) | 10.0 |
| Loans to other banks (under 6 months, unsecured) | 2.0 | SME deposits (qualifying, less stable) | 5.0 |
| Residential mortgages (standard, LVR 80% or below, over 1 year) | 50.0 | Corporate operational deposits (not fully insured) | 4.0 |
| Business loans (over 1 year) | 15.0 | Corporate non-operational deposits (not fully insured) | 6.0 |
| Personal and business loans (under 1 year) | 8.0 | Financial institution deposits (at call) | 4.0 |
| Other assets (premises, goodwill, tax assets) | 5.0 | Wholesale debt maturing within 30 days | 1.0 |
| | | Wholesale debt, over 30 days and under 6 months | 3.0 |
| | | Wholesale debt, 6 months to under 1 year | 2.0 |
| | | Wholesale debt, 1 year or more | 15.0 |
| | | Other liabilities (no stated maturity) | 2.0 |
| | | Shareholders' equity (treated as regulatory capital) | 8.0 |
| **Total assets** | **100.0** | **Total liabilities and equity** | **100.0** |

The two sides balance because equity is defined as the balancing item: assets 100.0 = liabilities 92.0 + equity 8.0.

> **Example:** Look at the bank's biggest asset and its biggest liabilities. The A$50.0bn of mortgages will be repaid slowly over many years. But A$25.0bn + A$15.0bn = A$40.0bn of retail deposits can be withdrawn on any day. The bank has promised customers quick access to money that it has lent out for a long time. The rest of this chapter is about why that is both the business of banking and its central weakness.

## Maturity transformation: borrow short, lend long

**Maturity** is the date on which a financial obligation must be repaid. An at-call deposit has no fixed maturity (the customer can ask for it back immediately). A 25-year mortgage has a maturity 25 years away. **Maturity transformation** is what a bank does when it funds long-maturity assets with shorter-maturity liabilities: "borrow short, lend long".

### Why it exists

Savers want safety and access. Borrowers want certainty that they can keep the money for years. A bank bridges the two. It pools thousands of depositors, each of whom may withdraw at any time, and relies on the fact that on a normal day only a small, predictable fraction will do so. New deposits arrive to replace those leaving. Because the bank can lend most of the pool for long periods, borrowers get long loans and savers get access and interest. This is socially useful, and it is why banks earn a margin: long-term interest rates are usually higher than short-term ones, and the bank is paid for bearing the mismatch.

### How it works, with numbers

Example Bank funds A$73.0bn of customer loans (A$50.0bn + A$15.0bn + A$8.0bn) from A$65.0bn of customer deposits, plus wholesale debt and equity. Of the deposits, A$40.0bn is at call. If every at-call depositor asked for their money today, the bank could not pay: its cash and government securities total only A$17.0bn. It does not need to be able to pay everyone at once on a normal day. It does need to be able to pay the people who do turn up, today, next week and next month, even if more turn up than usual.

### What can go wrong

If the bank cannot meet payments as they fall due, it has a **liquidity** problem. **Liquidity** is the ability to meet payment obligations in cash as they fall due, without unacceptable losses. **Liquidity risk** is the risk that the bank will not be able to do so. APS 210 puts it as the requirement that an ADI "must at all times maintain sufficient liquidity to meet its obligations as they fall due and hold a minimum level of liquid assets to survive a severe liquidity stress" (APS 210 para 12). It also requires that activities be funded "with stable sources of funding on an ongoing basis" (APS 210 para 13). Those two sentences are the seeds of the two Basel ratios described later in this chapter.

> **Why it matters:** Maturity transformation is not a flaw that can be engineered away. It is the product. The regulatory task is to make sure a bank holds enough liquid assets, and is funded stably enough, that the mismatch is survivable.

## Four different things: liquidity, solvency, capital and profitability

Newcomers often use these words as if they were one idea. They are four separate measures of four separate questions.

| Concept | Question it answers | Measured by | Looks at |
|---|---|---|---|
| **Liquidity** | Can the bank pay what it owes, in cash, when it falls due? | Liquid assets against near-term cash outflows (for example the LCR) | Timing of cash |
| **Solvency** | Are the bank's assets worth more than its liabilities? | Assets minus liabilities (equity) being above zero | Value |
| **Capital** | How big is the loss-absorbing cushion, relative to the risk the bank is running? | Capital as a share of risk-weighted assets, and the leverage ratio | Loss absorption |
| **Profitability** | Does the bank earn more than it spends? | Net profit, return on equity, net interest margin | Income over a period |

Some definitions:

- **Solvency** means that assets exceed liabilities. **Insolvency** is the opposite: the bank owes more than it owns, so even if all assets were sold at fair value, creditors could not be paid in full.
- **Capital** is the part of the bank's funding that can absorb losses without the bank failing to pay depositors. It is mainly shareholders' equity. Regulators define layers: **CET1** (Common Equity Tier 1: ordinary shares and retained earnings), **Additional Tier 1** (loss-absorbing securities such as some hybrids) and **Tier 2** (subordinated debt, which ranks below depositors). A **risk weight** is a percentage applied to an asset to reflect its riskiness, and **risk-weighted assets** are assets multiplied by their risk weights. The **leverage ratio** compares capital with total exposures without risk weighting. (Capital standards are summarised in Chapter 2 and explained in detail in Chapter 3. Capital is not the subject of APS 210.)
- **Retained earnings** are profits kept in the bank rather than paid as dividends. They build equity.
- **Profitability** is how much the bank earns after all costs, including the cost of bad loans.

### Why they differ: three short cases

1. **Solvent, profitable, illiquid.** A bank has assets worth 110 and liabilities of 100, earns a healthy profit, and holds capital well above the minimum. But most of its assets are 25-year loans and half its funding is at-call deposits. In a sudden withdrawal, it cannot turn the loans into cash fast enough. It fails even though on paper it is worth more than it owes.
2. **Liquid, insolvent.** A bank holds a lot of cash from a recent wholesale bond issue, but its loan book has lost a third of its value. It can pay today's bills but is hopelessly insolvent. Cash buys time, not solvency.
3. **Profitable, but under-capitalised.** A bank writes high-margin, risky loans. Reported profit is high; the capital cushion is thin. One bad year could wipe out equity.

> **Why it matters:** "The bank has plenty of capital" does not mean "the bank has plenty of liquidity". Capital protects against losses on assets. Liquidity protects against the timing of cash. A bank run is a liquidity event first; if it is not stopped, forced sales of assets at low prices turn it into a solvency event.

The links run both ways. A bank that looks insolvent will find depositors and wholesale lenders pulling funds (solvency worry causes a liquidity problem). A bank that is forced to sell assets cheaply to raise cash makes losses, and its capital shrinks (a liquidity problem causes a solvency problem). Regulators therefore treat liquidity and capital as complementary, not as substitutes.

## Funding liquidity risk and market liquidity risk

APS 210 para 20 defines two concepts that senior management and the Board must understand, together with the links between them.

| Term | APS 210 definition | Plain meaning |
|---|---|---|
| **Funding liquidity risk** | "the risk that an ADI may not be able to meet its financial obligations as they fall due" (APS 210 para 20) | Can we pay when depositors and lenders want their money? |
| **Market liquidity risk** | "the risk that liquidity in financial markets, such as the market for debt securities, may reduce significantly" (APS 210 para 20) | Can we sell or borrow against our assets at a sensible price when we need to? |

APS 210 para 20 also says that other risks, including credit, market, operational and reputation risks, affect the overall liquidity strategy. **Credit risk** is the risk that a borrower or counterparty fails to pay. A **counterparty** is the other party to a transaction.

### How they feed each other

1. Funding liquidity risk bites: depositors leave. The bank needs cash.
2. It tries to sell securities. If many banks do this at once, the market becomes illiquid, buyers disappear and prices fall. This is market liquidity risk.
3. The bank gets less cash than it expected. It may take losses. Its reported capital falls.
4. Lenders and depositors see the losses, become more worried and withdraw more. Funding liquidity risk rises again.

This is a loop. It is the reason the regulator does not just ask "do you hold securities?" but "can those securities be turned into cash in a crisis, and are they free to be used?" It is also why a bank cannot count on selling lower-quality assets at their normal price, and why the LCR applies haircuts (Chapter 5).

> **In the standard:** "Senior management and the Board must be able to demonstrate a thorough understanding of the links between funding liquidity risk ... and market liquidity risk ..." (APS 210 para 20).

## Anatomy of a bank run

A **bank run** is a rush of depositors or other funders to withdraw their money because they fear the bank may not be able to pay everyone. The run can be rational for each individual even when it is harmful for the group. If you believe others will withdraw, and the bank can pay only those who ask first, you should ask first. Fear becomes self-fulfilling.

### A run in stages

1. **Trigger.** News, rumour, a loss announcement, a credit rating downgrade, a failed bond issue or the failure of another bank.
2. **First movers.** The most informed and mobile funders leave first: large wholesale lenders, corporate treasurers, fund managers.
3. **Spread.** Depositors who are not insured, or who hear about the departures, follow.
4. **Asset sales.** The bank sells liquid assets, then less liquid assets at a loss, and borrows against what it has left.
5. **Closure or rescue.** Either confidence is restored (by a regulator, a central bank or a buyer), or the bank cannot pay and fails.

### Retail run versus wholesale run

| Feature | Retail run | Wholesale run |
|---|---|---|
| **Who** | Households and small businesses | Banks, funds, large corporates, institutional investors |
| **Speed (historically)** | Days to weeks (queues, branches) | Hours to days |
| **Information** | Often rumour and media | Often quick, detailed credit analysis |
| **Sticky if insured?** | Partly: insured depositors have less reason to run | Large balances are mostly uninsured, so no protection |
| **How it shows up** | Withdrawals, transfers out, card and ATM usage | Refusal to roll over short-term debt, shorter terms, higher demands for collateral |

This is why the LCR assigns low run-off rates to stable, insured retail deposits and much higher rates to unsecured funding from financial institutions (Chapter 5). The Example Bank LCR in later chapters assumes, for example, 5% of A$25.0bn of stable retail deposits leaves in a 30-day stress, but 100% of A$4.0bn of financial institution deposits.

**Rollover risk** is the risk that when a debt matures, the bank cannot borrow again to repay it. A wholesale run is mostly rollover risk: the lenders simply do not renew.

### Contagion

**Contagion** is the spread of stress from one institution to others. It travels through:

- **Direct links**: Bank A owes Bank B money (interbank lending), so A's failure hurts B. **Interbank** means between banks.
- **Market prices**: A's forced asset sales lower prices of assets that B also holds.
- **Confidence**: Depositors reason that if A had a problem, B may have the same one.

### Why confidence matters

A bank's liabilities are promises. The value of those promises depends on belief that they will be honoured. Most of the time this belief is correct and costless. In a crisis, belief is everything. Regulators therefore care about the quality of information, the speed of the response and the credibility of backstops.

### Deposit insurance and the lender of last resort

Two public arrangements exist to stop runs.

**Deposit insurance** protects small depositors if a bank fails, so they have no reason to rush. In Australia this is the **Financial Claims Scheme**, which as published by APRA covers deposits up to A$250,000 per account holder per ADI. It is paid for by government, not by a premium on each deposit. Chapter 2 covers the scheme in detail. The scorecard for less stable retail deposits in the LCR also uses A$250,000 (Att A para 40).

A **central bank** is the public institution that issues currency and acts as the bank to the banking system. In Australia it is the **Reserve Bank of Australia (RBA)**. The **lender of last resort** is the central bank acting as the lender when no one else will, to a bank that is solvent but cannot raise cash in the market. In Australia this is done through the RBA's standing arrangements and, in extreme cases, **Exceptional Liquidity Assistance (ELA)**. APS 210 para 70 says an ADI under severe liquidity stress may request ELA from the RBA, but must first notify APRA immediately. Chapter 2 gives more detail.

> **Watch out:** Deposit insurance and the lender of last resort are emergency backstops, not business models. Regulators require banks to hold their own liquid assets precisely so that these backstops are rarely or never used. A bank that plans to rely on the central bank is not meeting the standard.

## What makes an asset "liquid"?

A **liquid asset** is one that can be turned into cash quickly, with little or no loss of value. Three properties matter.

| Property | Question | Strong example | Weak example |
|---|---|---|---|
| **Speed** | How fast can it become cash? | Balance at the RBA (immediate) | A commercial property loan |
| **Certainty of value** | How much cash will it raise, and how sure are we? | Short-dated government bond | A thinly traded corporate bond |
| **Depth of market** | Can a large amount be sold without moving the price? | Australian Government Securities | A single unrated security |

APS 210 captures these ideas in its conditions for high-quality liquid assets: for example, securities must be "traded in large, deep and active repo or cash markets characterised by a low level of concentration" and have a "proven record as a reliable source of liquidity in the markets (repo or sale) even during stressed market conditions" (Att A para 9(c)(ii) and (iii)). A **repo** (repurchase agreement) is a transaction where one party sells a security for cash and agrees to buy it back later at a set price; it is a form of secured borrowing. Chapter 4 explains repos step by step with numbers.

### Encumbered versus unencumbered

An asset is **encumbered** when it has been pledged or otherwise committed so that it is not free to be sold or used. To **pledge** is to hand over an asset as security for an obligation. **Collateral** is an asset pledged to secure a debt or a trade. An **unencumbered** asset is free of such claims.

Only unencumbered assets count as liquidity buffer. APS 210 requires "a cushion of unencumbered liquid assets" (APS 210 para 26), and the LCR is defined as a ratio of the stock of unencumbered HQLA (Att A para 1 and APS 210 para 55). If Example Bank has already lent its A$12.0bn of government bonds out as collateral, it cannot use them a second time.

> **Example:** Example Bank's A$12.0bn of government and semi-government securities is a liquid asset only while unencumbered. If A$4.0bn is pledged to a lender, then only A$8.0bn is free, and the bank's liquid buffer is A$5.0bn + A$8.0bn = A$13.0bn, not A$17.0bn.

### Monetise: sell or repo

To **monetise** an asset means to turn it into cash without waiting for it to mature. There are two main ways.

1. **Sell it outright.** Fast, but the bank loses the asset, and in a market under stress the price may be poor.
2. **Repo it.** Borrow against it. The bank keeps ownership economically and gets the asset back when the loan is repaid. A central bank will often lend against suitable collateral when private lenders will not. The lender applies a **haircut**, a percentage cut from the asset's market value to determine how much it will lend, to protect itself against price falls.

In the LCR, a **haircut** is also the percentage subtracted from the market value of an asset when counting it towards HQLA (for example, 15% for HQLA2A, Att A para 10).

> **Why it matters:** The best liquid assets can be monetised in both ways, with little haircut, in every market condition. The worst can be monetised only by selling at a discount, or not at all.

## Sources and uses of cash in a bank

A bank is a machine for moving cash. Looking at its cash flows over different time scales shows what liquidity management has to cover.

### Over a day

| Sources of cash | Uses of cash |
|---|---|
| Deposits received, card and payment inflows | Withdrawals and payments out |
| Loan repayments received | New loans drawn down |
| Maturing assets, such as short-term bank placements | Debts maturing |
| Sales or repos of securities | Margin calls and collateral posted |
| Newly raised wholesale funding | Payments to other banks through the settlement system |

Within a single day the timing matters. A bank may have to send large payments in the morning, before large payments arrive in the afternoon. This is **intraday liquidity** (covered in Chapter 9; see also APS 210 para 41).

### Over a month

The 30-day horizon is where the LCR operates. Over a month the main flows are maturing wholesale debt, deposit withdrawals, drawdowns of undrawn credit lines and the bank's own loan repayments from customers. An **undrawn committed facility** is a promise to lend that the customer has not yet used.

### Over a year

Over a year the question is whether the bank's funding is stable enough to support its lending. Long-term wholesale debt must be refinanced as it matures. Deposits that look stable must stay stable. Loan growth must be matched by funding growth. This is the NSFR horizon.

### Example Bank, 30-day view

Using the 30-day figures in the shared example: the bank expects outflows of A$13.45bn under stress and inflows (after the cap) of A$1.90bn, a net outflow of A$11.55bn, against A$17.0bn of liquid assets. Chapter 5 builds this up line by line.

## Stress: idiosyncratic, market-wide and combined

A **stress scenario** is a hypothetical but plausible set of adverse events used to test whether a bank can survive. A **stress test** is the exercise of working out what the scenario would do to the bank's cash flows and liquid assets. APS 210 para 26 requires a liquidity risk management framework that withstands stress events "including those involving the loss or impairment of both unsecured and secured funding sources", and adds that "the source of liquidity stress could be specific to the ADI or market-wide or a combination of the two".

| Stress type | What happens | Typical effects |
|---|---|---|
| **Idiosyncratic** (name-specific) | Trouble affects this bank only, for example a rating downgrade, a large fraud, a governance scandal | Wholesale lenders stop rolling over debt; some depositors leave; collateral demands rise; the market is otherwise normal, so assets can still be sold |
| **Market-wide** | Trouble hits the whole financial system, for example a funding market freeze or a sharp rate shock | Funding is hard to raise for every bank; asset prices fall; assets become hard to sell |
| **Combined** | Both at once | The worst case: the bank is shunned and the market is shut |

The LCR scenario in APS 210 is a combined scenario: it assumes bank-specific outflows and general market effects together (Att A para 1 describes "a severe liquidity stress scenario"). Chapter 5 sets out the exact parameters. Internal stress tests by the bank (APS 210 paras 62 to 66) go further, using several scenarios of different lengths. See Chapter 9.

## The two Basel ratios on one page

Both ratios come from the Basel Committee (see Chapter 2). They answer different questions.

| | **Liquidity Coverage Ratio (LCR)** | **Net Stable Funding Ratio (NSFR)** |
|---|---|---|
| **Question** | Could the bank survive 30 days of severe stress? | Is the bank funded soundly over a one-year horizon? |
| **Idea** | Hold enough high-quality liquid assets to pay the net cash that leaves in a month of stress | Fund long-term assets with stable, long-term funding |
| **Formula** | Stock of HQLA divided by total net cash outflows over the next 30 calendar days (Att A para 3) | Available stable funding divided by required stable funding (Att C paras 1 to 4) |
| **Minimum (locally incorporated ADI)** | 100% on an Australian dollar basis and on an all currencies basis (APS 210 para 55(a)) | 100% at all times (APS 210 para 60) |
| **Example Bank** | 17.0 / 11.55 = 147.2% | 79.75 / 58.50 = 136.3% |
| **Time scale** | Short term: one month | Structural: one year |
| **Detail** | Chapter 5 | Chapter 6 |

```
LCR  = Stock of HQLA / Total net cash outflows over the next 30 calendar days

NSFR = Available stable funding (ASF) / Required stable funding (RSF)
```

**HQLA** means high-quality liquid assets: the assets that count towards the LCR. **Available stable funding (ASF)** is the part of a bank's capital and liabilities likely to be reliable over one year. **Required stable funding (RSF)** is the amount of stable funding a bank's assets and off-balance sheet exposures require. Both are defined properly in Chapters 5 and 6.

Smaller or less complex locally incorporated ADIs may instead be classified as **Minimum Liquidity Holdings (MLH) ADIs**, which must hold 9% of liabilities in specified liquid assets (APS 210 para 57). That regime is Chapter 7.

> **Watch out:** The two ratios are complements. An LCR of 147% says nothing about whether long-dated assets are funded with stable money, and an NSFR of 136% says nothing about whether the bank can survive a 30-day panic. Regulators require both.

## A short history

The dates below are widely documented. Where they are outside APS 210 they are given as generally understood and should be checked against official sources.

| Period | Event | Liquidity lesson |
|---|---|---|
| 2007 | Funding markets for short-term bank debt and securitised assets start to seize up in the United States and Europe. In the United Kingdom, Northern Rock suffers a retail run in September 2007 after it cannot roll over its wholesale funding. | A bank dependent on short-term wholesale funding can fail even if its loans are performing. |
| 2008 | Investment banks Bear Stearns (March) and Lehman Brothers (September) collapse or are rescued. Interbank markets freeze. Governments and central banks provide emergency support. | Market-wide stress disables even large, well-regarded institutions. Asset prices that were assumed to be stable fell sharply. |
| 2008 to 2009 | Australian banks, though not failing, found offshore wholesale funding hard to raise. The Australian Government introduced guarantees of deposits and wholesale funding in October 2008, and later set the Financial Claims Scheme as a permanent arrangement (Treasury describes the A$250,000 cap as effective from 1 February 2012). | Even sound banks depend on markets being open. Wholesale funding is a vulnerability. |
| 2010 | The Basel Committee published Basel III, a package of reforms raising capital standards and introducing global liquidity standards. | Liquidity regulation became international and quantitative. |
| 2013 onwards | The Basel Committee finalised the LCR (revised January 2013) and the NSFR (published October 2014). | Two standardised measures. |
| 2014 to 2018 | APRA's revised APS 210 took effect in 2014. As APRA's post-implementation review states, the LCR became effective in 2015 and the NSFR in 2018. | Australia adopted the global standards, with local adaptations (Chapter 2). |
| March 2023 | Silicon Valley Bank (US) failed on 10 March after depositors, many of them uninsured corporate and venture-capital clients, withdrew very large amounts within about a day. Signature Bank followed. Credit Suisse, under pressure, was taken over by UBS with Swiss authorities' support. | Run speed is much faster in the age of mobile banking and social media; concentrated, uninsured depositors can leave in hours; unrealised losses on securities can destroy confidence. |

Detail on the 2023 events (exact amounts withdrawn, exact dates of announcements) is not given here. The point to take is the speed: the older picture of a run as a queue outside a branch no longer describes the risk. A depositor can move money with a phone, and information spreads in minutes. This is one reason APS 210 para 50 requires a retail run contingency plan that does not rely on "closing distribution channels" (APS 210 para 50) and why Chapter 9 treats the plan seriously.

> **Why it matters:** For anyone building a Treasury dashboard, the lesson of 2023 is that the numbers have to be fresh. Daily is the minimum; intraday monitoring of the largest deposits and payment flows is the direction of travel.

## What can go wrong: common misunderstandings

- **"If a bank is profitable, it is safe."** No. Profit says nothing about whether cash is available on a given day.
- **"If a bank holds a lot of securities, it has plenty of liquidity."** Only if they can be turned into cash, are not pledged, and keep their value in stress.
- **"The central bank will always lend."** The RBA's emergency lending is a last resort with conditions, and APRA expects banks to have their own buffers (APS 210 para 70 and para 26).
- **"A run needs a queue."** Modern runs are digital and fast.
- **"More liquidity is always better."** Liquid assets earn lower returns than loans. Chapter 9 explains the cost and why a buffer above 100% is a deliberate choice (Att A para 4).

## Key points

- A bank takes deposits (liabilities) and makes loans (assets); it earns the net interest margin between them.
- Maturity transformation, borrowing short and lending long, is the core product and the core source of liquidity risk.
- Liquidity (cash on time), solvency (assets above liabilities), capital (loss cushion) and profitability (income) are four different things; a bank can fail from illiquidity while solvent and profitable.
- APS 210 para 20 defines funding liquidity risk (unable to meet obligations as they fall due) and market liquidity risk (market liquidity reduces significantly); each can trigger the other.
- Runs are driven by confidence; wholesale funders move faster than insured retail depositors; contagion spreads stress between banks.
- Deposit insurance (the Financial Claims Scheme, A$250,000 per account holder per ADI) and the lender of last resort (the RBA) are backstops, not substitutes for a bank's own buffer.
- An asset is liquid if it is fast to sell, certain in value and traded in a deep market; only unencumbered assets count.
- To monetise an asset is to sell it or repo it.
- The LCR tests survival over 30 days of combined stress; the NSFR tests whether one-year funding is stable enough. Example Bank has an LCR of 147.2% and an NSFR of 136.3%.
- The 2007 to 2009 crisis showed the danger of wholesale funding freezes, Basel III responded with the two ratios, and the 2023 failures showed how fast a modern run can be.

## Check your understanding

**1. Explain why a deposit is a liability of the bank but an asset of the customer, and say which of Example Bank's balance sheet lines are the bank's biggest asset and biggest group of funding.**

**Answer:** The bank owes the money back, so for the bank it is a liability; the customer is owed it, so for the customer it is an asset. Example Bank's biggest asset is residential mortgages (A$50.0bn). Its biggest group of funding is customer deposits of A$65.0bn (A$25.0 + 15.0 + 10.0 + 5.0 + 4.0 + 6.0), or A$69.0bn including financial institution deposits.

**2. A bank has assets of A$100bn, liabilities of A$92bn, and profits well above target. Can it still fail? Explain.**

**Answer:** Yes. It is solvent (assets exceed liabilities by A$8bn) and profitable, but if its liabilities are short-term and its assets long-term, a loss of funding can leave it unable to pay in cash as obligations fall due. That is a liquidity failure. If it is forced to sell assets at a discount, it may become insolvent as well.

**3. Calculate Example Bank's loan-to-deposit ratio, and say what it suggests about maturity transformation.**

**Answer:** Customer loans A$73.0bn divided by customer deposits A$65.0bn = 112.3%. Loans exceed customer deposits, so the gap (A$8.0bn) is funded by wholesale debt and other sources. Combined with the fact that most deposits are at call while most loans are long, the bank is doing material maturity transformation.

**4. Distinguish funding liquidity risk from market liquidity risk and describe one way each can cause the other.**

**Answer:** Funding liquidity risk (APS 210 para 20) is the risk of being unable to meet obligations as they fall due; market liquidity risk is the risk that financial markets lose liquidity. Funding trouble forces sales into a thin market, which depresses prices (funding causes market). A market freeze reduces the cash that can be raised from selling or repoing assets, deepening the funding gap (market causes funding).

**5. Example Bank's A$12.0bn government and semi-government securities include A$4.0bn pledged as collateral. What is its liquid buffer from cash and these securities, and why?**

**Answer:** A$5.0bn + (A$12.0bn - A$4.0bn) = A$13.0bn. Pledged securities are encumbered and cannot be used again; only unencumbered assets count (APS 210 para 26; Att A para 1).

**6. Using Example Bank's figures, suppose the LCR is 147.2% with HQLA of A$17.0bn and net cash outflows of A$11.55bn. If HQLA falls to A$14.0bn and net outflows are unchanged, what is the LCR, and is it still above the minimum?**

**Answer:** 14.0 / 11.55 = 121.2%. It remains above the 100% minimum for a locally incorporated ADI (APS 210 para 55(a)), but the surplus over 100% falls from A$5.45bn (17.0 - 11.55) to A$2.45bn (14.0 - 11.55).

**7. Why is a wholesale run usually faster than a retail run, and which Example Bank balance sheet items would a wholesale run affect first?**

**Answer:** Wholesale funders are professional, well informed, hold large uninsured balances and can decide in hours not to roll over. Retail depositors are numerous, often insured and slower. Example Bank's wholesale debt maturing within 30 days (A$1.0bn) and financial institution deposits (A$4.0bn) would be hit first; the LCR assumes 100% of both leave (A$5.0bn in total).

**8. In one sentence each, say what the LCR and NSFR test, and name the horizon of each.**

**Answer:** The LCR tests whether enough high-quality liquid assets are held to cover net cash outflows over a 30 calendar day severe stress (Att A para 3). The NSFR tests whether available stable funding covers the stable funding required by the bank's assets and commitments over a one-year horizon (Att C paras 1 to 4).

---

# Chapter 2: Who regulates Australian banks, and the rulebook

## The regulators and what each does

Several public bodies touch a bank's liquidity. Knowing which one does what tells you whom a rule comes from, who checks it, and who steps in during a crisis.

| Body | Full name | Main role relevant to banks |
|---|---|---|
| **APRA** | Australian Prudential Regulation Authority | The **prudential regulator**: it licenses ADIs, writes binding prudential standards, supervises banks for safety and soundness, and runs the Financial Claims Scheme when activated. APS 210 is APRA's standard. |
| **RBA** | Reserve Bank of Australia | The **central bank**: sets monetary policy (the cash rate), provides settlement accounts and market operations to banks, oversees payment systems and acts as lender of last resort. |
| **ASIC** | Australian Securities and Investments Commission | The **conduct and markets regulator**: oversees how financial firms treat consumers and investors, market integrity and company disclosure. It does not set liquidity minimums. |
| **Treasury** | The Australian Government Treasury (the government department) | Advises the Treasurer and government on policy and legislation, including the Banking Act and the legal framework for deposit protection. It is a policy department, not a supervisor. Do not confuse it with "Treasury" the bank function (Chapter 9). |
| **CFR** | Council of Financial Regulators | A **coordinating body**, not a regulator. As generally understood, its members are the RBA (which chairs it), APRA, ASIC and Treasury. It shares information and coordinates on financial stability, including crisis response. |
| **AUSTRAC** | Australian Transaction Reports and Analysis Centre | Regulates anti-money-laundering and counter-terrorism financing obligations. It has no role in liquidity rules. |

A **prudential regulator** supervises the safety and soundness of institutions, so that they can keep their promises to depositors. A **conduct regulator** supervises how firms deal with customers and markets.

### The "twin peaks" model

Australia is often described as using a "twin peaks" model of financial regulation, adopted after the Wallis Inquiry of 1997 (as generally understood): one peak for prudential regulation (APRA) and one for conduct and market integrity (ASIC), with the RBA responsible for monetary policy and financial system stability. For liquidity, the two key bodies are APRA, which sets and enforces the minimums, and the RBA, which provides the settlement and lending infrastructure behind them.

> **Why it matters:** If you meet a liquidity rule in a Treasury report, it nearly always traces to APRA. If it concerns what the bank may borrow from the central bank, or how payments settle, it traces to the RBA.

## The Banking Act 1959 and what an ADI is

The **Banking Act 1959** is the federal law under which banking is regulated in Australia. It makes it an offence to carry on banking business without authority and empowers APRA to authorise institutions and to make prudential standards. APS 210 states that it "is made under section 11AF of the Banking Act 1959" (APS 210 para 1).

An **authorised deposit-taking institution (ADI)** is a body that APRA has authorised under the Banking Act to take deposits. ADIs include:

- banks (large domestic groups, smaller domestic banks, and branches or subsidiaries of foreign banks);
- building societies; and
- credit unions.

"ADI" is a legal term. All banks are ADIs, but some ADIs are not called banks. Standards such as APS 210 apply to "all authorised deposit-taking institutions (ADIs)" (APS 210 para 2).

### Authorised NOHC

An **authorised non-operating holding company (authorised NOHC)** is a holding company, approved by APRA, that sits at the top of a group containing an ADI but does not carry on banking itself. APS 210 para 4(b) says that if an ADI is a subsidiary of an authorised NOHC, the NOHC "must ensure that the requirements in this Prudential Standard are met on a Level 2 basis, where applicable".

### Foreign ADI: branch versus subsidiary

| Feature | Foreign ADI (a branch) | Locally incorporated ADI (including a subsidiary of a foreign bank) |
|---|---|---|
| **Legal form** | Branch of a bank incorporated overseas; part of the same legal entity as the foreign head office | A separate company incorporated in Australia |
| **Capital and Board** | Supported by the head office; APS 210 says the Board's responsibilities are "to be fulfilled by the senior officer outside Australia" (APS 210 para 15) | Has its own capital and its own Board |
| **LCR minimum** | 40% on an all currencies basis (APS 210 para 55(b)) | 100% on both an Australian dollar basis and an all currencies basis (APS 210 para 55(a)) |
| **NSFR** | Not applicable: the NSFR applies to "a locally incorporated ADI classified as an LCR ADI" (APS 210 para 59) | At least 100% at all times if an LCR ADI (APS 210 para 60) |
| **Extra requirement** | Local operational capacity assessment at least annually (APS 210 paras 67 to 69) | Not required |

> **Watch out:** "Foreign ADI" and "foreign-owned bank" are different things. A foreign-owned bank that is incorporated in Australia is a locally incorporated ADI and gets the full 100% tests. Only a branch is a foreign ADI. Chapter 10 compares these terms.

## Prudential standards and prudential practice guides

APRA writes two kinds of document, and the difference matters.

| | **Prudential standard** | **Prudential practice guide (PPG)** |
|---|---|---|
| **Status** | Legally binding. A breach is a breach of the law. | Guidance. It explains APRA's view of sound practice; it does not add binding rules. |
| **Naming** | **APS** = standards for ADIs. **CPS** = cross-industry standards, applying across ADIs, insurers and superannuation entities. | **APG** = guide for ADIs. **CPG** = cross-industry guide. |
| **Language** | "must", "is required to" | "should", "APRA expects", "would typically" |
| **Example** | APS 210 Liquidity | APG 210 Liquidity |

So **APS 210** is the binding standard on liquidity, and **APG 210** is the guide that explains how APRA expects it to be applied. APG 210 is where practical points (for example which Australian dollar assets APRA has recognised as HQLA) are often set out. This guide uses APS 210 as the source for rules, and flags points that depend on APG 210 or other guidance as outside the standard.

### How a standard is made: section 11AF

Under subsection 11AF(1) of the Banking Act, APRA may determine prudential standards by written instrument. The instrument that made the current APS 210 is Banking (prudential standard) determination No. 3 of 2025. In it, APRA's delegate revoked the earlier determination (No. 13 of 2022) under subsection 11AF(3) and determined the new standard under subsection 11AF(1). The instrument records that it commences on 1 July 2025 and was dated 13 April 2025. The standard also states that it commences on 1 July 2025 (APS 210 para 6). Subsection 11AF(2) lets APRA adjust or exclude requirements for a particular ADI or authorised NOHC (see footnote 1 to APS 210 para 71). Before finalising a standard, APRA normally consults the industry on a draft (as generally understood; the consultation steps are APRA's practice rather than something APS 210 itself states).

> **In the standard:** "Where this Prudential Standard provides for APRA to exercise a power or discretion, this power or discretion is to be exercised in writing." (APS 210 para 8). So a higher minimum LCR, for example, must be imposed in writing.

## The standards that touch liquidity

Titles below are the titles used in APS 210 itself where APS 210 cites them, and otherwise the titles as generally understood at the time of writing, which you should check on apra.gov.au before quoting.

| Standard | Title | What it covers, in one line |
|---|---|---|
| **APS 210** | Liquidity | Liquidity risk management; the LCR, the MLH regime and the NSFR (this guide, Chapters 5 to 9). |
| **APG 210** | Liquidity (guide) | APRA's non-binding guidance on how to apply APS 210. |
| **APS 110** | Capital Adequacy | The overall capital framework: the minimum amount of capital an ADI must hold. |
| **APS 111** | Capital Adequacy: Measurement of Capital | What counts as capital (CET1, Additional Tier 1, Tier 2). |
| **APS 112** | Capital Adequacy: Standardised Approach to Credit Risk | Risk weights for credit exposures. APS 210 uses its risk weights to decide which securities qualify as HQLA1 and HQLA2A (Att A paras 9(c)(i) and 10(a)(i)). |
| **APS 113** | Capital Adequacy: Internal Ratings-based Approach to Credit Risk | Advanced approach to credit risk for approved banks. APS 210 refers to it for internal ratings of corporate debt (Att A para 10(b)(iii)). |
| **APS 120** | Securitisation | Rules for securitisation and capital relief. APS 210 para 5 links to it (see below). |
| **APS 220** | Credit Risk Management | How an ADI manages credit risk, a risk that feeds liquidity risk. |
| **APS 330** | Public Disclosure | What an ADI must publish, including disclosure of its liquidity ratios (as generally understood). |
| **CPS 220** | Risk Management | Overall risk management framework. APS 210 para 35 requires the liquidity framework to be reviewed as part of the CPS 220 review. |
| **CPS 190** | Recovery and Exit Planning | Plans for recovery and orderly exit. Earlier drafts called it "Financial Contingency Planning"; APRA's website gives its final title as Recovery and Exit Planning, applying to ADIs from 1 January 2024. |
| **CPS 230** | Operational Risk Management | Operational risk, including critical operations and service providers. As generally understood it commenced on 1 July 2025. Not cited in APS 210. |
| **CPS 001** | Defined Terms | Shared definitions. Terms in bold in APS 210 are defined there (APS 210 para 7). |

> **Why it matters:** Liquidity is never alone. A deteriorating loan book (APS 220) lowers confidence, which raises run-off. An operational failure (CPS 230) can stop payments, which is a liquidity problem. A recovery plan (CPS 190) lists the liquidity actions a bank would take in a crisis. When you read a bank's liquidity report, remember that it sits inside a web of obligations.

## Basel Committee, Basel III and how APRA adapts it

The **Basel Committee on Banking Supervision** is an international committee of bank regulators and central banks, based at the Bank for International Settlements (BIS) in Basel, Switzerland. It sets global minimum standards but has no legal power: each country writes its own rules. **Basel III** is the package of reforms issued after the global financial crisis, covering higher and better-quality capital, a leverage ratio and, for the first time, two global liquidity standards: the LCR and the NSFR.

APRA implements Basel standards through its own binding prudential standards. APS 210 is the Australian version of the Basel liquidity standards. APRA's post-implementation review states that the LCR became effective in Australia in 2015 and the NSFR in 2018, and that the Basel Committee assessed APS 210 as compliant with Basel III.

Some differences in the Australian approach:

- **Australian dollar LCR.** A locally incorporated ADI must meet 100% on both an Australian dollar basis and an all-currencies basis (APS 210 para 55(a)).
- **Minimum Liquidity Holdings.** A simpler regime for smaller ADIs (APS 210 para 57; Chapter 7).
- **Foreign ADI branches** have a lower 40% minimum (APS 210 para 55(b)) and a local operational capacity test (paras 67 to 69).
- **Recognition of assets.** HQLA2A and HQLA2B assets must have been "recognised by APRA or the relevant prudential regulator" (Att A paras 10 and 12).
- **The Committed Liquidity Facility (CLF)**, an Australian solution to a shortage of government bonds (see the RBA section below).

## The structure of APS 210

APS 210 has a main body and three attachments.

| Part | Paragraphs | Content | Chapter |
|---|---|---|---|
| Objectives and key requirements | (front page) | Three requirements: a risk management framework; a portfolio of liquid assets sufficient to withstand a severe liquidity stress; a robust funding structure | 2 |
| Authority, application, interpretation, definitions | 1 to 10 | Source of power; Level 1 and Level 2; securitisation carve-out; definitions of associated entity and financial institution | 2 |
| Key principles | 11 to 14 | Sound management; sufficient liquidity at all times; stable funding; inform APRA | 2, 8 |
| Board and senior management responsibilities | 15 to 20 | Board, senior management, funding and market liquidity | 8 |
| Liquidity risk management framework | 21 to 35 | Risk tolerance, strategy, independent oversight | 8, 9 |
| Management of liquidity risk | 36 to 43 | Cash flows, limits, collateral, early warnings, MIS, intraday, cost allocation, currencies | 8, 9 |
| Funding strategy | 44 to 46 | Three-year strategy | 8, 9 |
| Contingency funding plan | 47 to 51 | Plan, retail run, annual test | 8, 9 |
| Classification of ADIs | 52 to 54 | LCR ADIs and MLH ADIs | 2, 7 |
| LCR ADIs | 55 to 56 | Minimums and higher minimums | 5 |
| MLH ADIs | 57 to 58 | 9% of liabilities | 7 |
| NSFR | 59 to 61 | 100% at all times | 6 |
| Stress testing | 62 to 66 | Scenarios, Board and APRA reporting | 8, 9 |
| Local operational capacity | 67 to 69 | Foreign ADIs | 8 |
| Exceptional Liquidity Assistance | 70 | RBA assistance | 2, 8 |
| Adjustments; previous discretion | 71 to 72 | APRA's powers | 2, 8 |
| Attachment A | Att A paras 1 onward | Liquidity coverage ratio | 5 |
| Attachment B | Att B | Minimum liquidity holdings | 7 |
| Attachment C | Att C | Net stable funding ratio | 6 |

### Objectives

The standard "requires an authorised deposit-taking institution to adopt prudent practices in managing its liquidity risks and to maintain an adequate level of liquidity to meet its obligations as they fall due across a wide range of operating circumstances" (APS 210, objectives). The three key requirements are risk management, a portfolio of liquid assets, and a robust funding structure.

### Key principles (paras 11 to 14)

| Para | Principle |
|---|---|
| 11 | The ADI is responsible for sound management of liquidity risk and must have a robust framework. |
| 12 | It must at all times maintain sufficient liquidity to meet its obligations as they fall due and hold a minimum level of liquid assets to survive a severe liquidity stress. |
| 13 | Activities must be funded with stable sources of funding on an ongoing basis. |
| 14 | It must inform APRA "as soon as possible" of any concerns about current or future liquidity, and its plans to address them. If it experiences a severe liquidity stress, it must notify APRA "immediately" and advise the action being taken. |

Paragraph 12 is the basis for the LCR and MLH; paragraph 13 is the basis for the NSFR; paragraph 14 is the notification duty.

### Classification: LCR ADI or MLH ADI (paras 52 to 54)

| Case | Rule |
|---|---|
| Locally incorporated ADI | "APRA will determine" whether it is an LCR ADI or an MLH ADI (APS 210 para 52). |
| Foreign ADI | An LCR ADI "unless APRA determines" it is an MLH ADI; APRA considers size and complexity with respect to liquidity risk (APS 210 para 53). |
| Timing | An ADI must meet the minimums for its classification "on a continuous basis, absent a situation of financial stress" (APS 210 para 54). |

### The three quantitative requirements (paras 55 to 61)

| Requirement | Who | Minimum | Reference |
|---|---|---|---|
| LCR | Locally incorporated LCR ADI | 100% on an Australian dollar (AUD) basis and 100% on an all currencies basis | APS 210 para 55(a) |
| LCR | Foreign ADI that is an LCR ADI | 40% on an all currencies basis | APS 210 para 55(b) |
| MLH | MLH ADI | 9% of liabilities in specified liquid assets | APS 210 para 57 |
| NSFR | Locally incorporated LCR ADI | 100% at all times | APS 210 paras 59 to 60 |

## Level 1 versus Level 2

APS 210 para 3 says a reference to an ADI is a reference to "(a) an ADI on a Level 1 basis; and (b) a group of which an ADI is a member on a Level 2 basis".

| | Level 1 | Level 2 |
|---|---|---|
| **Scope** | The ADI itself (the licensed legal entity), including its overseas branches | The consolidated group: the ADI plus its subsidiaries |
| **Who ensures compliance** | The ADI | The ADI if it is the group's holding company, or the authorised NOHC if the ADI is its subsidiary (APS 210 para 4) |

The requirement is met on both bases where applicable. A group could have enough liquidity in aggregate but with the cash stuck in a subsidiary; the Level 1 test catches the opposite problem. Chapter 8 covers the governance consequences (see APS 210 para 25, which requires the framework to set out the organisational structure on a Level 1 and Level 2 basis).

### The securitisation carve-out (para 5)

A **securitisation** is a transaction in which loans (for example mortgages) are pooled and sold to a **special purpose vehicle (SPV)**, a legal entity created for the transaction, which funds itself by issuing securities backed by the loans. The **originator** is the ADI that created the loans. APS 210 para 5 provides that where the originating ADI meets the operational requirements for regulatory capital relief under APS 120, it "may exclude the assets and liabilities of the relevant special purpose vehicles (SPVs) from the calculation of its minimum liquidity holdings (MLH) and net stable funding ratio (NSFR)". But for the LCR it "must include the cash flows from the assets and liabilities of SPVs related to the ADI's securitisation activities".

> **Watch out:** The carve-out is asymmetrical. For NSFR and MLH, the SPV can be left out; for LCR it cannot. A data model that drops SPV entities everywhere will produce wrong LCR inputs.

## APRA's powers under the standard

| Power | Paragraph | Effect |
|---|---|---|
| Higher minimum LCR | 56 | If APRA has concerns about the ADI's liquidity risk profile or the quality of its liquidity risk management. |
| Higher minimum MLH | 58 | Same concerns, for MLH ADIs. |
| Higher minimum NSFR | 61 | Where APRA considers it appropriate, including concerns about funding or liquidity risk profile or risk management. |
| Classification | 52 and 53 | Decides LCR ADI or MLH ADI. |
| Adjustments and exclusions | 71 | APRA "may adjust or exclude a specific requirement" for an ADI or authorised NOHC. |
| Additional requirements for foreign ADIs | 69 | If a local operational capacity assessment shows problems. |
| Information from ADIs | 70 | Any information requested by APRA or the RBA in an ELA request. |
| Funding strategy | 44(a) | The three-year strategy "must be provided to APRA on request". |

These powers must be exercised in writing (APS 210 para 8).

### Notification duties (para 14, Att A para 5, para 70)

- Inform APRA as soon as possible of concerns about the liquidity position (APS 210 para 14).
- Notify APRA immediately of a severe liquidity stress (APS 210 para 14).
- Inform APRA immediately of an actual breach of the LCR requirement, or if circumstances may result in a breach (Att A para 5).
- Before requesting ELA from the RBA, notify APRA immediately (APS 210 para 70).
- Advise APRA of any material changes to the funding strategy (APS 210 para 46).
- Contact APRA before relying on a previous exemption or discretion given under an earlier version of the standard (APS 210 para 72).

## The Financial Claims Scheme

The **Financial Claims Scheme (FCS)** is the Australian Government's depositor protection arrangement, administered by APRA. As published on apra.gov.au, if an ADI fails and the scheme is activated, it covers deposits up to A$250,000 per account holder per ADI, with balances at the same ADI added together. It covers accounts such as transaction, savings and term deposits (APRA lists mortgage offset accounts too), and, as APRA states, applies to Australian dollar accounts only. APRA says it will endeavour to pay within seven calendar days of activation. Treasury describes the scheme as arising from the 2008 financial crisis, with the A$250,000 cap in place from 1 February 2012.

### Why it matters for run-off

Insured depositors have less reason to run. That is why the LCR rates differ by deposit type. The scorecard for less stable retail deposits in Att A para 40 uses a threshold of A$250,000 as part of deciding whether a deposit is stable or less stable (Chapter 5 sets out the scorecard). A deposit above the limit is uninsured, so the depositor has an incentive to leave early.

In Example Bank, the A$25.0bn of stable retail deposits runs off at 5% (A$1.25bn), while the A$15.0bn of less stable retail runs off at 10% (A$1.50bn). The corporate and financial-institution deposits are largely uninsured and have higher rates (corporate non-operational 40%; financial institutions 100%).

> **Watch out:** The FCS limit is per account holder per ADI, not per account. A customer with three accounts totalling A$300,000 at one ADI is covered up to A$250,000 in total. Data models should aggregate by customer, not by account, if they want to estimate insured balances.

## The RBA's role

The RBA matters to liquidity in four ways. The descriptions below are of the RBA's arrangements as generally understood and should be checked on rba.gov.au before use in a formal document.

### Exchange Settlement Accounts

An **Exchange Settlement Account (ESA)** is an account that a bank holds with the RBA. Banks use ESAs to settle payments among themselves: when Bank A pays Bank B, the RBA debits A's ESA and credits B's. Balances in ESAs are claims on the central bank, so they count as "central bank balances" in HQLA1, "to the extent that these balances may be drawn down in times of stress" (Att A para 9(b)). Example Bank's A$5.0bn of "cash and balances with the RBA" combines notes and coin with its ESA balance.

### Open market operations and the cash rate

The **cash rate** is the interest rate on unsecured overnight loans between banks. The RBA sets a target for it as part of monetary policy. To keep the actual rate close to the target, the RBA conducts **open market operations**: buying and selling securities, and lending against them under repo, to adjust the supply of ESA balances. As generally understood, the RBA also pays interest on ESA balances and lends overnight on request against eligible collateral, which acts as a ceiling and floor around the target. Treat the exact corridor settings as outside this guide and check the RBA's website.

### Standing facilities

A **standing facility** is a lending or deposit arrangement a central bank offers on a continuing basis. The RBA's standing facility, as generally understood, is the ability for banks to borrow overnight against eligible securities (repo). That makes high-quality securities such as government bonds valuable because they can be repoed with the RBA. The exact eligible collateral list and pricing should be checked on rba.gov.au.

### Exceptional Liquidity Assistance

**Exceptional Liquidity Assistance (ELA)** is emergency lending by the RBA to an ADI in severe liquidity stress. APS 210 para 70 says an ADI under severe stress "may request" ELA from the RBA, must "notify APRA immediately of the ADI's liquidity concerns and its intention to request ELA" before approaching the RBA, must provide information requested by APRA or the RBA, and must "have the operational capability to provide information along with its application for ELA or within other timeframes specified by APRA".

> **Watch out:** ELA is not a planning assumption. It is not an HQLA or a funding source in the LCR or NSFR. A bank with a liquidity plan that depends on ELA has no plan.

### The Committed Liquidity Facility

Australia has a small government bond market relative to the size of its banks. When the LCR was introduced, there were not enough HQLA for all banks to hold. The solution was the **Committed Liquidity Facility (CLF)**: a contractual commitment by the RBA, for a fee, to repo certain securities (including bank-issued and securitised assets that were not HQLA) for cash, which APS 210 allowed banks to count towards the LCR. The standard still describes the CLF (Att A paras 13 to 21), and Att A para 5 refers to drawing on it in stress.

APRA and the RBA phased the facility down as the supply of government bonds grew in the pandemic years. The RBA states that the aggregate CLF was reduced to zero as at 1 January 2023, as scheduled in 2022 reductions, and APRA has said it remains available for reactivation if HQLA shortfalls arise. So as at the date of this guide the CLF can be thought of as still in the standard but with zero allocations. Chapter 5 explains the CLF rules.

### The Term Funding Facility

The **Term Funding Facility (TFF)** was a pandemic-era RBA scheme, announced in March 2020 (as generally understood), that offered banks three-year funding at a very low fixed rate. The RBA states that it closed to new drawdowns on 30 June 2021, with A$188 billion drawn of the A$213 billion available, and that the last borrowings matured in mid-2024. It was a monetary policy and funding-support measure, not an LCR instrument. For a Treasury data migration the TFF matters mainly because it created a large block of maturing wholesale-like funding in 2023 and 2024 that banks had to replace.

## Reporting to APRA and public disclosure

Two separate flows of information come out of an ADI's liquidity data.

1. **Regulatory reporting to APRA.** Banks submit regular returns containing LCR and NSFR inputs and results, using APRA's reporting standards and forms. This guide does not name form numbers; check apra.gov.au for the current reporting standards. Frequency and submission deadlines are set in those standards (not in APS 210).
2. **Public disclosure.** Under Prudential Standard APS 330 Public Disclosure, as generally understood, ADIs publish information about their liquidity position, including their LCR and NSFR, in a report often called the Pillar 3 report (Pillar 3 is the Basel term for market disclosure). The published tables are explained in Chapter 3.

Two further duties come from APS 210 itself:

- Stress test results and vulnerabilities and any resulting actions "must be reported to, and discussed with, the Board and APRA" (APS 210 para 65).
- The three-year funding strategy "must be provided to APRA on request" (APS 210 para 44(a)).

## What can go wrong: common misunderstandings

- **Confusing the standard with the guide.** A statement in APG 210 is guidance; only the APS binds.
- **Confusing Treasury (the department) with Treasury (the bank function).** They are unrelated.
- **Assuming CLF is currently providing liquidity.** It is in the standard but, as understood, at zero.
- **Treating Level 1 and Level 2 as the same.** A group-wide figure can hide an entity-level shortfall.
- **Assuming the NSFR applies to foreign branches.** It does not (APS 210 para 59).

## Key points

- APRA writes and enforces the liquidity rules; the RBA provides settlement and lender-of-last-resort backstops; ASIC regulates conduct; Treasury advises government; the Council of Financial Regulators coordinates.
- An ADI is an institution authorised under the Banking Act 1959 to take deposits; banks, building societies and credit unions are ADIs.
- A foreign ADI is a branch; a foreign-owned subsidiary is a locally incorporated ADI with the full tests.
- Prudential standards (APS, CPS) are binding; prudential practice guides (APG, CPG) are guidance. APS 210 is made under section 11AF of the Banking Act.
- Locally incorporated LCR ADIs need an LCR of 100% (AUD and all currencies) and an NSFR of 100%; foreign ADIs 40% LCR; MLH ADIs 9% of liabilities (APS 210 paras 55, 57, 60).
- APRA may require higher minimums (paras 56, 58, 61), adjust requirements (para 71), and must be notified of liquidity concerns and breaches (para 14, Att A para 5).
- Level 1 is the ADI alone; Level 2 is the group. The SPV carve-out in para 5 excludes SPVs for MLH and NSFR but not LCR.
- The Financial Claims Scheme protects deposits up to A$250,000 per account holder per ADI, which is why insured retail deposits are assumed to be stickier.
- The CLF remains in the standard but allocations have been phased to zero; ELA is emergency assistance that requires immediate notice to APRA (para 70).
- Public disclosure and APRA reporting are separate; form numbers should be taken from apra.gov.au.

## Check your understanding

**1. Which regulator writes APS 210, and which provides Exchange Settlement Accounts?**

**Answer:** APRA writes APS 210 under section 11AF of the Banking Act (APS 210 para 1). The RBA provides Exchange Settlement Accounts.

**2. A foreign bank operates in Australia through a branch, and another through a locally incorporated subsidiary. State the LCR and NSFR minimums for each.**

**Answer:** The branch is a foreign ADI: LCR at least 40% on an all currencies basis (APS 210 para 55(b)); the NSFR does not apply (para 59). The subsidiary is a locally incorporated ADI: LCR at least 100% on both an AUD basis and an all currencies basis (para 55(a)), and NSFR at least 100% if it is an LCR ADI (paras 59 to 60).

**3. What is the difference between APS 210 and APG 210, and why does it matter when you cite a rule?**

**Answer:** APS 210 is a legally binding prudential standard; APG 210 is a practice guide that gives guidance. A "must" should be cited to APS 210; an APG point is APRA's expectation of good practice.

**4. Example Bank's LCR is 147.2%. APRA concludes that its liquidity risk management is weak and requires a higher minimum of 120% for the LCR. Is the bank compliant, and what authority does APRA use?**

**Answer:** Yes: 147.2% exceeds 120%. APRA uses para 56 (higher minimum LCR), in writing (para 8). The bank's HQLA surplus above 120% is 17.0 - (1.20 x 11.55) = 17.0 - 13.86 = A$3.14bn.

**5. A customer has A$180,000 in a savings account and A$120,000 in a term deposit at the same ADI. How much is covered by the Financial Claims Scheme?**

**Answer:** A$250,000. The limit applies per account holder per ADI, so the balances are added together (A$300,000); A$50,000 is not covered.

**6. A securitising ADI meets the APS 120 operational requirements. Which of LCR, NSFR and MLH calculations may exclude the SPV's assets and liabilities?**

**Answer:** NSFR and MLH may exclude them; the LCR must include the SPV's cash flows (APS 210 para 5).

**7. Example Bank's HQLA is A$17.0bn and net cash outflows are A$11.55bn. If APRA required a higher NSFR minimum of 140% and the bank's ASF is A$79.75bn and RSF is A$58.50bn, would it comply?**

**Answer:** NSFR = 79.75 / 58.50 = 136.3%, below 140%, so it would not comply. It would need ASF of 1.40 x 58.50 = A$81.9bn, an increase of A$2.15bn (APRA's power: para 61).

**8. Explain why a bank must notify APRA before it asks the RBA for Exceptional Liquidity Assistance.**

**Answer:** APS 210 para 70 requires an ADI to notify APRA immediately of its liquidity concerns and its intention to request ELA before approaching the RBA. The prudential regulator must know about a severe stress at once, so it can supervise and coordinate with the RBA; ELA is a last resort and is not a normal source of funds.

---

# Chapter 3: How to read a bank balance sheet

A liquidity dashboard is built on balance sheet data. Every number in the Liquidity Coverage Ratio (LCR) and the Net Stable Funding Ratio (NSFR) starts life as a line on a bank's books. This chapter teaches you to read those books. It starts with the accounting equation, walks through a typical Australian bank's balance sheet line by line, explains the valuation ideas you need, covers the off-balance sheet items, the notes, the income statement and the capital ratios, and then applies it all to the fictional Example Bank used throughout this guide.

## 3.1 The accounting equation

A **balance sheet** is a table that lists everything an organisation owns and everything it owes at one moment in time. It is a snapshot, not a movie. It has three parts:

- An **asset** is something the organisation owns or is owed that has value. For a bank, assets are mostly loans it has made and securities it holds.
- A **liability** is something the organisation owes to someone else. For a bank, liabilities are mostly deposits and debt it has issued.
- **Equity** is what is left for the owners after the liabilities are taken away from the assets. It is also called shareholders' equity or net assets.

The three parts are tied together by one identity:

```
Assets = Liabilities + Equity
```

It is an identity, not a target. The two sides always match because equity is defined as the difference. If you are a data professional, treat it as a checksum: total assets must equal total liabilities plus equity on every balance sheet you load. If it does not, a line is missing or mis-signed.

Another way to say the same thing: every asset was paid for by someone. Either a creditor lent the money (a liability) or an owner put it in or left profits in the business (equity). The right-hand side of the balance sheet tells you who funded the assets. The left-hand side tells you what the money was turned into.

> **Why it matters:** Liquidity is a question about the relationship between the two sides. Assets are what a bank can sell or collect to raise cash. Liabilities are what can be demanded back. The LCR compares liquid assets with expected outflows on liabilities over 30 days. The NSFR compares the stability of the right-hand side with the liquidity of the left-hand side over one year (APS 210 Att A para 1; Att C para 1).

### Why a bank's balance sheet looks "backwards" to a customer

When you open a bank account and put A$1,000 into it, you think of that money as yours, an asset. On the bank's balance sheet it is the opposite:

| Event | Your view | The bank's view |
|---|---|---|
| You deposit A$1,000 | You own A$1,000 | The bank owes you A$1,000. It is a **liability** (a deposit). The bank also gets A$1,000 of cash, an **asset**. |
| You borrow A$500,000 for a home | You owe the bank A$500,000 | The bank is owed A$500,000. It is an **asset** (a loan). The bank paid out cash or credited your account. |
| You repay the loan | Your debt falls | The bank's loan asset falls and its cash rises |

So your deposit is the bank's liability and your loan is the bank's asset. This is why a "deposit" is a funding source (liability) and a "loan" is a use of funds (asset).

> **Example:** A bank starts with equity of A$8 only. It takes in A$92 of deposits and debt, so it has A$100 of cash. It lends A$70 as mortgages. Assets are now cash A$30 plus loans A$70 = A$100. Liabilities and equity are A$92 + A$8 = A$100. The identity holds before and after the loan. The only change is the mix of the assets: cash falls from A$100 to A$30 and loans rise from nil to A$70, so the bank is less liquid than before.

## 3.2 A typical Australian bank's statutory balance sheet, line by line

The **statutory balance sheet** is the balance sheet in a bank's audited financial report, prepared under Australian Accounting Standards (issued by the Australian Accounting Standards Board, AASB). Banks do not present "current" and "non-current" items the way a retailer does. They present in **liquidity order**: the assets that are closest to cash come first, and the liabilities that are most likely to be demanded first come first. This is how an experienced reader scans the page: top-down, from most liquid to least liquid.

Line names vary from bank to bank and year to year. What follows is the typical order and the typical content. Treat the names as generic, not as a template from any particular bank.

### 3.2.1 Assets

**Cash and liquid assets** (sometimes "cash and balances with central banks").
- *What it is:* notes and coin, balances held at the Reserve Bank of Australia (RBA) and sometimes very short-term deposits with other banks. Balances at the RBA are held in an Exchange Settlement Account (ESA), the account a bank uses to settle payments with other banks (described in Chapter 2).
- *Valuation:* face amount, since it is already cash.
- *Liquidity rules:* notes and coin and central bank balances (to the extent they can be drawn down in stress) are HQLA1, with no haircut (APS 210 Att A para 9(a), 9(b)). In the NSFR they carry a 0% required stable funding factor (Att C para 29(a), 29(b)). **HQLA1** means the highest quality of high-quality liquid assets; Chapter 5 explains the classes.

**Receivables from financial institutions** (also "due from other banks", "placements with banks").
- *What it is:* money the bank has lent to, or placed with, other banks and financial institutions. It includes unsecured loans, deposits placed, and cash collateral paid.
- *Valuation:* usually amortised cost (see 3.3).
- *Liquidity rules:* it is not HQLA. In the LCR, contractual repayments due within 30 days from banks and central banks count as an inflow at 100% (Att A para 62(a)); inflows from deposits placed at other institutions for operational purposes are 0% (Att A para 63). In the NSFR, loans to financial institutions that are unencumbered and have a residual maturity under six months get 15% (Att C para 33(b)), or 10% if secured against HQLA1 with free rehypothecation (Att C para 31). Loans to financial institutions with a residual maturity of one year or more get 100% (Att C para 37(c)).

**Trading securities** (also "trading assets" or "assets at fair value through profit or loss").
- *What it is:* bonds, bills, shares and other securities the bank holds to trade, or to manage liquidity, rather than to collect interest to maturity.
- *Valuation:* fair value, re-measured every reporting date, with gains and losses going to the income statement (see 3.3).
- *Liquidity rules:* it depends entirely on what the security is. Government bonds could be HQLA1. A corporate bond could be HQLA2A, HQLA2B or nothing. Encumbered securities (pledged to someone) do not count as HQLA (APS 210 Att A para 22(b), 23). Securities with a maturity of one year or more that are not HQLA get 85% in the NSFR (Att C para 36(c)). The statutory line alone does not tell you the answer. You need the security-level detail.

**Derivative assets** (also "positive fair value of derivatives").
- *What it is:* contracts such as interest rate swaps and foreign exchange forwards that currently have a positive value to the bank, meaning the other side would owe the bank money if the contract were closed out today. A **derivative** is a contract whose value depends on something else, such as an interest rate or exchange rate (Chapter 4).
- *Valuation:* fair value (mark-to-market).
- *Liquidity rules:* not HQLA. In the NSFR, derivative assets are measured on a replacement cost basis, net of liabilities where a netting agreement exists, and the net asset position gets 100% (Att C paras 27, 28, 37(b)). In the LCR, derivative cash outflows are taken net by counterparty only where a valid master netting agreement exists (Att A Table 3, footnote 5), and derivative inflows get 100% (Att A para 65).

**Investment securities** (also "available-for-sale", "debt instruments at fair value through other comprehensive income", or "securities at amortised cost").
- *What it is:* the bank's long-term securities holdings, often including the government and semi-government bonds in its liquid asset portfolio. Important: the liquidity buffer is frequently held here, not in "trading".
- *Valuation:* either fair value with changes in other comprehensive income, or amortised cost (see 3.3).
- *Liquidity rules:* same as trading securities: it depends on the security. Government and semi-government securities that qualify are HQLA1 (Att A para 9(c)). Unencumbered HQLA1 securities (other than cash and central bank claims) get 5% in the NSFR (Att C para 30).

**Loans and advances** (the line is often "loans, bills discounted and other receivables"), shown **gross, less provisions**.
- *What it is:* the loans made to households, businesses and governments: mortgages, personal loans, credit cards, business loans, overdrafts. It is usually the largest asset by far.
- *Gross vs net:* the gross amount is what customers owe. A **provision** (also "allowance for expected credit losses") is the bank's estimate of loans it will not get back. Net loans = gross loans less provisions. The balance sheet shows the net figure and the notes show the gross figure and provisions. Both matter. See 3.3.
- *Valuation:* mostly amortised cost less expected credit loss provision; a small portion may be at fair value.
- *Liquidity rules:* loans are not HQLA. In the LCR, only contractual repayments due within 30 days from fully performing loans count as inflows: 50% from retail and SME customers (Att A para 61) and 50% from non-financial corporates (Att A para 62(b)). Performing means the borrower is meeting its payments and there is no reason to expect a default within 30 days (Att A para 54). In the NSFR, the factor depends on type and maturity: 65% for standard residential mortgages with a loan-to-valuation ratio of 80% or below and a residual maturity of one year or more (Att C para 35(a)); 85% for other performing loans of one year or more (Att C para 36(b)); 50% for most loans under one year (Att C para 34(f)); 100% for non-performing loans (Att C para 37(c)).

**Property, plant and equipment** (PP&E).
- *What it is:* buildings, branch fit-outs, computers, and right-of-use assets for leased premises.
- *Valuation:* cost less accumulated depreciation (and sometimes revalued).
- *Liquidity rules:* none in the LCR. 100% RSF in the NSFR as a fixed asset (Att C para 37(c)).

**Intangibles and goodwill.**
- *What it is:* **goodwill** is the premium paid when one business buys another for more than the fair value of its identifiable net assets. Intangibles include software and brands.
- *Valuation:* cost less amortisation and impairment (goodwill is tested for impairment, not amortised).
- *Liquidity rules:* no LCR value. 100% RSF (Att C para 37(c): "items deducted from regulatory capital" and other assets not elsewhere listed). Goodwill and many intangibles are also deducted from regulatory capital (see 3.9), so it has no value in a stress.

**Deferred tax assets.**
- *What it is:* tax the bank expects to recover in future periods because of timing differences between accounting and tax rules.
- *Valuation:* the expected tax saving.
- *Liquidity rules:* no LCR value. Where deducted from capital, 100% RSF (Att C para 37(c)).

**Other assets.**
- *What it is:* everything else: accrued interest receivable, prepayments, settlement balances, insurance assets, investments in associates.
- *Liquidity rules:* mostly 100% RSF under the catch-all (Att C para 37(c)); some items, such as trade-date receivables expected to settle on time, get 0% (Att C para 29(d)).

### 3.2.2 Liabilities

**Deposits and other borrowings.**
- *What it is:* the combined funding line. It includes at-call deposits, savings, term deposits, certificates of deposit, and often repurchase agreements. In many bank reports the line is split in the notes by type: retail, corporate, wholesale, and so on. Chapter 4 defines each deposit type.
- *Valuation:* amortised cost (the amount owed plus accrued interest).
- *Liquidity rules:* this is the most important line for the LCR. Run-off rates range from 5% to 100% depending on type: stable retail 5%, less stable retail 10% or 25%, operational deposits 5% or 25%, non-operational corporate deposits 20% or 40%, other non-operational deposits (including financial institution deposits) 100% (Att A Table 3). In the NSFR the factors run from 95% for stable retail and SME deposits to 0% for short-term financial institution funding (Att C paras 11 to 15).

**Payables to financial institutions** (also "due to other banks").
- *What it is:* money the bank has borrowed from other banks and financial institutions, including interbank deposits and, in some reports, central bank funding.
- *Valuation:* amortised cost.
- *Liquidity rules:* unsecured funding from financial institutions that can be withdrawn within 30 days runs off at 100% (Att A Table 3, "all other non-operational deposits"). In the NSFR, funding from financial institutions with a residual maturity of under six months gets 0%, and six months to under one year gets 50% (Att C paras 15(a), 14(f)).

**Derivative liabilities.**
- *What it is:* derivative contracts with a negative value to the bank.
- *Valuation:* fair value.
- *Liquidity rules:* in the LCR, net derivative cash outflows within 30 days run off at 100% (Att A Table 3). In the NSFR, 20% of derivative liabilities (before deducting variation margin posted) are added to RSF (Att C para 37(d)), and net liabilities get a 0% ASF factor (Att C para 15(c)).

**Debt issues** (also "debt securities in issue", "bonds and notes").
- *What it is:* bonds, medium-term notes, commercial paper and covered bonds that the bank itself has issued to investors. This is **wholesale funding** (funding from large investors rather than households).
- *Valuation:* mostly amortised cost; sometimes fair value if hedged or designated.
- *Liquidity rules:* debt maturing within 30 days runs off at 100% in the LCR (Att A Table 3, "unsecured debt issuance"; para 45). Debt with a residual maturity of one year or more gets 100% ASF; six months to under one year gets 50%; under six months gets 0% (Att C paras 11(c), 14(f), 15(a)).

**Loan capital** (subordinated debt and hybrids).
- *What it is:* **subordinated debt** is debt that ranks below ordinary creditors if the bank fails. Hybrids are securities that mix features of debt and equity. Both are part of regulatory capital, so this line links directly to 3.9.
- *Valuation:* usually amortised cost.
- *Liquidity rules:* regulatory capital before regulatory adjustments gets 100% ASF, excluding the part of Tier 2 instruments with a residual maturity under one year (Att C para 11(a)). Note that maturing subordinated debt inside 30 days is still a contractual cash outflow in the LCR (Att A Table 3 "other contractual cash outflows", 100%).

**Provisions.**
- *What it is:* liabilities of uncertain timing or amount, such as employee entitlements, restructuring, customer remediation and legal claims. (Provisions for credit losses on loans normally reduce the loan asset instead; those on undrawn commitments sit here.)
- *Liquidity rules:* no stated maturity, usually 0% ASF (Att C para 15(b)).

**Other liabilities.**
- *What it is:* accrued expenses, trade creditors, lease liabilities, deferred tax liabilities, unearned income.
- *Liquidity rules:* liabilities without a stated maturity get 0% ASF, except deferred tax liabilities and minority interests, which are treated by their term (Att C para 15(b)). Contractual outflows within 30 days (for example bills due) fall under "other contractual cash outflows" at 100% (Att A Table 3).

### 3.2.3 Equity

| Line | What it is |
|---|---|
| **Share capital** | Money shareholders paid in for ordinary shares, and sometimes preference shares or capital notes classified as equity |
| **Reserves** | Gains and losses recorded outside profit, such as changes in the fair value of securities held at fair value through other comprehensive income, cash flow hedge reserve, foreign currency translation reserve |
| **Retained earnings** | Accumulated profits that have not been paid out as dividends |
| **Non-controlling interests** | The share of subsidiaries' equity owned by outside parties |

*Liquidity rules:* regulatory capital gets a 100% ASF factor (Att C para 11(a)). Non-controlling interests are treated by the term of the instrument, usually perpetual (Att C para 15(b)). Equity is not a cash outflow in the LCR.

> **Watch out:** Statutory equity is not the same as regulatory capital. Regulators start with accounting equity, then deduct goodwill, deferred tax assets and other items to arrive at CET1 (3.9). Att C para 11(a) refers to "the total amount of regulatory capital, before the application of regulatory adjustments", which is close to, but not identical with, the accounting equity figure.

## 3.3 Valuation ideas a non-accountant needs

Banks hold a mix of assets valued in different ways. The same A$100 loan could be shown at A$100, A$98, or A$103 depending on rules. Liquidity regulation deliberately uses a particular valuation basis for each purpose, so you must know which one a number is on.

### Carrying value, market value and face value

| Term | Meaning |
|---|---|
| **Carrying value** | The amount at which an item is shown on the balance sheet, after the accounting adjustments that apply to it. The NSFR starts from carrying value for both capital and liabilities (ASF) and assets (RSF) (Att C paras 7(a), 17(a); Att C footnote 9: "before application of any regulatory deductions, filters or other adjustments") |
| **Market value** | The price at which the item could be sold today in an active market. HQLA are counted at market value, then haircuts are applied (Att A para 9, 10, 12) |
| **Face value** (also nominal or principal) | The amount a bond or loan repays at maturity, regardless of today's price (Chapter 4) |

A government bond with a face value of A$100 might have a market value of A$96 after interest rates rose. If the bank holds it at amortised cost, its carrying value might still be near A$100. The LCR uses A$96 (market value); the NSFR uses the carrying value.

### Amortised cost vs fair value

- **Amortised cost** starts from the amount originally lent or borrowed, adds interest as it accrues, and subtracts repayments and loss allowances. It ignores day-to-day market price changes. It suits loans and deposits the bank intends to hold and collect or repay.
- **Fair value** is the price that would be received to sell an asset (or paid to transfer a liability) in an orderly transaction at the measurement date. It changes with the market. Valuing at current market prices is also called **mark-to-market**. When no active market exists, models estimate it ("mark-to-model").

Under the main Australian accounting standard for financial instruments, AASB 9 *Financial Instruments*, a financial asset is classified by (1) the bank's business model for the asset and (2) the contractual cash flow characteristics of the asset. In broad terms (as generally understood; check AASB 9 for exact criteria):

| Category | Typical use | Where changes in value go |
|---|---|---|
| Amortised cost | Loans held to collect repayments; deposits placed | No fair value changes shown; interest accrues, loss allowance applies |
| Fair value through other comprehensive income (FVOCI) | Securities held both to collect cash flows and to sell, such as many liquid asset portfolio bonds | Changes recorded in other comprehensive income (a section below profit); moved to profit if sold |
| Fair value through profit or loss (FVTPL) | Trading securities, derivatives, assets that fail the cash-flow test | Changes recorded directly in profit or loss |

The practical consequence for a liquidity reader: a fall in bond prices can reduce equity (via reserves, if FVOCI), or reduce profit (if FVTPL), or hide in the notes (if amortised cost). Liquidity regulation looks through all three: the HQLA stock is measured at market value regardless of accounting classification (Att A para 9).

### Expected credit loss provisions

AASB 9 requires a bank to recognise an **expected credit loss** (ECL) allowance on its loans and debt securities that are not held at FVTPL. ECL is a probability-weighted estimate of credit losses. In broad terms the allowance is the 12-month ECL for loans whose credit quality has not worsened much, and lifetime ECL for loans where credit risk has increased significantly or that are credit-impaired. Banks usually describe this as stage 1, stage 2 and stage 3. This matters for two reasons:

1. Net loans on the balance sheet = gross loans less the ECL allowance.
2. A bank's expense for credit losses (the "credit impairment charge") flows through the income statement (3.7).

For liquidity, the key point is that regulatory liquidity amounts use contractual exposures for performing loans, and non-performing loans are excluded from inflows (Att A para 54) and attract 100% in the NSFR (Att C para 37(c)).

### Accruals

An **accrual** is revenue earned or an expense incurred that has not yet been paid in cash. If a bank has earned a month of interest on a loan but the borrower pays at month-end, the earned interest sits as "accrued interest receivable" (an asset). Likewise interest owing on deposits sits as "accrued interest payable" (a liability). Accruals are why profit and cash flow are different numbers: profit counts what is earned; cash flow counts what is paid. A bank can be profitable on an accrual basis and still run short of cash. That is the liquidity problem in one sentence.

### Disclosure standard

The Australian standard that governs what must be disclosed about financial instruments, including liquidity risk and maturity analysis, is AASB 7 *Financial Instruments: Disclosures* (the AASB website confirms paragraph 39 requires a maturity analysis for non-derivative financial liabilities and derivative liabilities). That is the source of the maturity tables described in 3.6.

## 3.4 Presentation in liquidity order, and the two kinds of maturity

Banks present assets and liabilities in the order of liquidity rather than splitting them into current and non-current. A retailer can say "stock sells within a year, so it is current". A bank cannot say that about a mortgage: it has a 30-year contractual term, but a customer can repay early, the bank can sell or securitise it, and part of it falls due every month. The statutory balance sheet therefore lists in rough liquidity order and the notes carry the maturity detail.

Two maturity concepts appear everywhere in liquidity rules:

| Concept | Meaning | Example |
|---|---|---|
| **Original maturity** (also original term) | The length of the contract when it was first written | A 5-year bond issued in 2022 |
| **Residual maturity** (also remaining maturity) | The time left until the contract ends, measured from today | The same bond in 2026 has about one year left |

Liquidity rules use **residual maturity**. A term deposit that was a five-year product but now has 20 days left is a 20-day item. A term deposit with a 90-day original term that is two days from maturity is a 2-day item (APS 210 Att A para 45 uses "earliest possible contractual maturity date" within the horizon; Att C paras 8, 20 to 22 set the NSFR rules for maturity).

Important subtleties for building a data model:

- For **liabilities**, the NSFR assumes the earliest date funds may be redeemed (Att C para 8). For **assets**, the NSFR assumes the latest possible maturity, and assumes any option to extend will be exercised (Att C para 20).
- Where an asset has no defined maturity or is subject to periodic review, the NSFR treats it as one year or more (Att C para 21).
- For an amortising loan, the portion due within one year may be included in the under-one-year category (Att C para 22). An **amortising loan** is one where each repayment includes some principal as well as interest, so the balance falls over time.
- **Contractual maturity** is the date written in the contract. **Behavioural maturity** is when customers are expected to act, for example withdrawing "at call" deposits that in practice stay for years. Regulators prescribe behavioural-like assumptions through run-off rates; banks also model their own. Chapter 9 covers the maturity ladder.

## 3.5 Off-balance sheet items

**Off-balance sheet** items are commitments and contingent exposures that do not appear as assets or liabilities on the statutory balance sheet today, but could create cash flows or balance sheet exposure later. Liquidity regulators care because a customer can turn a promise into a cash demand at any time.

| Item | What it is | Why it matters for liquidity |
|---|---|---|
| **Undrawn commitments** | A **committed facility** is a promise to lend up to a limit on request. The undrawn part is the unused portion. | The customer can draw it down in a stress, and the bank must fund it. LCR run-off 5% to 100% depending on customer and facility type (Att A Table 3). NSFR 5% for irrevocable and conditionally revocable facilities (Att C para 41, Table 1) |
| **Guarantees** | A **guarantee** is a promise to pay if a customer fails to meet an obligation to a third party | If called, the bank pays cash. LCR rate is a percentage of recent actual monthly net outflows (Att A Table 3, 50% of the average of actual monthly net outflows in a recent 12-month period) |
| **Letters of credit** | A **letter of credit** is the bank's promise to pay a seller on presentation of the right documents, used in trade | Same treatment as guarantees unless trade finance related (Att A Table 3; Att C para 42) |
| **Derivatives** | Contracts valued off other prices | The balance sheet shows only the current market value (net positive or negative). The risk can be far larger than the value; see below |
| **Contingent liabilities** | Obligations that depend on an uncertain future event, for example legal claims or guarantees given | Disclosed in the notes. Cash outflow only if the event occurs |

### Notional vs market value for derivatives

The **notional** amount of a derivative is the face amount on which payments are calculated. It is a reference number, not money that changes hands. An interest rate swap with a notional of A$1 billion does not involve A$1 billion of cash. Only the interest differences are paid. The **market value** (also fair value or replacement cost) is what the contract is worth today; it can be positive (asset) or negative (liability).

```
Notional: A$1,000m interest rate swap
Market value today: +A$4m  (derivative asset: the bank would receive A$4m to close out)
```

The balance sheet shows A$4m, not A$1,000m. The notional is a note disclosure. For liquidity, what matters is the cash and collateral the contract can demand: variation margin calls when the market value moves against the bank, and extra collateral if the bank is downgraded. The LCR includes outflows for collateral that would be posted on a 3-notch downgrade, and for market-move collateral calls based on the largest net 30-day collateral flow in the past 24 months (Att A Table 3). Chapter 4 covers derivatives in depth.

> **Why it matters:** A bank with a small derivative balance on its balance sheet can still face large margin calls if markets move or its credit rating falls. A balance sheet alone understates liquidity risk. Always read the commitments and derivative notes.

## 3.6 The notes that matter for liquidity

The notes to the financial statements are where the liquidity story is told. For a fast read, look for these:

| Note (typical name) | What it shows | What to look for |
|---|---|---|
| **Maturity analysis of liabilities** (under liquidity risk, often required by AASB 7) | Contractual undiscounted cash flows by time bucket: on demand, up to 3 months, 3 to 12 months, 1 to 5 years, over 5 years | A heavy "on demand" bucket; the gap between short-dated liabilities and long-dated assets |
| **Maturity profile of assets** | The same for assets, in some reports | Whether liquid assets cover the early buckets |
| **Assets pledged as collateral (encumbrance)** | Which assets are pledged for repos, covered bonds, securitisation and derivative collateral | High encumbrance reduces the pool of assets available in a stress (APS 210 para 38; Att A para 22(b), 23) |
| **Funding composition** | Split of funding between retail deposits, wholesale deposits, short and long-term debt, equity | Share of stable funding; share of short-term wholesale; offshore funding |
| **Contingent liabilities and commitments** | Undrawn loan facilities, guarantees, letters of credit, legal claims | Size of undrawn commitments relative to liquid assets |
| **Liquidity risk note** (financial risk management section) | How the bank manages liquidity, its liquid asset holdings, and its regulatory ratios | The stated LCR and NSFR, size and composition of liquid assets, and policy summary |
| **Derivatives note** | Notional and fair value by type | Large gross positions; collateral arrangements |
| **Securitisation and transferred assets** | Assets sold to or held in special purpose vehicles | Self-securitised assets that can be used as collateral (Chapter 4) |

> **In the standard:** APS 210 requires an ADI to project cash flows from assets, liabilities and off-balance sheet items over an appropriate set of time horizons (APS 210 para 36) and to differentiate between encumbered and unencumbered assets (APS 210 para 38). The notes are where an outsider sees summarised versions of both.

## 3.7 The income statement in one section

The **income statement** (also profit and loss statement) shows revenue and expenses over a period, such as a year. It is a movie rather than a snapshot. Its lines, from top to bottom:

| Line | Meaning |
|---|---|
| **Interest income** | Interest earned on loans, securities and balances with other banks |
| **Interest expense** | Interest paid on deposits, debt and other borrowings |
| **Net interest income** (NII) | Interest income less interest expense. This is the bank's core earnings |
| **Non-interest income** (also other operating income) | Fees, commissions, trading income, gains on derivatives, other income |
| **Operating expenses** | Staff, technology, premises, marketing, compliance |
| **Credit impairment charge** | The expense for expected credit losses, linked to the provision on the balance sheet |
| **Profit before tax**, then **income tax**, then **profit after tax** (net profit) | What is left |

```
Net interest income   = Interest income - Interest expense
Operating income      = Net interest income + Non-interest income
Profit before tax     = Operating income - Operating expenses - Credit impairment charge
```

Key ratios:

| Ratio | Formula | What it tells you |
|---|---|---|
| **Net interest margin** (NIM) | Net interest income / average interest-earning assets | The spread the bank earns on its assets after paying for its funding |
| **Return on equity** (ROE) | Profit after tax / average equity | How well the owners' money is used |
| **Cost-to-income ratio** | Operating expenses / operating income | Efficiency: lower is better |

### Why liquidity costs show up in net interest margin

Liquid assets earn less than loans. A government bond might yield less than a mortgage, and cash at the RBA earns only the RBA's rate on Exchange Settlement balances (which, as generally understood, is set at a small margin below the cash rate target; see the RBA website). Meanwhile the bank's deposits and wholesale debt cost whatever they cost. So every dollar parked in the liquid asset buffer instead of lent out reduces the average yield on the asset side. Likewise, long-term wholesale funding costs more than at-call deposits (investors want a premium to lock money up), but the NSFR encourages banks to hold it. Both the LCR and the NSFR therefore push NIM down. That is the cost of safety, and why banks run a modest buffer above 100% rather than a very large one (APS 210 Att A para 4; Att C para 4).

> **Example:** Suppose a bank holds A$17bn in liquid assets earning 4.0% and funds them at 3.5%, a spread of 0.5%. If those A$17bn were instead lent as mortgages earning 6.0% against the same 3.5% funding, the spread would be 2.5%. The extra margin foregone is 2.0% x A$17bn = A$340m a year. These rates are invented for illustration only.

## 3.8 Profitability is not liquidity

Because the income statement is on an accrual basis, a bank can report a profit while running out of cash. It is why liquidity regulators look at the balance sheet and cash flows, not at profit. Chapter 1 covers this difference between liquidity, solvency, capital and profitability.

## 3.9 Capital in one section

Capital is often confused with liquidity. This section keeps them apart.

**Regulatory capital** is the part of a bank's funding that can absorb losses without the bank having to close. It is mostly equity plus certain subordinated debt and hybrid securities. APRA's capital rules are in Prudential Standards APS 110 (Capital Adequacy), APS 111 (Measurement of Capital) and APS 112 (Standardised Approach to Credit Risk), as referred to in APS 210 (for example Att C para 11(a) refers to APS 111; Att A para 9(c)(i) refers to APS 112; Att C para 26 refers to APS 110). Chapter 2 covers these standards.

| Tier | Meaning |
|---|---|
| **Common Equity Tier 1 (CET1)** | The highest-quality capital: ordinary shares and retained earnings, less deductions such as goodwill and deferred tax assets |
| **Additional Tier 1 (AT1)** | Hybrid securities that can absorb losses while the bank is still operating, for example by converting to shares or being written off |
| **Tier 2** | Subordinated debt that absorbs losses if the bank fails or is close to failing |

**Risk-weighted assets** (RWA) are a way of scaling assets by riskiness. Each asset is multiplied by a **risk weight**: 0% for safe government exposures, 20% for some bank exposures, 35% for standard mortgages in the standardised approach (as generally understood; the APS 112 text sets the exact weights), up to 100% or more for riskier loans. Adding the results gives RWA. APS 210 itself refers to risk weights to define HQLA: for example, HQLA1 securities must carry a 0% risk weight (Att A para 9(c)(i)).

```
CET1 ratio        = CET1 capital / Risk-weighted assets
Total capital ratio = (CET1 + AT1 + Tier 2) / Risk-weighted assets
Leverage ratio     = Tier 1 capital / Total exposures (not risk-weighted)
```

The **leverage ratio** is a simple backstop: capital divided by total exposures, with no risk weights, so a bank cannot reduce its capital need by loading up on assets with low risk weights.

> **Watch out:** Capital and liquidity answer different questions.
> - Capital: *can the bank absorb losses?* It is about the right-hand side's loss-absorbing layer.
> - Liquidity: *can the bank pay what falls due when it falls due?* It is about cash and the ability to raise cash.
> A bank with plenty of capital can run out of cash. A bank with plenty of liquid assets can be insolvent. Capital ratios are computed from risk-weighted assets. The LCR and NSFR do not use risk weights, except that risk weights help define which securities are HQLA (Att A para 9(c)(i), 10(a)(i)).

## 3.10 Example Bank: the balance sheet and every line

Example Bank is a fictional locally incorporated bank used throughout this guide. All figures are A$ billions.

| Assets | A$bn | Liabilities and equity | A$bn |
|---|---|---|---|
| Cash and balances with the RBA | 5.0 | Retail deposits, stable (at call) | 25.0 |
| Government and semi-government securities | 12.0 | Retail deposits, less stable (at call, scorecard 0 to 2) | 15.0 |
| Other debt securities (non-HQLA, over 1 year) | 3.0 | Retail term deposits (over 30 days, under 1 year, no early withdrawal, less stable) | 10.0 |
| Loans to other banks (under 6 months, unsecured) | 2.0 | SME deposits (qualifying, less stable) | 5.0 |
| Residential mortgages (standard, LVR 80% or below, over 1 year) | 50.0 | Corporate operational deposits (not fully insured) | 4.0 |
| Business loans (over 1 year) | 15.0 | Corporate non-operational deposits (not fully insured) | 6.0 |
| Personal and business loans (under 1 year) | 8.0 | Financial institution deposits (at call) | 4.0 |
| Other assets (premises, goodwill, tax assets) | 5.0 | Wholesale debt maturing within 30 days | 1.0 |
| | | Wholesale debt, over 30 days and under 6 months | 3.0 |
| | | Wholesale debt, 6 months to under 1 year | 2.0 |
| | | Wholesale debt, 1 year or more | 15.0 |
| | | Other liabilities (no stated maturity) | 2.0 |
| | | Shareholders' equity (treated as regulatory capital) | 8.0 |
| **Total assets** | **100.0** | **Total liabilities and equity** | **100.0** |

Check the identity: assets 5.0 + 12.0 + 3.0 + 2.0 + 50.0 + 15.0 + 8.0 + 5.0 = 100.0. Liabilities 25.0 + 15.0 + 10.0 + 5.0 + 4.0 + 6.0 + 4.0 + 1.0 + 3.0 + 2.0 + 15.0 + 2.0 = 92.0, plus equity 8.0 = 100.0. The two sides agree.

### Example Bank's off-balance sheet items and 30-day flows

| Item | A$bn |
|---|---|
| Undrawn committed facilities, retail and SME | 10.0 |
| Undrawn committed credit facilities, non-financial corporates | 5.0 |
| Undrawn committed liquidity facilities, non-financial corporates | 1.0 |
| Net derivative cash outflows due within 30 days | 0.3 |
| Collateral to be posted on a 3-notch downgrade | 0.2 |
| Contractual loan repayments due within 30 days, retail and SME | 1.0 |
| Contractual loan repayments due within 30 days, non-financial corporates | 0.8 |
| Contractual repayments due within 30 days from other banks | 1.0 |

### Every line explained

**Assets**

- *Cash and balances with the RBA, 5.0.* Notes, coin and the balance in Example Bank's Exchange Settlement Account. The most liquid asset there is. 5% of the balance sheet.
- *Government and semi-government securities, 12.0.* Bonds issued by the Commonwealth and by state and territory governments. Easily sold or lent to the RBA. Together with cash they make up Example Bank's whole liquidity buffer.
- *Other debt securities, 3.0.* Bonds that do not qualify as HQLA, with more than a year to maturity. They could be sold, but they do not count in the LCR.
- *Loans to other banks, 2.0.* Unsecured lending to other banks, due in under six months.
- *Residential mortgages, 50.0.* Standard home loans with a loan-to-valuation ratio (loan divided by property value) of 80% or below and more than a year to run. Half of the entire balance sheet. This is the classic illiquid asset: it pays back slowly, month by month.
- *Business loans, 15.0.* Loans to businesses with more than a year to run.
- *Personal and business loans, 8.0.* Shorter loans of under a year.
- *Other assets, 5.0.* Premises, goodwill, tax assets. None of it can be turned into cash quickly.

**Liabilities**

- *Retail deposits, stable, 25.0.* Households' money in transaction and similar accounts, where the customer has other established relationships with the bank and the deposit is covered by the Financial Claims Scheme (the government deposit guarantee, up to A$250,000 per account holder per ADI) (APS 210 Att A para 37). The most reliable funding.
- *Retail deposits, less stable, 15.0.* At-call household deposits that are not stable, with a scorecard of 0 to 2 (Att A paras 38 to 40).
- *Retail term deposits, 10.0.* Household deposits locked for more than 30 days, less than a year, with no early withdrawal right (Att A para 41).
- *SME deposits, 5.0.* Small business deposits treated as retail because each customer has less than A$2 million in total (Att A para 46).
- *Corporate operational deposits, 4.0.* Deposits that companies leave with the bank to support clearing, custody or cash management services (Att A paras 47 to 50). Not fully covered by the Financial Claims Scheme.
- *Corporate non-operational deposits, 6.0.* Company deposits kept for return, not for services.
- *Financial institution deposits, 4.0.* At-call deposits from other financial institutions, the most flighty funding on the sheet.
- *Wholesale debt, 1.0 / 3.0 / 2.0 / 15.0.* Bonds and notes Example Bank has issued, split by remaining time to maturity: within 30 days; over 30 days to 6 months; 6 months to under 1 year; 1 year or more.
- *Other liabilities, 2.0.* Items with no stated maturity.
- *Shareholders' equity, 8.0.* Treated as regulatory capital for this exercise.

### The simple ratios, and what each tells you

| Ratio | Calculation | Result | What it tells you |
|---|---|---|---|
| **Customer loans** | 50.0 + 15.0 + 8.0 | 73.0 | The loan book funded by customers |
| **Customer deposits** | 25.0 + 15.0 + 10.0 + 5.0 + 4.0 + 6.0 | 65.0 | Deposits from households and non-financial businesses (financial institution deposits excluded) |
| **Loan-to-deposit ratio** (LDR) | 73.0 / 65.0 | **112.3%** | Above 100% means loans exceed customer deposits, so the bank also relies on wholesale debt and other funding. The higher the LDR, the more dependent the bank is on markets |
| **Liquid assets to total assets** | (5.0 + 12.0) / 100.0 | **17.0%** | Share of the balance sheet in the liquid asset portfolio |
| **Equity to total assets** | 8.0 / 100.0 | **8.0%** | The simplest measure of loss-absorbing cushion. Not a regulatory ratio |
| **Total liabilities** | 25.0 + 15.0 + 10.0 + 5.0 + 4.0 + 6.0 + 4.0 + 1.0 + 3.0 + 2.0 + 15.0 + 2.0 | 92.0 | |
| **Deposits (including financial institutions) as share of liabilities** | 69.0 / 92.0 | **75.0%** | Reliance on deposits. 65.0 customer deposits plus 4.0 financial institution deposits = 69.0 |
| **Wholesale debt as share of liabilities** | (1.0 + 3.0 + 2.0 + 15.0) = 21.0; 21.0 / 92.0 | **22.8%** | Reliance on debt markets. Note that 6.0 of the 21.0 matures within a year |

> **Watch out:** These ratios are quick screens, not regulatory measures. An LDR of 112.3% looks alarming until you see that 15.0 of the 21.0 wholesale debt has a residual maturity of a year or more. The regulatory NSFR (Chapter 6) and LCR (Chapter 5) weight each item by stability and liquidity rather than treating all deposits and debt the same.

## 3.11 Mapping each Example Bank line to its LCR and NSFR treatment

This table is the bridge to Chapters 5 and 6. Each treatment is shown by category name, factor and paragraph reference. Details and every limb of each rule are in those chapters. The derivative balance is ignored in the NSFR for simplicity.

### Assets

| Example Bank line (A$bn) | LCR treatment | NSFR treatment (RSF factor) |
|---|---|---|
| Cash and balances with the RBA (5.0) | HQLA1, no haircut (Att A para 9(a), 9(b)). Counts in the numerator | 0% (Att C para 29(a), 29(b)) |
| Government and semi-government securities (12.0) | HQLA1, no haircut, subject to the conditions in Att A para 9(c); in the numerator | 5% as unencumbered HQLA1 (Att C para 30(a)) |
| Other debt securities, non-HQLA, over 1 year (3.0) | Not HQLA. No inflow in the 30-day window as they do not mature within it (inflows from maturing securities not in the HQLA stock are 100%, Att A para 62) | 85% as unencumbered securities of one year or more that are not HQLA (Att C para 36(c)) |
| Loans to other banks, under 6 months, unsecured (2.0) | Not HQLA. Only contractual repayments due within 30 days count as inflows: 1.0 at 100% (Att A para 62(a)) | 15% as other unencumbered loans to financial institutions under six months (Att C para 33(b)) |
| Residential mortgages (50.0) | Not HQLA. Contractual repayments due within 30 days from retail and SME customers (1.0 of the Example Bank flows) count at 50% (Att A para 61) | 65% as standard residential loans, LVR 80% or below, one year or more (Att C para 35(a)) |
| Business loans, over 1 year (15.0) | Not HQLA. Contractual repayments within 30 days from non-financial corporates (0.8) count at 50% (Att A para 62(b)) | 85% as other performing loans of one year or more (Att C para 36(b)), on the assumption that they do not qualify for a risk weight of 35% or lower (Att C para 35(b)) |
| Personal and business loans, under 1 year (8.0) | Not HQLA. Their repayments are part of the retail and SME and corporate inflow lines above | 50% as loans with a residual maturity under one year to retail, SME and non-financial corporate customers (Att C para 34(f)) |
| Other assets (5.0) | Not HQLA. No inflow | 100% as other assets (Att C para 37(c)) |

### Liabilities and equity

| Example Bank line (A$bn) | LCR treatment (run-off rate) | NSFR treatment (ASF factor) |
|---|---|---|
| Retail deposits, stable (25.0) | Stable retail deposit, 5% (Att A para 37; Table 3) | 95% (Att C para 12(a)) |
| Retail deposits, less stable, scorecard 0 to 2 (15.0) | Less stable retail, 10% (Att A paras 38 to 40, Table 2; Table 3) | 90% (Att C para 13(a)) |
| Retail term deposits, over 30 days, no early withdrawal (10.0) | 0%: excluded because the depositor has no legal right to withdraw within 30 days (Att A para 41) | 90% as less stable term deposits under one year (Att C para 13(a)) |
| SME deposits, qualifying (5.0) | Treated as retail under Att A para 46; less stable, 10% (Table 3) | 90% (Att C para 13(a)) |
| Corporate operational deposits, not fully insured (4.0) | 25% (Att A paras 47 to 50; Table 3) | 50% (Att C para 14(b)) |
| Corporate non-operational deposits, not fully insured (6.0) | 40% (Att A Table 3) | 50% as funding under one year from non-financial corporates (Att C para 14(a)) |
| Financial institution deposits, at call (4.0) | 100% as other non-operational deposits (Att A Table 3) | 0% as funding under six months from financial institutions (Att C para 15(a)) |
| Wholesale debt within 30 days (1.0) | 100% as unsecured debt issuance (Att A Table 3; para 45) | 0% (Att C para 15(a)) |
| Wholesale debt, over 30 days to under 6 months (3.0) | 0%: outside the 30-day window (Att A para 45) | 0% (Att C para 15(a)) |
| Wholesale debt, 6 months to under 1 year (2.0) | 0%: outside the 30-day window | 50% (Att C para 14(f)) |
| Wholesale debt, 1 year or more (15.0) | 0%: outside the 30-day window | 100% (Att C para 11(c)) |
| Other liabilities, no stated maturity (2.0) | Not included in the example (no cash outflow assumed in the 30-day window) | 0% (Att C para 15(b)) |
| Shareholders' equity (8.0) | No outflow | 100% as regulatory capital (Att C para 11(a)) |

### Off-balance sheet

| Example Bank item (A$bn) | LCR treatment | NSFR treatment |
|---|---|---|
| Undrawn committed facilities, retail and SME (10.0) | 5% (Att A Table 3) | 5% (Att C para 41, Table 1) |
| Undrawn committed credit facilities, non-financial corporates (5.0) | 10% (Att A Table 3) | 5% (Att C para 41) |
| Undrawn committed liquidity facilities, non-financial corporates (1.0) | 30% (Att A Table 3; definition in Att A para 51) | 5% (Att C para 41) |
| Net derivative cash outflows within 30 days (0.3) | 100% (Att A Table 3) | Derivatives ignored for simplicity |
| Collateral on a 3-notch downgrade (0.2) | 100% (Att A Table 3) | Derivatives ignored for simplicity |

Under the NSFR example in this guide, the three undrawn facilities total 16.0 and are treated at 5%, giving 0.80 of RSF.

> **Why it matters:** Notice what the mapping shows. The same A$1 of balance sheet can be a source of strength (stable retail deposits: 95% ASF) or a drain (financial institution deposits: 100% LCR run-off, 0% ASF). The totals are Example Bank's LCR of 147.2% (HQLA 17.0 divided by net cash outflows 11.55) and NSFR of 136.3% (ASF 79.75 divided by RSF 58.50). Chapters 5 and 6 build these from the table above, line by line.

## 3.12 Reading a real bank's public liquidity disclosure

Locally incorporated and larger Australian banks publish their LCR and NSFR as part of "Pillar 3" disclosures. **Pillar 3** is the third part of the Basel framework: it requires banks to publish standardised regulatory information so markets can compare them. In Australia the disclosure rules sit in Prudential Standard APS 330 *Public Disclosure*, which APRA has revised several times (APRA's website shows several versions and drafts of this standard, so confirm the in-force version before relying on the detail below).

What the disclosures show, as generally understood and consistent with Basel's template design:

- **LCR template.** For each line (HQLA categories, outflow categories, inflow categories) it shows an **unweighted** amount and a **weighted** amount. *Unweighted* means the raw balance before the run-off or inflow rate; *weighted* means after multiplying by the rate and, for HQLA, after haircuts. For example, A$6bn of corporate non-operational deposits unweighted becomes A$2.4bn weighted at 40%. The template ends with total HQLA, total net cash outflows and the LCR.
- **Averages.** In APRA's published materials the LCR figures are described as averages of daily observations over the quarter, with the number of data points disclosed (from APRA's 2023 version of APS 330, as reported in a search of APRA's website; verify). This means a published LCR is a quarterly average, not a single-day figure. A bank's dashboard computes a daily LCR, so the two will not match exactly.
- **NSFR template.** It shows unweighted amounts by residual maturity bucket (no maturity, under six months, six months to under one year, one year or more) and the weighted amounts, ending with ASF, RSF and the NSFR. NSFR disclosure is made at quarter-ends (per the APRA material above). The figure is a point-in-time quarter-end figure, as generally understood; verify in APS 330 Attachment F.
- **Exemption.** Banks that use the minimum liquidity holdings approach are, in the drafts I saw on APRA's website, not required to disclose the LCR and NSFR. Chapter 7 covers that regime.

> **Watch out:** Comparing your dashboard's daily LCR to a published quarterly average LCR is comparing different things. Also comparing unweighted to weighted columns is a common error. Always say which one you mean.

## 3.13 A five-minute liquidity read of any bank's annual report

Use this routine. It takes roughly five minutes and gives a reasonable first view.

1. **Find the balance sheet (minute 1).** Note total assets. Check assets = liabilities + equity. Note the share of cash and liquid assets, investment securities and net loans.
2. **Funding mix (minute 2).** Divide deposits by total liabilities. Check the split between retail, corporate and wholesale in the notes. Compute loans divided by customer deposits. Note the amount of debt issued and its maturity split.
3. **Liquidity risk note (minute 3).** Find the maturity analysis of liabilities. What share is "on demand" or "up to 3 months"? Compare with the liquid assets. Note anything described as encumbered or pledged.
4. **Commitments and derivatives (minute 3 to 4).** Find undrawn commitments, guarantees and the derivative notional. Divide undrawn commitments by liquid assets.
5. **Regulatory ratios (minute 4).** Find the stated LCR and NSFR (in the annual report, or in the Pillar 3 report). Check they are above 100%. Check whether they are quarterly averages or point-in-time figures. Look at the buffer above 100%.
6. **Income statement (minute 5).** Net interest margin: trend up or down? Cost-to-income? Credit impairment charge trend? Falling NIM may reflect a higher liquid asset buffer or costlier funding.
7. **Capital (minute 5).** CET1 ratio and leverage ratio, for context.
8. **Write down three observations**: the main funding risk, the main buffer, and one thing you want to check in the full notes.

## Key points

- The accounting equation, assets = liabilities + equity, always holds. For a bank, a customer's deposit is the bank's liability and a customer's loan is the bank's asset.
- Banks present in liquidity order, not current and non-current. Liquidity rules use residual (remaining) maturity, not original maturity. For liabilities the NSFR uses the earliest redemption date; for assets, the latest maturity (APS 210 Att C paras 8, 20).
- The valuation basis matters: amortised cost, fair value through other comprehensive income, and fair value through profit or loss behave differently, but HQLA is counted at market value whatever the accounting basis (Att A para 9). The NSFR starts from carrying value (Att C para 7(a), 17(a)).
- Off-balance sheet items (undrawn commitments, guarantees, letters of credit, derivatives) are invisible on the balance sheet but create LCR outflows and NSFR requirements. Derivative notional is not the cash at risk.
- The liquidity story is in the notes: the maturity analysis, encumbered assets, funding composition, commitments and the liquidity risk note.
- Liquidity costs appear in net interest margin because liquid assets earn less than loans and stable funding costs more than at-call funding.
- Capital (can the bank absorb losses?) and liquidity (can it pay when due?) are different questions. CET1, Additional Tier 1 and Tier 2 are measured against risk-weighted assets; the LCR and NSFR do not use risk weights.
- Example Bank: loan-to-deposit ratio 112.3%, liquid assets 17.0% of assets, equity 8.0%, LCR 147.2%, NSFR 136.3%.
- Published LCR figures are, as generally understood, quarterly averages of daily values with weighted and unweighted columns; do not compare them with a single-day dashboard value without noting the difference.

## Check your understanding

**1. A customer deposits A$10,000 in a savings account. Explain what happens to the bank's balance sheet, and why the deposit is not an asset to the bank.**
**Answer:** Cash (an asset) rises by A$10,000 and deposits (a liability) rise by A$10,000. Assets still equal liabilities plus equity. The deposit is a liability because the bank owes the money back to the customer on demand or at maturity.

**2. Example Bank's balance sheet shows 'Residential mortgages 50.0'. Using the table in 3.11, state which category and factor applies in the NSFR, and why the LCR gives it no value as a liquid asset.**
**Answer:** 65% RSF as a standard residential loan with LVR 80% or below and residual maturity of one year or more (Att C para 35(a)), so 50.0 x 65% = 32.50 of RSF. It is not HQLA: it cannot be sold quickly at a certain value (Att A para 9 limits HQLA1 to notes and coin, central bank balances, and qualifying sovereign and similar securities). Only 30-day contractual repayments count, as inflows at 50% (Att A para 61).

**3. Calculate Example Bank's loan-to-deposit ratio and explain why a result above 100% does not by itself mean the bank is in trouble.**
**Answer:** Customer loans 73.0 / customer deposits 65.0 = 112.3%. Above 100% means part of the loan book is funded by something other than customer deposits, here wholesale debt (21.0 of which 15.0 matures in one year or more) and equity. That long-term funding is stable, so the NSFR of 136.3% shows the bank is soundly funded despite the ratio. The simple ratio does not weight funding by stability.

**4. A bond has a face value of A$100m. Interest rates rise and its market value falls to A$94m. The bank holds it as HQLA1 at amortised cost with a carrying value of A$99m. What value goes into the LCR numerator and what value is the starting point for the NSFR?**
**Answer:** The LCR numerator uses market value, A$94m, with no haircut for HQLA1 (Att A para 9). The NSFR starts from carrying value, A$99m (Att C para 17(a)), and applies the RSF factor (5% for unencumbered HQLA1 securities, Att C para 30), giving 4.95 of RSF.

**5. Explain the difference between original and residual maturity using a 5-year term deposit with 20 days left. How would the LCR treat it if the depositor has no right to withdraw early?**
**Answer:** Original maturity is five years; residual maturity is 20 days. The LCR looks at what happens within 30 days, so by residual maturity the deposit falls inside the window. For retail term deposits, only those with a residual maturity or notice period greater than 30 days can be excluded (Att A para 41). With 20 days left, it matures inside 30 days, so the exclusion is not available and it is treated as a normal retail outflow based on its stability (stable 5%, less stable 10% or 25%).

**6. A bank has a A$1,000m interest rate swap (notional) with a market value of negative A$6m, and has posted no variation margin. In the NSFR, how much is added to required stable funding from this derivative liability? What does the notional tell you that the market value does not?**
**Answer:** 20% of the derivative liability (negative replacement cost) before deducting variation margin posted: 20% x 6 = A$1.2m of RSF (Att C para 37(d)), ignoring the netting against derivative assets. The notional (A$1,000m) shows the scale of exposure and how large future movements in market value, and so margin calls, could become; the market value shows only today's amount.

**7. Example Bank lends A$3.0bn of its cash as new standard mortgages. What happens to its net interest margin, its LCR and its NSFR?**
**Answer:** The net interest margin rises, since mortgages earn more than cash at the RBA, but the LCR falls. HQLA drops from 17.0 to 14.0, giving 14.0 / 11.55 = 121.2% (down from 147.2%), and the NSFR falls from 136.3% to 131.9% because RSF rises by 3.0 x 65% = 1.95 to 60.45 (79.75 / 60.45). This is the profit versus safety trade-off.

**8. Why can a bank be profitable and still run out of cash?**
**Answer:** Profit is measured on an accrual basis: interest earned on a long loan is recognised as it accrues, but the cash arrives over many years, while deposits and short-term debt can be withdrawn immediately. Profit does not give cash to pay depositors on the day they ask. Liquidity ratios therefore look at cash flows over 30 days (LCR) and the stability of funding over one year (NSFR).

---

# Chapter 4: Instruments and market terms

A balance sheet line such as "deposits" or "debt securities" hides dozens of different products. Liquidity rules treat them differently, so you need to know what each product is and what rights its holder has. This chapter is a plain-English dictionary of the instruments and market terms behind a liquidity report. It covers deposits, loans, debt securities, Australian market instruments, reference rates, repurchase agreements, securitisation, derivatives, trade finance, wholesale funding, the counterparty types APS 210 uses, and currency terms.

Where a term has a role in APS 210, the reference is given. Where a fact comes from outside APS 210 (market conventions, product features, RBA arrangements), it is described as generally understood and should be checked against the issuer's or regulator's own documents.

## 4.1 Deposits

A **deposit** is money a customer places with a bank. The bank owes it back, so it is a liability of the bank and an asset of the customer. Deposits are the main funding source of most Australian banks. Liquidity rules care about two things: how quickly the customer can take the money out, and how likely they are to do so in a stress.

### Deposit types by access

| Type | What it is | Liquidity significance |
|---|---|---|
| **At-call deposit** (also demand deposit) | The customer can withdraw any amount at any time without notice, or on the same day | Can leave in a day, so counted as callable within the 30-day horizon. Retail demand deposits are in the retail run-off categories (APS 210 Att A para 34; Table 3) |
| **Transaction account** | An at-call account used for daily payments, where salary may be credited and bills paid | Often a *stable* deposit if fully covered by the Financial Claims Scheme and the account is transactional (Att A para 37(b)) |
| **Savings account** | An at-call account paying interest, used to hold money rather than make payments. Some pay bonus or promotional rates | A deposit that is heavily rate-driven or online scores points on the less stable scorecard (Att A paras 39, 40) |
| **Notice account** | An account where the customer must give notice, for example 31 days, before withdrawing | The notice period matters. A notice period of more than 30 days, with no right to withdraw sooner, can lead to exclusion from the 30-day outflows (Att A para 41) |
| **Term deposit** (also **fixed-term deposit**) | Money locked for an agreed term (for example three months or five years) at an agreed rate. Early withdrawal is usually allowed only with a penalty or not at all | Excluded from LCR outflows if residual maturity or notice is over 30 days and the depositor has no legal right to withdraw within 30 days, or early withdrawal carries a significant penalty materially greater than the loss of interest (Att A para 41). If the bank lets customers withdraw anyway, the whole category must be treated as demand deposits (Att A para 42). Hardship withdrawals are permitted under a defined policy without contaminating the pool (Att A para 43) |
| **Offset account** | A transaction or savings account linked to a home loan. The balance is netted against the loan balance when interest is calculated, so each dollar saves loan interest | For the bank it is a normal at-call deposit (a liability), even though the customer sees it as reducing the loan. Offset balances tend to be sticky because they save the customer interest at the loan rate, but the standard does not give a special rate; the stability tests in Att A paras 37 to 40 apply |

**Certificates of deposit** are covered in section 4.4.

### Deposit types by customer

APS 210 splits deposits by who owns them, because behaviour in a stress differs.

| Customer type | APS 210 treatment |
|---|---|
| **Retail** | Deposits placed by a **natural person** (an individual human, not a company). Deposits from companies, sole proprietorships and partnerships are wholesale (Att A para 34) |
| **SME** (small and medium enterprise) | A non-financial small business. Unsecured funding from SMEs can be treated as retail where the funds are managed as retail exposures and the total from that SME is less than A$2 million (consolidated where applicable) (Att A para 46). Above A$2 million, it is treated as non-financial corporate funding |
| **Corporate** (non-financial corporate) | Companies that are not financial institutions. Their deposits are *operational* or *non-operational* (below) |
| **Financial institution** | Defined below in 4.12 |

### Retail deposits: stable and less stable

Retail deposits are split into **stable** deposits (fully covered by the Financial Claims Scheme, with an established relationship or a transactional account, Att A para 37) and **less stable** deposits (the rest, Att A para 38). Less stable deposits are scored using the scorecard in Att A para 40: a balance above A$250,000 scores 2, being an online account scores 2, no established relationship scores 1, and being heavily rate-driven scores 1 (Att A Table 1; Chapter 5 shows the scorecard in full). A score of 0 to 2 gives a 10% run-off rate and 3 or more gives 25% (Att A Table 2).

### Insured vs uninsured

The **Financial Claims Scheme** (FCS) is the Australian Government's guarantee of deposits at ADIs. As generally understood, it protects deposits up to A$250,000 per account holder per ADI (the APS 210 scorecard uses the same AUD 250,000 figure, Att A para 40). **Deposit insurance** is the general term for such schemes. A balance above the limit is *uninsured* for the excess. The distinction matters because uninsured depositors have more to lose, so they move faster. APS 210 uses it in the stable deposit definition (Att A para 37) and in the wholesale lines: operational deposits fully covered by deposit insurance run off at 5%, not fully covered at 25%; non-operational deposits from non-financial corporates, sovereigns, central banks, public sector entities, multilateral development banks and SMEs above A$2m run off at 20% if fully insured and 40% if not (Att A Table 3).

### Operational deposits

An **operational deposit** is a deposit a customer leaves with the bank because it needs it to use the bank's services. Examples are balances kept to support cash management, clearing and custody. APS 210 allows operational treatment only if the customer has a substantive dependency on the ADI (Att A para 47). The qualifying activities are clearing, custody or cash management, provided under a legally binding agreement with termination subject to at least 30 days' notice or significant switching costs (Att A para 48). The deposits must be by-products of those services, not offered in the market just to earn interest, and priced without incentive to leave excess funds in the account (Att A para 49). Excess balances that could be withdrawn without damaging those activities do not qualify (Att A para 50).

> **Why it matters:** Whether a corporate deposit is operational or non-operational can move its LCR run-off rate between 25% (operational, not fully insured) and 40% (non-operational, not fully insured). The NSFR factor is 50% either way (Att C para 14(a), 14(b)). The classification is a data point your dashboard must carry on each account.

### Intermediated (brokered) deposits

An **intermediated deposit** (also called a brokered deposit, or a deposit through a platform) is money a person places through an intermediary, such as a broker, a platform or a superannuation fund, which then places it with the ADI. Under APS 210, the deposit is treated as a deposit from a financial institution unless, during the next 30 days, all of these conditions hold (Att A para 35):

1. the person keeps all legal rights over withdrawal or movement of the funds;
2. the person exercises those rights in practice and cannot transfer them to the intermediary;
3. there is clear and prominent disclosure that the funds will be placed with the ADI; and
4. the intermediary cannot make investment decisions about the deposit or withdraw it without the person's specific direction (apart from miscellaneous items like fees and taxes).

If all conditions are met, the ADI may treat the funds as the person's own and must be able to demonstrate this. The NSFR adds a layer: intermediated deposits that qualify as stable retail get 95%, and as less stable get 90%, only if the intermediary cannot replace the ADI without at least 12 months' notice; with six months' notice they get 50% (Att C paras 12(b), 13(b), 14(d)).

> **Watch out:** Failing the intermediated deposit tests moves money from a 5% to 10% run-off to a 100% run-off (financial institution deposits, Att A Table 3). This is a common source of large swings in an LCR.

## 4.2 Loans

A **loan** is money lent by the bank to a customer, to be repaid with interest. It is an asset of the bank. Liquidity rules care about the repayment schedule (cash coming in), whether the loan is performing, and whether the customer can draw more.

### Mortgages

A **mortgage** (also home loan) is a loan secured by a charge over property. If the borrower does not repay, the bank can sell the property to recover the debt.

| Term | Meaning |
|---|---|
| **Owner-occupier** | The borrower lives in the property |
| **Investor** | The property is rented out. Investor loans often carry a higher interest rate |
| **Principal and interest** (P&I) | Each repayment covers interest and also reduces the loan balance. This is an amortising loan. Cash comes in steadily as the balance falls |
| **Interest only** | The borrower pays only interest for a period, so the balance does not fall. All principal is due later |
| **Loan-to-valuation ratio** (LVR) | Loan amount divided by property value. A A$400,000 loan against a A$500,000 property is 80% LVR |
| **Standard residential property loan** | In the NSFR, a loan to an individual or individuals with an LVR of 80% or below (as defined under APS 112) and residual maturity of one year or more attracts the lower 65% RSF factor (Att C para 35(a)) |

```
LVR = Loan balance / Property value
Example: 400 / 500 = 80%
```

### Business lending

| Product | What it is |
|---|---|
| **Business loan** | A term loan to a company or sole trader with a fixed repayment schedule |
| **Overdraft** | A facility letting a transaction account go below zero up to a limit. Usually repayable on demand, with no fixed maturity |
| **Revolving credit facility** (RCF) | A facility where the borrower can draw, repay and redraw up to a limit during an agreed period |
| **Syndicated loan** | A large loan provided by several banks together. Each lender funds a share |
| **Margin lending** | A loan to buy shares or managed funds, secured by those assets. If the value falls, the lender makes a margin call and the borrower must add cash or assets or sell. The LCR treats collateralised loans for leveraged trading as a 50% inflow where backed by non-HQLA1 or non-HQLA2 collateral (Att A para 55 and Table 4; see Chapter 5) |

### Committed, uncommitted and revocable facilities

A **facility** is an agreement to lend up to a limit. How firmly the bank is bound decides its liquidity risk.

| Term | Meaning | APS 210 effect |
|---|---|---|
| **Committed facility** | The bank is contractually obliged to lend when asked, if conditions are met | The undrawn part runs off at 5% to 100% depending on customer and type (Att A Table 3) |
| **Uncommitted facility** | The bank may decline each request | Not a commitment, no committed-facility outflow |
| **Revocable facility** | The bank can cancel the undrawn limit at any time without notice | 5% run-off for revocable credit and liquidity facilities (Att A Table 3, other contingent funding obligations). NSFR: 5% for irrevocable and conditionally revocable; 1% for unconditionally revocable (Att C para 41, Table 1) |

### Credit facility vs liquidity facility

This distinction drives the LCR run-off rates.

- A **credit facility** (also general working capital facility) is a committed facility to fund a customer's general needs: for example a revolving credit facility for working capital. General working capital facilities for corporates must not be classified as liquidity facilities (Att A para 51).
- A **liquidity facility** is any committed, undrawn back-up facility used to refinance a customer's debt obligations when it cannot roll that debt over in financial markets. The amount treated as a liquidity facility is the outstanding debt issued by the customer maturing within 30 days that the facility backstops; extra capacity is treated as a credit facility (Att A para 51).
- Facilities to hedge funds, money market funds, special purpose funding vehicles and other vehicles used to finance an ADI's own assets are captured in full as liquidity facilities to a financial institution (Att A para 52).

| Undrawn committed facility to | Credit facility | Liquidity facility |
|---|---|---|
| Retail and SME customers | 5% | 5% |
| Non-financial corporates, sovereigns, central banks, PSEs | 10% | 30% |
| Banks and other ADIs subject to prudential supervision | 40% | 40% |
| Other financial institutions | 40% | 100% |
| Other legal entity customers | 100% | 100% |

(Att A Table 3. Chapter 5 covers it line by line.)

**Why the difference?** A liquidity facility is drawn exactly when markets are closed to the customer, so it is far more likely to be drawn in a stress than an ordinary working capital line.

> **Example:** Example Bank has A$5.0bn undrawn credit facilities to non-financial corporates (10% = 0.50) and A$1.0bn undrawn liquidity facilities to non-financial corporates (30% = 0.30). The A$1.0bn is smaller but its 30% rate shows how much more likely it is to be drawn per dollar.

### Performing vs non-performing

A **performing loan** is one where the borrower is making payments on time. A **non-performing loan** is one that is in default or well behind in payments (the definitions sit in APRA's credit risk standard APS 220, as generally understood and referenced in APS 210 Att C footnote 27). **Default** is failure to pay what is owed when it is due. For liquidity: only fully performing contractual inflows with no expected default in 30 days count as LCR inflows (Att A para 54), and non-performing loans get 100% RSF in the NSFR (Att C para 37(c)).

## 4.3 Debt securities: the basics

A **debt security** is a tradeable IOU. The issuer borrows money from investors and promises to pay interest and repay the principal. Because it is tradeable, the holder can sell it to someone else instead of waiting. That is why many debt securities count as liquid assets.

| Term | Meaning |
|---|---|
| **Bond** | A longer-term debt security, usually paying regular interest |
| **Note** | A medium-term debt security. Often used for "medium-term notes" |
| **Bill** | A short-term debt security issued at a discount to face value, with no interest payments. The investor profits from the difference between the price paid and the face value repaid |
| **Face value** (also nominal, par, principal) | The amount repaid at maturity |
| **Coupon** | The fixed (or floating) interest payment made on a bond, quoted as a percentage of face value per year |
| **Yield** | The return an investor earns if they buy at today's price and hold to maturity. It reflects coupon and price |
| **Maturity** | The date the principal is repaid |
| **Tenor** | The length of time from issue (or from now) to maturity. "A five-year tenor" |
| **Duration** | A single number describing how sensitive a bond's price is to a change in interest rates. A longer duration means a bigger price move for the same rate move. A bond with duration of 5 loses about 5% of its price if yields rise by one percentage point (an approximation) |
| **Basis point** (bp) | One hundredth of one percentage point: 0.01%. 100 basis points = 1%. A rate rising from 4.00% to 4.25% rose 25 basis points |
| **Credit rating** | An assessment of the issuer's ability to repay, from agencies such as S&P, Moody's and Fitch. The scale runs from AAA (strongest) down. APS 210 uses ratings in the HQLA tests, for example AA-, A+ to BBB- (Att A paras 10(b)(iii), 12(b)(ii)) |
| **Senior debt** | Debt that ranks ahead of subordinated debt if the issuer fails |
| **Subordinated debt** | Debt that ranks behind senior debt, so it is paid only after senior creditors. Banks issue it to count as Tier 2 capital |
| **Secured** | Backed by specific assets that the lender can claim if the borrower fails |
| **Unsecured** | Not backed by specific assets. The lender is an ordinary creditor |

### Price and yield move in opposite directions

A bond promises fixed cash flows. If market interest rates rise, new bonds pay more, so older bonds with lower coupons become less attractive and their price falls until the yield matches. When rates fall, existing bonds become more attractive and prices rise.

```
Price of a one-year zero-coupon bond = Face value / (1 + yield)
Face value A$100:
  yield 4.0%  ->  price = 100 / 1.04 = A$96.15
  yield 5.0%  ->  price = 100 / 1.05 = A$95.24   (yield up, price down)
  yield 3.0%  ->  price = 100 / 1.03 = A$97.09   (yield down, price up)
```

> **Why it matters:** This is why HQLA is counted at market value, not face value (Att A para 9), and why holding long-dated bonds as a liquidity buffer exposes the bank to price risk when rates rise. A forced sale in a stress may realise less than the carrying value. APS 210 handles this by adding haircuts on lower-quality assets and by requiring that HQLA2A has a proven record of limited price falls in stress (Att A para 10(a)(iii), 10(b)(v)).

## 4.4 Australian instruments

This section gives one or two sentences on each instrument you will meet in Australian bank data. Descriptions are as generally understood.

| Instrument | What it is | Liquidity relevance |
|---|---|---|
| **Australian Government Securities (AGS)** | Debt issued by the Australian Government: Treasury Bonds (longer-term, paying a coupon) and Treasury Notes (short-term, discount) (issuer: the Australian Office of Financial Management on behalf of the Commonwealth; check aofm.gov.au) | Zero risk weight and deep markets, so they qualify as HQLA1 if the conditions in Att A para 9(c) are met. Also eligible for repo with the RBA |
| **Semi-government securities** | Bonds issued by state and territory governments, or their treasury corporations ("semis") | As generally understood, in Australian dollars these are treated as HQLA1 by APRA. Confirm in APRA's guidance APG 210 |
| **Bank bill** | A short-term bill (typically 30 to 180 days) accepted or endorsed by a bank. It is a discount instrument | Bank bills issued by ADIs are eligible liquid assets under MLH (Att B para 2(e)) but are not HQLA under the LCR, because they are obligations of financial institutions (Att A para 9(c)(iv), 10(a)(iv)) |
| **Negotiable certificate of deposit** (NCD or CD) | A tradeable certificate showing that a deposit has been made with a bank for a fixed term. The holder can sell it before maturity | Treated as unsecured wholesale funding if issued by the ADI: debt maturing in 30 days runs off at 100% (Att A Table 3) |
| **Commercial paper** (CP) | Short-term unsecured debt issued by corporates or banks, normally under 12 months | Corporate commercial paper, if plain vanilla and highly rated and not issued by a financial institution, can be HQLA2A (Att A para 10(b)) or HQLA2B (Att A para 12(b)) |
| **Medium-term note** (MTN) | A bond-like note issued under a programme, with maturities from a few years to ten | Bank-issued MTNs are unsecured wholesale funding. Maturities of one year or more attract 100% ASF (Att C para 11(c)) |
| **Covered bond** | A bond issued by a bank and backed by a dedicated pool of assets (typically mortgages) that stays on the bank's balance sheet. If the bank fails, holders have a claim on the pool *and* on the bank. Australian ADIs can issue them subject to a limit set by the Banking Act (check Banking Act 1959 and APRA for the cap) | Covered bonds issued by someone else can be HQLA2A if rated at least AA- (Att A para 10(b)); not if issued by the ADI itself or its associated entities (Att A para 10(b)(ii)). The assets backing them are encumbered (Att C footnote 21) |
| **Residential mortgage-backed security** (RMBS) | A bond backed by a pool of home loans, whose payments flow through to investors | Can be HQLA2B with a 25% haircut if strict conditions are met, including AA rating or better, pool limited to residential mortgages, average LVR of 80% or below, and not originated by the ADI (Att A para 12(a)) |
| **Asset-backed security** (ABS) | A bond backed by a pool of other loans or receivables, such as car loans, equipment finance or credit cards | Not HQLA under Att A. Maturing ADI-issued ABS run off at 100% (Att A Table 3) |
| **Asset-backed commercial paper** (ABCP) | Short-term paper issued by a conduit that holds a pool of assets. It must be rolled over often | ABCP, ABS, covered bonds and other structured financing issued by the ADI itself run off at 100% when maturing (Att A Table 3) |
| **Hybrid** | A security with features of both debt and equity, which can convert to shares or be written off if the bank is in trouble. Banks issue them to count as Additional Tier 1 capital | Capital instruments with at least one year to run get 100% ASF (Att C para 11(a), 11(b)) |

## 4.5 Reference rates

A **reference rate** (or benchmark rate) is a published interest rate that other contracts are priced from.

| Rate | What it is |
|---|---|
| **Cash rate target** | The RBA's target for the **cash rate**, the interest rate on unsecured overnight loans between banks. The RBA Board sets the target and announces changes. The cash rate is the main policy rate in Australia (RBA, rba.gov.au) |
| **Overnight rates** | Rates on borrowing for one night. The **cash rate** is the overnight interbank rate. The RBA publishes a measure of it, the AUD Overnight Index Average (AONIA) (RBA website) |
| **Bank bill swap rate (BBSW)** | A benchmark for short-term, term-based (for example one-month, three-month, six-month) bank credit rates in Australia, calculated from trades in bank bills. It is used to price loans, bonds and derivatives. As generally understood, the benchmark is administered by ASX and regulated under Australian law; confirm on asx.com.au and asic.gov.au. |
| **Exchange Settlement rate** | The rate the RBA pays on Exchange Settlement balances held by banks at the RBA. As generally understood it is set at a margin below the cash rate target (RBA, rba.gov.au) |

**Why they matter for liquidity data:** funding costs and loan yields are quoted as a margin over these rates (for example BBSW plus 90 basis points). A change in the cash rate target flows into deposit rates, lending rates and the profitability of the liquid asset portfolio.

## 4.6 Secured funding: repurchase agreements and related transactions

**Secured funding** is borrowing where the lender takes specific assets as security. APS 210 splits funding into unsecured and secured because lenders against good collateral are more willing to keep lending in a stress (Att A Table 3).

### Repurchase agreement (repo)

A **repurchase agreement** (**repo**) is a sale of a security with a promise to buy it back at a set price on a set date. In economic substance it is a short-term secured loan: the seller gets cash now, the buyer holds the security as collateral, and the repurchase price includes interest.

Step by step, using numbers:

1. **Day 0, start leg.** Example Bank owns A$100.0m (market value) of Australian Government bonds. It needs cash. It sells them to a counterparty for A$98.0m cash. (The A$2.0m gap is the haircut, explained below.)
2. **During the repo.** The counterparty holds the bonds as **collateral**, which is an asset pledged to secure an obligation. If Example Bank defaulted, the counterparty could keep and sell them.
3. **Day 30, end leg.** Example Bank buys the bonds back for A$98.0m plus interest. At an interest rate of 4.00% per year over 30 days: 98.0 x 4.00% x 30/365 = A$0.322m. It pays A$98.322m and gets the bonds back.

```
Interest = Cash lent x Rate x Days / 365
         = 98.0m x 0.04 x 30 / 365 = A$0.322m
Repurchase price = 98.0m + 0.322m = A$98.322m
```

A repo is a borrowing for the seller: a liability. For the buyer, the same trade is a **reverse repo**: it lends cash and takes the security as collateral. The reverse repo is an asset (a secured loan).

| | Repo | Reverse repo |
|---|---|---|
| Whose view | The borrower of cash (the seller of securities) | The lender of cash (the buyer of securities) |
| Balance sheet | Liability; the security stays on the balance sheet but is encumbered | Asset (loan secured by collateral) |
| LCR | Outflow when the repo matures, at a rate depending on the collateral (Att A Table 3) | Inflow when it matures, at a rate depending on collateral (Att A Table 4) |

Securities received in a reverse repo that have not been rehypothecated, and are legally and contractually available for the ADI's use, may be counted in its HQLA stock (Att A para 23).

### LCR run-off rates for secured funding

The better the collateral, the more likely the lender is to roll the funding over, so the lower the run-off rate (Att A Table 3):

| Secured funding backed by | Run-off |
|---|---|
| HQLA1, any counterparty | 0% |
| HQLA2A, any counterparty | 15% |
| Other transactions with domestic sovereigns, PSEs (not the RBA) or MDBs with a risk weight of 20% or lower | 25% |
| RMBS eligible for HQLA2B | 25% |
| Other HQLA2B | 50% |
| All other secured funding | 100% |

### Haircut and margin

A **haircut** has two uses in this guide. Do not mix them up.

1. *Market haircut in a repo:* the discount between the market value of the collateral and the cash lent. A A$100.0m bond lent against A$98.0m cash has a haircut of 2.0%. It protects the lender if the collateral loses value before it can be sold.
2. *Regulatory haircut in the LCR:* the percentage taken off the market value of an asset to reflect its price risk when counting HQLA. HQLA1: none; HQLA2A: 15%; HQLA2B: 25% for eligible RMBS and 50% for corporate debt and equities (Att A paras 9, 10, 12).

**Margin** in a repo context is the extra collateral required to keep the loan covered. A **margin call** is a demand for more collateral (or cash) when the value of the collateral falls or the exposure rises.

> **Example:** A repo is done at a 2% haircut. Bond value falls by 3% in a day. A$100.0m collateral is now worth A$97.0m against A$98.0m cash lent. To restore the 2% haircut the collateral must again be worth 98.0 / 0.98 = A$100.0m, so the lender issues a margin call for A$3.0m more collateral (or A$3.0m of cash returned).

### Related terms

| Term | Meaning |
|---|---|
| **Collateral** | An asset pledged to secure an obligation |
| **Rehypothecation** | The recipient of collateral re-using it, for example pledging it onwards to a third party. Assets received in reverse repo count as HQLA only if not rehypothecated (Att A para 23). If reverse repo collateral is rehypothecated for 30 days or more to cover short positions, the reverse repo is assumed to roll over with zero inflow (Att A para 56) |
| **Securities lending** (also securities borrowing) | A lender temporarily gives securities to a borrower for a fee, usually against collateral. Maturing securities borrowing secured by HQLA1 is assumed to roll over, 0% inflow (Att A para 55) |
| **Collateral swap** | An exchange of one type of security for another, for example the bank gives lower-quality securities and receives government bonds, for a term and a fee. Used to improve the quality of liquid assets. Collateral swaps within 30 days must be unwound when applying the HQLA caps (Att A paras 7, 8). APRA may require the ADI to include their net cash flow in its LCR if it actively uses them for liquidity (Att A para 33) |
| **General collateral** (GC) | Repo in which the lender accepts any security from an agreed basket (such as government bonds), as opposed to a *special* repo where a specific security is requested. Defined here as generally understood in markets; not defined in APS 210 |
| **Buyback** | When an issuer repurchases its own debt from investors before maturity, for example to support market liquidity. APS 210 includes buybacks of domestic Australian debt securities at 10% for short-term and 5% for long-term securities, unless otherwise agreed with APRA (Att A Table 3) |
| **Short position** | Selling a security the seller does not own, having borrowed it, in expectation of buying it back later |
| **Securities financing transaction** | The group term for repos, reverse repos, securities lending and borrowing, and collateral swaps (Att C para 25) |
| **Encumbered asset** | An asset pledged or otherwise committed so that it cannot be freely sold or used. **Unencumbered** means free of such claims. HQLA must be unencumbered (Att A para 22(b), 23) |
| **Monetise** | Turn an asset into cash, by selling it or by repo |

## 4.7 Securitisation

**Securitisation** is the process of pooling loans, selling them (or the cash flows) to a vehicle, and having the vehicle issue bonds to investors that are repaid from the loans' payments.

| Term | Meaning |
|---|---|
| **Originator** | The institution that made the loans being securitised, often the bank |
| **Special purpose vehicle** (SPV) | A separate legal entity set up to hold the loans and issue the bonds. It has no other business. Also called a special purpose funding vehicle |
| **Tranche** | A slice of the bonds with a different ranking. The **senior** tranche is paid first and absorbs losses last; **mezzanine** and **junior** (equity) tranches are paid later and take losses first. Senior tranches get higher credit ratings |
| **Warehouse** | A temporary funding facility, often from banks, that holds loans while a pool is built up, before a bond issue ("term deal") refinances it |
| **Self-securitisation** (internal securitisation) | The bank securitises its own loans and keeps all the resulting bonds on its own books rather than selling them to investors |
| **Structured investment vehicle** (SIV) | An investment vehicle that funds longer-term assets with short-term paper. Prominent in the 2007 to 2009 period; the LCR assumes loss of funding at 100% for SPVs, conduits and SIVs that cannot refinance (Att A Table 3) |

**Why do banks securitise?** To obtain funding from investors that is secured on the loans; to move assets off the balance sheet and reduce capital required (if the true-sale conditions are met); and to diversify funding.

**Why do banks self-securitise?** To create assets that can be used as collateral with the RBA. As generally understood, self-securitised RMBS were eligible collateral for repos with the RBA and were relevant to the Committed Liquidity Facility (CLF). APS 210 refers to "self-securitised assets, eligible as CLF collateral" in the NSFR at a 10% RSF factor (Att C para 32(b)). The CLF is described in Att A paras 13 to 21 and, as generally understood, APRA reduced CLF allocations to zero by the end of 2022 (verify on apra.gov.au).

**Treatment in APS 210:** if the ADI is the originator and meets the operational requirements for regulatory capital relief under APS 120, it may exclude the assets and liabilities of the SPVs from MLH and NSFR calculations. For the LCR, it must include the SPVs' cash flows (APS 210 para 5).

## 4.8 Derivatives

A **derivative** is a contract whose value depends on an underlying variable: an interest rate, exchange rate, bond price or commodity price. Banks use derivatives to hedge their own risks and to serve customers.

| Derivative | What it is | Example |
|---|---|---|
| **Swap** | An agreement to exchange cash flows over time. An **interest rate swap** exchanges fixed interest payments for floating ones | The bank pays fixed 4.5% and receives BBSW on a A$100m notional, to convert floating-rate funding into fixed |
| **Forward** | A contract to buy or sell something at a fixed price on a future date | Agreeing today to buy US$10m at A$1 = US$0.65 in 3 months |
| **Option** | A contract giving the buyer the right, but not the obligation, to buy or sell at a set price. The seller must perform if asked | A right to buy A$ at a set rate |
| **FX swap** | Two exchanges of currencies: swap now at the spot rate and swap back at a set future rate. Economically a collateralised loan in one currency against another | Borrow US$ for 3 months against A$ |
| **Cross-currency swap** | A longer-term swap where two currencies are exchanged and interest in each is paid along the way, then exchanged back at maturity. Australian banks use them to turn foreign-currency bond funding into A$ funding | Issue a bond in euros, swap into A$ |

### Derivative measurement terms

| Term | Meaning |
|---|---|
| **Notional** | The reference amount on which payments are computed. Not the amount at risk |
| **Mark-to-market** | Revaluing a contract at today's market prices |
| **Replacement cost** | The cost of replacing the contract with a new one today, equal to its mark-to-market value when positive. APS 210 bases NSFR derivative assets and liabilities on replacement cost (Att C paras 9, 27) |
| **Netting** | Offsetting amounts owed in both directions with the same counterparty so only the net is paid or counted |
| **Master netting agreement** | A legal agreement that lets all derivative contracts with one counterparty be netted together, including if the counterparty fails. In the LCR, derivative amounts are taken net by counterparty only where a valid master netting agreement exists (Att A Table 3, footnote 5) |
| **Central counterparty** (CCP) | A clearing house that stands between buyer and seller in a trade so each deals with the CCP rather than with each other. It requires margin from both sides. Contributions to a CCP's default fund get 85% RSF (Att C para 36(a)) |

### Initial margin and variation margin

| | Initial margin | Variation margin |
|---|---|---|
| Purpose | A buffer against potential future losses if a counterparty defaults | Settles day-to-day changes in the contract's market value |
| When paid | At the start of the trade, and updated | Daily (or more often) as value moves |
| Direction | Posted by both sides in many arrangements, held aside | Paid by the side that is losing |
| NSFR | Posted initial margin gets 85% RSF (Att C para 36(a)) | Variation margin posted is deducted from derivative liabilities (Att C para 10); cash variation margin received can offset derivative assets only if conditions are met (Att C para 28) |

### Why derivatives create liquidity needs

1. **Variation margin calls.** If the market moves against the bank, it must post cash or securities, often the next day. The LCR covers this with outflows for collateral valuation changes (Att A Table 3).
2. **Downgrade triggers.** A **downgrade trigger** is a clause requiring extra collateral if the bank's credit rating falls. The LCR assumes a 3-notch downgrade and a 100% outflow of the extra collateral required (Att A Table 3).
3. **Collateral substitution** clauses that let the counterparty swap HQLA for non-HQLA, and **excess collateral** held that the counterparty can call back, are also outflows at 100% (Att A Table 3).
4. **Initial margin** posted is a locked-up asset that cannot be used for other purposes.
5. **Net cash payments** under the contracts themselves in the next 30 days (Example Bank: A$0.3bn).

## 4.9 Trade finance, guarantees and letters of credit

| Instrument | What it is | Liquidity relevance |
|---|---|---|
| **Trade finance** | Products that support the buying and selling of goods across borders: letters of credit, guarantees, documentary collections, import and export loans | The LCR outflow is the average of actual monthly net outflows in a recent 12-month period (Att A Table 3). The NSFR applies 100% to the actual net outflows in the most recent 12-month period (Att C para 42) |
| **Guarantee** | The bank promises to pay a third party if its customer fails to perform | Guarantees and letters of credit other than trade finance run off at 50% of the average of actual monthly net outflows in a recent 12-month period (Att A Table 3) |
| **Letter of credit** (LC) | The bank's promise to pay an exporter once the right shipping documents are presented | Same as above |

**Contingent liability** is the umbrella term: an obligation that becomes real only if something happens. Guarantees and letters of credit are contingent liabilities. They sit in the notes, not on the balance sheet.

## 4.10 Wholesale funding

**Wholesale funding** is money raised from institutional investors and other financial institutions rather than from households and small businesses. It includes debt securities issued, interbank deposits, large corporate deposits and repo.

| Split | Meaning | Why it matters |
|---|---|---|
| **Short-term vs long-term** | Under one year vs one year or more. In the NSFR: 100% ASF at one year or more, 50% from six months to under one year, 0% under six months (Att C paras 11(c), 14(f), 15(a)) | Short-term funding must be refinanced soon |
| **Domestic vs offshore** | Raised from Australian investors in A$ vs raised abroad, often in foreign currency | Offshore funding opens access to bigger investor pools but brings currency mismatch and exposure to overseas market conditions. The ADI must manage currency liquidity needs separately (APS 210 para 43) |

**Refinancing risk** (also **rollover risk**) is the risk that when a borrowing matures the bank cannot replace it with new funding, or only at a much higher cost. A bank with a lot of debt maturing in the same month has high rollover risk. The reason maturity matters is that the principal of every maturing debt must be found from somewhere on a specific date. A bank that funds 10-year mortgages with 3-month paper must roll the paper about 40 times.

> **Why it matters:** The LCR counts all wholesale funding maturing within 30 days at 100% (Att A para 45; Table 3). The NSFR rewards funding of one year or more. Your data should carry the *residual* maturity of every wholesale funding line, and the first-possible-redemption date where the investor has an option (Att A para 45; Att C para 8).

## 4.11 Counterparty types used in APS 210

APS 210 classifies customers because liquidity behaviour differs by type. Your data model needs a counterparty type field consistent with these.

| Type | Meaning in APS 210 | Reference |
|---|---|---|
| **Natural person** | An individual human being. Retail deposits are deposits placed by a natural person | Att A para 34 |
| **SME** | A small or medium enterprise. Funding from non-financial SMEs managed as retail, with total funding from the SME under A$2 million, can be treated as retail. Where this definition cannot be applied due to lack of liability products, the definition in paragraph 40 of APS 113 may be used | Att A para 46 and footnote 7 |
| **Non-financial corporate** | A company or entity that is not a financial institution. APS 210 uses the term in Table 3 and in the inflow rules but does not define it in the text. It is treated as wholesale, with run-offs such as 20% or 40% for non-operational deposits | Att A Table 3; para 62 |
| **Sovereign** | A national government. Securities issued by or guaranteed by sovereigns can be HQLA1 if they meet the tests | Att A para 9(c) |
| **Central bank** | The monetary authority, for Australia the RBA. Balances at the central bank are HQLA1 to the extent they can be drawn in stress | Att A para 9(b) |
| **Public sector entity** (PSE) | An entity owned or controlled by government, such as a state government body. Defined by reference to the capital standards (APS 112), not in APS 210 itself, as generally understood | Att A para 9(c) |
| **Multilateral development bank** (MDB) | An international development institution owned by several countries, such as the World Bank. Defined by reference to APS 112 (as generally understood) | Att A para 9(c) |
| **Financial institution** | "For the avoidance of doubt, a financial institution includes a money market corporation, finance company, friendly society and the trustee of a superannuation/pension fund, public unit trust/mutual fund or cash management trust" | APS 210 para 10(b) |

The definition of financial institution is an inclusive list, not an exhaustive one ("for the avoidance of doubt ... includes"). Banks and other ADIs are also financial institutions. Hedge funds and money market funds appear in Att A para 52. Deposits from financial institutions run off at 100% unless they are operational deposits (Att A Table 3). Associated entities (as defined in section 50AAA of the Corporations Act 2001, APS 210 para 10(a)) of a financial institution are also excluded from HQLA lists (Att A paras 9(c)(iv), 10).

## 4.12 Currency terms

| Term | Meaning |
|---|---|
| **AUD** | The Australian dollar |
| **All-currencies LCR** | The LCR calculated across all currencies, with foreign currency amounts converted to A$. A locally incorporated ADI must meet 100% on this basis (APS 210 para 55(a)) |
| **AUD LCR** | The LCR calculated using only the Australian-dollar items. A locally incorporated ADI must also meet 100% on this basis (APS 210 para 55(a)) |
| **Foreign ADI** | A foreign bank's branch in Australia. It must meet at least 40% on an all-currencies basis (APS 210 para 55(b)) |
| **Significant currency** | A currency in which the ADI has material liabilities or activity. As generally understood, the Basel liquidity framework defines this as a currency where liabilities are 5% or more of total liabilities; APS 210 refers to "material activities" in a currency (para 43(c)). Confirm the Basel threshold on bis.org before using it |
| **Currency mismatch** | A situation where assets and liabilities in a currency do not match, for example borrowing US dollars and lending Australian dollars. The ADI must assess its aggregate foreign-currency liquidity needs, set an acceptable level of mismatch, and maintain liquid assets consistent with its needs by currency (APS 210 para 43) |

The Committed Liquidity Facility could only be used for Australian-dollar shortfalls (Att A para 14). Foreign currency is a reason an AUD LCR is reported separately from the all-currencies LCR.

## Key points

- Deposits differ by access (at-call, notice, term), by customer (retail, SME, corporate, financial institution) and by insurance (Financial Claims Scheme up to A$250,000 per account holder per ADI). All three drive LCR run-off and NSFR factors.
- Term deposits with a residual maturity over 30 days and no right of early withdrawal (or a penalty well above lost interest) are excluded from LCR outflows; if the bank lets customers out anyway the entire category is treated as demand (APS 210 Att A paras 41 to 42).
- Intermediated deposits fall to 100% run-off unless the four tests in Att A para 35 are met.
- A committed facility is a firm promise, a revocable one is not. A liquidity facility backs up a customer's debt rollover and runs off at higher rates than a credit facility; facilities to hedge funds, money market funds and funding vehicles are always liquidity facilities to financial institutions (Att A paras 51, 52).
- Bond prices and yields move in opposite directions. HQLA is counted at market value, not face value.
- A repo is a secured loan: a sale of securities with an agreed repurchase. The haircut protects the lender; the better the collateral, the lower the LCR run-off (HQLA1 0%, HQLA2A 15%).
- Securitisation moves loans into a special purpose vehicle that issues tranches of bonds; self-securitisation keeps the bonds to make collateral. For LCR, the SPV's cash flows are included (APS 210 para 5).
- Derivatives create liquidity needs through margin calls and downgrade triggers even when their balance sheet value is small. Notional is not cash at risk.
- Wholesale funding matters by residual maturity; rollover risk is the risk of failing to refinance.
- The counterparty type of every position drives its treatment. APS 210 defines financial institution inclusively (para 10(b)) and SME by the A$2 million test (Att A para 46).

## Check your understanding

**1. A retail customer has A$300,000 in an online savings account paying a promotional rate, opened last month, with no other products at the bank. Using the scorecard in Att A para 40, what is the score and the run-off rate? Assume the Financial Claims Scheme limit is A$250,000.**
**Answer:** Balance over A$250,000: 2. Online account: 2. No established relationship: 1. Heavily rate-driven: 1. Total 6. A score of 3 or more gives a 25% run-off rate (Att A Table 2). Run-off = 25% x A$300,000 = A$75,000. (Strictly the scorecard applies to the less stable portion of the deposit. This account clearly fails the stable tests.)

**2. Example Bank swaps A$2.0bn of at-call financial institution deposits for A$2.0bn of retail term deposits over 30 days with no early withdrawal right. What happens to the 30-day outflow from this change, and why?**
**Answer:** Before: 2.0 x 100% = 2.00 outflow (financial institution deposits, Att A Table 3). After: retail term deposits with residual maturity over 30 days and no right to withdraw are excluded (0%) (Att A para 41). Outflows fall by 2.00 from 13.45 to 11.45. Net outflows are 11.45 - 1.90 = 9.55, so LCR = 17.0 / 9.55 = 178.0%.

**3. A bank runs a repo: it sells A$50.0m of government bonds for A$49.0m cash for 14 days at 4.50% per year. Calculate the haircut, the interest, and the repurchase price.**
**Answer:** Haircut = (50.0 - 49.0) / 50.0 = 2.0%. Interest = 49.0m x 0.045 x 14 / 365 = A$0.0846m (about A$84,600). Repurchase price = 49.0 + 0.0846 = A$49.0846m.

**4. A zero-coupon one-year bill has face value A$100. Calculate its price at a yield of 4% and at 6%. What happens to the price when the yield rises?**
**Answer:** At 4%: 100 / 1.04 = A$96.15. At 6%: 100 / 1.06 = A$94.34. The price falls as the yield rises, which is why a bank forced to sell bonds after rates have risen realises less.

**5. Explain the difference between a credit facility and a liquidity facility. Example Bank has A$5.0bn undrawn credit facilities and A$1.0bn undrawn liquidity facilities to non-financial corporates. Calculate the LCR outflow.**
**Answer:** A credit facility is a committed line for general or working capital purposes; a liquidity facility is a committed back-up line to refinance a customer's maturing debt when it cannot roll over in markets (Att A para 51). Outflow = 5.0 x 10% + 1.0 x 30% = 0.50 + 0.30 = 0.80 (Att A Table 3).

**6. A fund manager places a client's money in a deposit at an ADI. The manager can withdraw the money without the client's instruction. How is the deposit treated for the LCR, and why?**
**Answer:** The condition in Att A para 35(d) fails (the intermediary can withdraw funds without specific direction), so the deposit is treated as a deposit from a financial institution rather than a retail deposit. That means a 100% run-off rate (Att A Table 3) instead of 5% or 10%, because intermediated money is more likely to move together and fast.

**7. Why does a derivative with a market value of only A$1m possibly require a bank to hold much more liquidity than A$1m?**
**Answer:** The balance sheet shows only today's market value. A bank may face large variation margin calls if the market moves against it, and extra collateral if its credit rating is downgraded (APS 210 Att A Table 3 includes both). The notional can be hundreds of millions of dollars, and the potential cash demand scales with the movement in the underlying. The accounting value understates liquidity risk.

**8. A bank has A$4.0bn of unsecured financial institution deposits maturing in 20 days and A$4.0bn maturing in 200 days. What is the LCR outflow for each, and the NSFR ASF factor for each?**
**Answer:** The first matures inside the 30-day window: 100% LCR outflow = 4.00 (Att A para 45; Table 3). The second is outside the window: 0% LCR outflow. NSFR: funding from financial institutions with residual maturity under six months gets 0% ASF (Att C para 15(a)); 200 days is about 6.6 months, so it falls in the six months to under one year band at 50% ASF = 2.00 (Att C para 14(f)). The 20-day funding gets 0 ASF.

---

# Chapter 5: The Liquidity Coverage Ratio, line by line

The Liquidity Coverage Ratio (LCR) is the most detailed liquidity rule in Australian banking. It is set out in Attachment A of APRA Prudential Standard APS 210 Liquidity (the July 2025 version, Federal Register of Legislation F2025L00653). This chapter follows Attachment A in its own order. Every rule and rate carries a reference in the form `(Att A para 37)` or `(Att A Table 3)`. Main-body references are written `(APS 210 para 55)`.

## 1. What the LCR is, who must meet it, and at what level

### 1.1 The idea in one paragraph

A bank takes in money that customers can ask for back quickly, and it lends or invests much of that money for longer. If many customers ask for their money at once, the bank needs cash fast. The LCR asks a single question: *does the bank hold enough easily sold assets to pay out the cash it would lose over 30 days of severe stress?*

The objective, in the standard's words, is to ensure that an authorised deposit-taking institution (ADI) "maintains an adequate level of unencumbered HQLA that can be converted into cash to meet its liquidity needs for a 30 calendar day time period under a severe liquidity stress scenario" (Att A para 1).

Define the terms in that sentence:

- **ADI (authorised deposit-taking institution):** a bank, credit union or building society that APRA (the Australian Prudential Regulation Authority) has authorised to take deposits. Chapter 2 covers ADIs in full.
- **HQLA (high-quality liquid assets):** assets that can be turned into cash quickly, in large size, with little loss of value, even in a crisis. The categories are defined in sections 3 to 5 below.
- **Unencumbered:** free of any legal or practical claim by someone else. An asset pledged as collateral to a lender is *encumbered*. The bank cannot also sell it to raise cash. (Att A paras 22 to 23.)
- **Stress scenario:** a set of assumed bad events, written down by the regulator, that the bank must be able to survive. Section 1.3 describes this one.

### 1.2 Who must meet it, and at what level

APRA sorts every ADI into one of two classes. A locally incorporated ADI is classified by APRA as either a Liquidity Coverage Ratio ADI (LCR ADI) or a Minimum Liquidity Holdings ADI (MLH ADI) (APS 210 para 52). A foreign ADI (an Australian branch of an overseas bank) is an LCR ADI unless APRA determines that it is an MLH ADI, taking account of its size and complexity with respect to liquidity risk (APS 210 para 53). Chapter 7 covers MLH ADIs.

An ADI must meet the minimum requirements of its class "on a continuous basis, absent a situation of financial stress" (APS 210 para 54).

An LCR ADI must maintain an adequate level of unencumbered HQLA to meet its liquidity needs for a 30 calendar day period under a severe stress scenario (APS 210 para 55). The minimums are:

| ADI type | Minimum LCR | Basis | Reference |
|---|---|---|---|
| Locally incorporated ADI | 100% | Australian dollar (AUD) LCR **and** all currencies LCR, each separately | (APS 210 para 55(a)) |
| Foreign ADI | 40% | All currencies basis only | (APS 210 para 55(b)) |

APRA may require an LCR ADI to hold a higher minimum LCR if it has concerns about the ADI's liquidity risk profile or the quality of its liquidity risk management (APS 210 para 56).

> **Watch out:** "Both bases" matters. A locally incorporated ADI can fail the AUD LCR while passing the all currencies LCR. For example, it might hold plenty of United States dollar (USD) assets but be short of AUD assets. Section 21 explains the two bases.

### 1.3 The stress scenario in words

Attachment A does not describe the scenario as a story. It builds the scenario from the run-off and inflow rates in Tables 3 and 4 and the paragraphs around them. Reading those rates together, the assumed 30 days look like this (this is a plain-English summary of the effect of the rates, not a quotation):

1. Some customers withdraw deposits. Stable retail deposits lose a small share (5%). Less stable retail deposits lose more (10% or 25%). Wholesale customers lose far more (20% to 100%) (Att A Table 3).
2. Lenders refuse to roll over short-term unsecured debt maturing in the window (100%) (Att A Table 3).
3. Lenders against weaker collateral withdraw funding on secured borrowings (up to 100%), while lenders against government securities keep rolling (0%) (Att A Table 3).
4. Customers draw on undrawn promises to lend (5% to 100%, depending on who the customer is) (Att A Table 3).
5. A downgrade of the ADI by three notches forces it to post more collateral on derivatives (Att A Table 3).
6. Money owed to the ADI still arrives, but only part of it counts as a real inflow, because the ADI is also assumed to keep lending (Att A paras 61 to 62), and total inflows are capped (Att A para 30).

The standard calls this a "severe liquidity stress scenario" (Att A para 1). In the main body it is called a "severe stress scenario" (APS 210 para 55).

### 1.4 The two components and the formula

The LCR has two components: the value of the stock of HQLA, and total net cash outflows, "calculated according to the scenario parameters set out in this Attachment" (Att A para 2). The formula is (Att A para 3):

```
              Stock of HQLA
LCR  =  ------------------------------------------------------
        Total net cash outflows over the next 30 calendar days
```

- The top line is the **numerator**: what the bank *has* (sellable assets).
- The bottom line is the **denominator**: what the bank is assumed to *lose* in 30 days, net of the money it is assumed to receive.
- A ratio of 100% means the stock exactly covers the net outflows. Above 100% means there is a surplus.

### 1.5 The buffer

An ADI "must include an appropriate buffer of HQLA over the LCR requirement in line with its liquidity risk tolerance" (Att A para 4). Liquidity risk tolerance is the amount of liquidity risk the Board is willing to accept (Chapter 8 covers it). In practice a bank targets an LCR comfortably above 100% so that ordinary daily movements never push it below the minimum.

> **Why it matters:** The 100% minimum applies "on a continuous basis" (APS 210 para 54). A bank that runs at exactly 100% will breach on the first day a large deposit leaves. Holding a buffer costs money, because liquid assets earn less than loans. The buffer is a trade-off set by the Board.

### 1.6 Using the buffer in stress, and telling APRA

In a real period of financial stress the bank may sell part of its HQLA and/or draw on its Committed Liquidity Facility (CLF) with the Reserve Bank of Australia (RBA), and use the cash to meet outflows. As a result, "the LCR may fall below the minimum level" required by APS 210 para 55 (Att A para 5). The standard accepts this. That is the purpose of the buffer: it is meant to be *used*.

The duty that goes with it: "An ADI must inform APRA immediately in the event of an actual breach of its LCR requirement or if it becomes aware of circumstances that may result in a breach of its LCR requirement" (Att A para 5). Note the second limb. A bank must report a *likely* breach, not only an actual one.

The CLF was a facility from the RBA that counted towards the LCR. Section 8 explains it, including its current status.

## 2. A map of Attachment A

| Part of Attachment A | Paragraphs | What it does | Section of this chapter |
|---|---|---|---|
| Objective, formula, buffer, use in stress | 1 to 5 | Defines the ratio | 1 |
| Eligible HQLA, caps, adjusted amounts | 6 to 8 | Sets the numerator's structure | 3, 6 |
| HQLA1 | 9 | Best assets, no haircut | 4 |
| HQLA2A | 10 to 11 | Good assets, 15% haircut | 5 |
| HQLA2B | 12 | Weaker assets, 25% or 50% haircut | 5 |
| Committed Liquidity Facility | 13 to 21 | Alternative liquid asset treatment | 8 |
| Operational requirements | 22 to 25 | Rules for holding the stock | 9 |
| Level 2 and offshore | 24, 26 to 29 | Group-wide testing | 10 |
| Net cash outflows | 30 to 33 | Denominator formula, 75% cap | 11 |
| Retail deposits | 34 to 43 | Stable, less stable, scorecard, term deposits | 12 |
| Unsecured wholesale funding | 44 to 50 | Definitions, SMEs, operational deposits | 13 |
| Liquidity facilities | 51 to 52 | Credit versus liquidity facility | 16 |
| Run-off rates (secured funding, structured financing, derivatives, facilities, other) | 53, Table 3 | Every outflow rate | 14 to 17 |
| Cash inflows | 54 to 66, Table 4 | Every inflow rate | 18 |
| Example Bank calculation and what-ifs | n/a | Worked answer | 19, 20 |
| AUD versus all currencies, foreign ADI | APS 210 para 55 | Two bases | 21 |
| Common mistakes, data fields | n/a | Practice | 22, 23 |

## 3. The stock of HQLA: the structure

### 3.1 What "high-quality liquid" means

An asset is liquid when it can be turned into cash quickly, in size, without a large loss. Chapter 1 gives the three tests: speed, certainty of value and depth of market. The standard turns these into a checklist that recurs in every HQLA paragraph:

- "traded in large, deep and active repo or cash markets characterised by a low level of concentration" (Att A paras 9(c)(ii), 10(a)(ii), 10(b)(iv), 12(a)(iii), 12(b)(iii), 12(c)(v));
- a "proven record as a reliable source of liquidity in the markets (repo or sale) even during stressed market conditions" (Att A paras 9(c)(iii), 10(a)(iii), 10(b)(v), 12(a)(iv), 12(b)(iv), 12(c)(vi));
- not an obligation of a financial institution or its associated entities (the idea: if the bank is in trouble, other banks' paper is probably in trouble too) (Att A paras 9(c)(iv), 10(a)(iv), 10(b)(i), 12(b)(i), 12(c)(i)).

Two market terms:

- **Repo (repurchase agreement):** a loan secured on a security. The borrower sells the security for cash today and agrees to buy it back later at a slightly higher price. Chapter 4 explains repos step by step.
- **Associated entity:** a company related to the issuer, for example a parent or subsidiary. Check CPS 001 (the defined-terms standard) for the exact meaning; this chapter does not reproduce it.

### 3.2 First day, any maturity

"Assets that may be included in each category are those that the ADI is holding on the first day of the stress period, irrespective of their residual maturity" (Att A para 6). *Residual maturity* is the time remaining until an instrument is repaid. A bond that matures in 5 days still counts in full as HQLA if it meets the tests, because the bank holds it on day one. (The cash it will pay on maturity must not also be counted as an inflow. See Att A para 31 in section 11.)

### 3.3 Two categories, three classes

| Class | Short description | Haircut | Reference |
|---|---|---|---|
| HQLA1 | Highest-quality assets | None (0%) | (Att A para 9) |
| HQLA2A | High-quality securities | 15% | (Att A para 10) |
| HQLA2B | Lower-quality but still eligible assets | 25% (eligible residential mortgage-backed securities); 50% (corporate debt, equities) | (Att A para 12) |

- HQLA1 "may be included without limit" (Att A para 6).
- HQLA2 (which means HQLA2A and HQLA2B together) "may only comprise up to 40 per cent of the total stock of HQLA" (Att A para 6).
- HQLA2B "must not exceed 15 per cent of the total stock of HQLA" and sits inside the 40% cap (Att A para 6).

A **haircut** is a percentage deducted from an asset's market value, to allow for the chance that it sells for less than its price in a crisis. An asset worth 100 at market with a 15% haircut counts as 85.

HQLA1 is included at **market value** (the price it would fetch today), not face value or book value (Att A para 9). HQLA2A haircuts apply to "the current market value" (Att A para 10).

> **Example:** A bond has a face value of A$100m, and its market price today is A$98m. As HQLA1 it counts for A$98m. As HQLA2A it counts for 98 x (1 - 0.15) = A$83.3m.

The caps and the adjusted-amount unwind (Att A paras 7 and 8) are explained in section 6, after the three classes have been described.

## 4. HQLA1 (Att A para 9)

HQLA1 are included at market value with no haircut, and may form any share of the stock (Att A para 9). The standard says the assets "are limited to" the list below. The list is closed: an asset that is not on it is not HQLA1.

| Limb | What qualifies | Reference |
|---|---|---|
| (a) | Notes and coin | (Att A para 9(a)) |
| (b) | Central bank balances, "to the extent that these balances may be drawn down in times of stress" | (Att A para 9(b)) |
| (c) | Marketable securities that are claims on, or guaranteed by, sovereigns, central banks, public sector entities (PSEs), the Bank for International Settlements (BIS), the International Monetary Fund (IMF), the European Central Bank (ECB), the European Union (EU) or multilateral development banks (MDBs), **and** meet all four conditions (i) to (iv) | (Att A para 9(c)) |
| (d) | For non-zero per cent risk-weighted sovereigns: sovereign or central bank debt securities issued in domestic currencies by the sovereign or central bank in the country in which the liquidity risk is being taken, or in the ADI's home country | (Att A para 9(d)) |
| (e) | For non-zero per cent risk-weighted sovereigns: domestic sovereign or central bank debt securities issued in foreign currencies, up to the amount of the ADI's stressed net cash outflows in that specific foreign currency stemming from its operations in the jurisdiction where the liquidity risk is being taken | (Att A para 9(e)) |

Terms:

- **Central bank balances:** in Australia, an ADI's balance in its Exchange Settlement Account at the RBA (Chapter 2). Money the bank can withdraw from the RBA counts as HQLA1. Money it could not withdraw in stress would not, hence "to the extent that these balances may be drawn down in times of stress".
- **Sovereign:** a national government.
- **Public sector entity (PSE):** a government-owned or government-backed body below national level, such as a state or territory borrowing authority. Chapter 4 explains the counterparty types used in APS 210.
- **Multilateral development bank (MDB):** a bank owned by several governments to lend for development, for example the World Bank group.
- **Risk weight:** a percentage assigned to an exposure for capital purposes. APS 112 sets risk weights. A 0% risk weight is the lowest, given to the safest sovereign claims.

### 4.1 The four conditions in limb (c)

A marketable security under limb (c) must satisfy **all** of these (Att A para 9(c)):

| Condition | Test |
|---|---|
| (i) | Assigned a zero per cent risk weight under Attachment B of Prudential Standard APS 112 Capital Adequacy: Standardised Approach to Credit Risk (APS 112) |
| (ii) | Traded in large, deep and active repo or cash markets characterised by a low level of concentration |
| (iii) | Proven record as a reliable source of liquidity in the markets (repo or sale) even during stressed market conditions |
| (iv) | Not an obligation of a financial institution or any of its associated entities |

### 4.2 Limbs (d) and (e): sovereigns that are not zero-weighted

Some sovereigns do not get a 0% risk weight. A bank that operates in such a country may still need its local government debt as a liquidity buffer. Limbs (d) and (e) allow this for that country's own currency (d) and for foreign-currency debt up to the stressed net outflows in that currency (e) (Att A para 9(d) and (e)). A bank that has liabilities in a country's own currency and holds that country's local-currency government bonds is naturally matched: the outflows and the assets are in the same currency.

### 4.3 The Australian position

APS 210 does not name specific Australian securities. It defines the *categories*, and for HQLA2 it adds that assets must be "recognised by APRA or the relevant prudential regulator in the jurisdiction where the liquidity risk is taken" (Att A paras 10 and 12). As stated in APRA's liquidity frequently asked questions and in the RBA's January 2024 Bulletin article on the CLF (see Appendix B), the only Australian-dollar assets that APRA has assessed as meeting the Basel criteria for HQLA are:

1. notes and coin;
2. balances at the RBA (Exchange Settlement Account balances);
3. Australian Government Securities (Treasury bonds and notes); and
4. securities issued by the borrowing authorities of the states and territories (semi-government securities, or "semis").

As generally understood, APRA has not recognised any AUD assets as HQLA2 (neither HQLA2A nor HQLA2B). This is why Australian banks' AUD HQLA is dominated by government and semi-government securities and RBA balances, and why the HQLA2 caps in section 6 rarely bind on the AUD LCR. HQLA2 assets can still matter for foreign-currency liquidity where a foreign prudential regulator recognises them in the place where the liquidity risk is taken. APRA's practice guide, Prudential Practice Guide APG 210 Liquidity, is the place to confirm the current position. This guide has not independently verified the recognised list beyond the RBA statement.

> **Why it matters for data work:** The eligibility test is partly a *regulatory recognition* test, not only a property of the security. An HQLA classification field in a dashboard should come from a maintained eligibility list (by security identifier, issuer and jurisdiction), not from a rule such as "all bonds rated AA or better".

> **Example:** Example Bank holds A$5.0bn in cash and balances with the RBA (Att A para 9(a) and (b)) and A$12.0bn in government and semi-government securities (Att A para 9(c)). Total HQLA1 = 5.0 + 12.0 = A$17.0bn. No haircut applies. The assumption is that the securities meet the conditions in para 9(c) and are unencumbered.

## 5. HQLA2A and HQLA2B (Att A paras 10 to 12)

Both HQLA2 classes are only eligible where the assets "have been recognised by APRA or the relevant prudential regulator in the jurisdiction where the liquidity risk is taken" (Att A paras 10 and 12). Both are subject to the 40% cap, and HQLA2B to the 15% cap (Att A para 6).

### 5.1 HQLA2A: 15% haircut (Att A para 10)

"A 15 per cent haircut is applied to the current market value of each HQLA2A held in the stock of eligible HQLA" (Att A para 10). The list is closed ("HQLA2A are limited to"). There are two limbs.

**Limb (a): sovereign, central bank, PSE and MDB securities with a 20% risk weight (Att A para 10(a)).** Marketable securities that are claims on, or guaranteed by, sovereigns, central banks, PSEs or MDBs and meet all of:

| Condition | Test | Reference |
|---|---|---|
| (i) | Assigned a 20 per cent risk weight under Attachment B of APS 112 | (Att A para 10(a)(i)) |
| (ii) | Traded in large, deep and active repo or cash markets characterised by a low level of concentration | (Att A para 10(a)(ii)) |
| (iii) | Proven record as a reliable source of liquidity (repo or sale) even in stress, meaning a maximum decline of price not exceeding 10 per cent, or an increase in haircut not exceeding 10 percentage points, over a 30-day period during a relevant period of significant liquidity stress | (Att A para 10(a)(iii)) |
| (iv) | Not an obligation of a financial institution or any of its associated entities | (Att A para 10(a)(iv)) |

**Limb (b): corporate debt securities (including commercial paper) and covered bonds (Att A para 10(b)).** All of the following must be met:

| Condition | Test | Reference |
|---|---|---|
| (i) | Corporate debt securities: not issued by a financial institution or any of its associated entities, and "plain vanilla" assets whose valuation is readily available from standard methods and does not depend on private knowledge | (Att A para 10(b)(i)) |
| (ii) | Covered bonds: not issued by the ADI itself or any of its associated entities | (Att A para 10(b)(ii)) |
| (iii) | A credit rating from a recognised external credit assessment institution (ECAI) of at least AA- (footnote 2: if there are multiple assessments, use the method in APS 112). For an ADI approved to use the internal ratings-based (IRB) approach under APS 113: no ECAI assessment, and internally rated with a probability of default (PD) corresponding to at least AA- | (Att A para 10(b)(iii)) |
| (iv) | Traded in large, deep and active repo or cash markets characterised by a low level of concentration | (Att A para 10(b)(iv)) |
| (v) | Proven record as a reliable source of liquidity: a maximum decline of price, or increase in haircut, over a 30-day period in a relevant period of significant liquidity stress not exceeding 10 per cent | (Att A para 10(b)(v)) |

Terms used above:

- **Covered bond:** a bond issued by a bank that is also backed by a separate pool of assets (usually mortgages) that stays available to bondholders if the bank fails. Chapter 4 describes covered bonds.
- **Commercial paper:** short-term unsecured debt issued by a company (Chapter 4).
- **ECAI (external credit assessment institution):** a credit rating agency that APRA recognises for capital purposes.
- **IRB approach:** an advanced method that some large banks have approval to use to measure credit risk with their own models (APS 113). Banks using it may rely on an internal rating where no external rating exists.
- **Probability of default (PD):** the bank's own estimate of the chance a borrower fails to pay within a year.

**Diversification (Att A para 11):** "The portfolio of HQLA2A held by the ADI must be well diversified in terms of type of assets, type of issuer and specific counterparty or issuer." This is a requirement on the whole HQLA2A portfolio, not a test on one security. The standard does not give a number, so each bank must define and document its own measure, and APRA will judge it.

### 5.2 HQLA2B: 25% or 50% haircut (Att A para 12)

HQLA2B are weaker assets that still pass demanding tests. There are three limbs, each with a different haircut.

**Limb (a): residential mortgage-backed securities (RMBS), 25% haircut (Att A para 12(a)).** An RMBS is a bond paid from the repayments on a pool of home loans (Chapter 4). All of the following must be met:

| Condition | Test | Reference |
|---|---|---|
| (i) | Not issued by, and the underlying exposures not originated by, the ADI itself or an associated entity of the ADI | (Att A para 12(a)(i)) |
| (ii) | A long-term credit rating from a recognised ECAI of AA or higher (footnote 3 refers to footnote 2: multiple assessments are resolved by the APS 112 method) or, if there is no long-term rating, a short-term rating equivalent in quality | (Att A para 12(a)(ii)) |
| (iii) | Traded in large, deep and active repo or cash markets characterised by a low level of concentration | (Att A para 12(a)(iii)) |
| (iv) | Proven record as a reliable source of liquidity: maximum decline in price not exceeding 20 per cent, or increase in haircut over a 30-day period not exceeding 20 percentage points, during a relevant period of significant liquidity stress | (Att A para 12(a)(iv)) |
| (v) | The underlying asset pool is restricted to residential mortgages and cannot contain structured products | (Att A para 12(a)(v)) |
| (vi) | The underlying mortgages are full recourse loans and, at issuance, have a maximum average loan-to-valuation ratio (LVR) of 80 per cent | (Att A para 12(a)(vi)) |
| (vii) | The securitisation is subject to risk retention regulations, which require an issuer to retain an interest in the assets it securitises | (Att A para 12(a)(vii)) |

- **Full recourse:** if the borrower defaults and the property sells for less than the debt, the lender can still pursue the borrower for the rest.
- **Loan-to-valuation ratio (LVR):** loan amount divided by the value of the property. A A$400,000 loan on a A$500,000 property has an LVR of 80%.
- **Risk retention:** the rule that the originator must keep some of the risk in the securities it creates, so it cares about loan quality.

Note condition (i): a bank's own RMBS, including one it created for itself (self-securitisation), is not HQLA2B. Chapter 4 explains self-securitisation.

**Limb (b): corporate debt securities (including commercial paper), 50% haircut (Att A para 12(b)).**

| Condition | Test | Reference |
|---|---|---|
| (i) | Not issued by a financial institution or an associated entity | (Att A para 12(b)(i)) |
| (ii)(1) | A long-term credit rating from a recognised ECAI between A+ and BBB- (footnote 4 refers to footnote 2) or, with no long-term rating, a short-term rating equivalent in quality | (Att A para 12(b)(ii)(1)) |
| (ii)(2) | For an IRB-approved ADI: no ECAI assessment, and internally rated as having a PD corresponding to a rating between A+ and BBB- | (Att A para 12(b)(ii)(2)) |
| (iii) | Traded in large, deep and active repo or cash markets characterised by a low level of concentration | (Att A para 12(b)(iii)) |
| (iv) | Proven record as a reliable source of liquidity: a maximum decline in price not exceeding 20 per cent, or increase in haircut over a 30-day period not exceeding 20 percentage points, during a relevant period of significant liquidity stress | (Att A para 12(b)(iv)) |

Notice that limb (b) takes corporate bonds rated *below* those allowed in HQLA2A (AA- or better, Att A para 10(b)(iii)), down to BBB-, and charges a larger haircut (50% instead of 15%).

**Limb (c): common equity shares, 50% haircut (Att A para 12(c)).**

| Condition | Test | Reference |
|---|---|---|
| (i) | Not issued by a financial institution or an associated entity | (Att A para 12(c)(i)) |
| (ii) | Exchange traded and centrally cleared | (Att A para 12(c)(ii)) |
| (iii) | A constituent of the major stock index where the liquidity risk is taken | (Att A para 12(c)(iii)) |
| (iv) | Denominated in the currency of the jurisdiction where the bank's liquidity risk is taken | (Att A para 12(c)(iv)) |
| (v) | Traded in large, deep, active repo or cash markets characterised by a low level of concentration | (Att A para 12(c)(v)) |
| (vi) | Proven record as a reliable source of liquidity: a maximum decline in share price not exceeding 40 per cent, or increase in haircut not exceeding 40 percentage points, over a 30-day period during a relevant period of significant liquidity stress | (Att A para 12(c)(vi)) |

### 5.3 The three classes side by side

| Feature | HQLA1 | HQLA2A | HQLA2B RMBS | HQLA2B corporate debt | HQLA2B equities |
|---|---|---|---|---|---|
| Haircut | 0% | 15% | 25% | 50% | 50% |
| Reference | Att A para 9 | Att A para 10 | Att A para 12(a) | Att A para 12(b) | Att A para 12(c) |
| Stress price-fall test | Not stated | 10% | 20% | 20% | 40% |
| Rating test | Risk weight 0% | Risk weight 20%, or at least AA- | At least AA | A+ to BBB- | None stated |
| Financial institution issuers allowed? | No | No | RMBS not own/associated | No | No |
| Share limit | None | Inside 40% HQLA2 cap | Inside 15% and 40% caps | Inside 15% and 40% caps | Inside 15% and 40% caps |

> **Watch out:** The stress price-fall figures (10%, 20%, 40%) are tests of *historical* behaviour in a stress period. They are not the haircuts. The haircut is separate.

## 6. The caps and the adjusted-amount unwind (Att A paras 6 to 8)

### 6.1 Why caps exist

HQLA1 is the strongest. The regulator does not want a bank's buffer to be built mostly from assets that might be hard to sell in a crisis. So HQLA2 is limited to 40% of the total, and HQLA2B to 15% (Att A para 6).

### 6.2 The caps as percentages

- HQLA2 (A and B together) must not exceed 40% of the total stock of HQLA.
- HQLA2B must not exceed 15% of the total stock of HQLA, and counts inside the 40% (Att A para 6).

### 6.3 The caps as calculation formulas (Att A para 7)

A cap stated as "40% of the total" is circular, because the total includes the thing being capped. Paragraph 7 solves this by stating the caps relative to the other assets:

| Cap | Formula | Reference |
|---|---|---|
| HQLA2 maximum | Two-thirds of adjusted HQLA1 (after haircuts) | (Att A para 7) |
| HQLA2B maximum | The lower of the two limits below; para 7 states them as "either ... or, in cases where the 40 per cent cap is binding" | (Att A para 7) |
| - normal case | 15/85 of (adjusted HQLA1 + adjusted HQLA2A, after haircuts) | (Att A para 7) |
| - when the 40% cap binds | Up to one quarter of adjusted HQLA1 (after haircuts) | (Att A para 7) |

Why two-thirds? If HQLA2 is 40% of the total, HQLA1 is 60%, so HQLA2 / HQLA1 = 40/60 = two-thirds. Why 15/85? If HQLA2B is 15% of the total, the rest (HQLA1 + HQLA2A) is 85%, so HQLA2B / rest = 15/85. Why one quarter? If HQLA2 is already at its 40% limit and HQLA2B is 15% of the total, then HQLA2B / HQLA1 = 15/60 = one quarter.

In a spreadsheet or SQL, the sequence is:

```
adj_HQLA1   = HQLA1 after haircuts, after unwinding (see 6.4)
adj_HQLA2A  = HQLA2A after 15% haircut, after unwinding
adj_HQLA2B  = HQLA2B after 25% / 50% haircuts, after unwinding

HQLA2 cap   = (2/3) * adj_HQLA1
HQLA2B cap  = min( 15/85 * (adj_HQLA1 + adj_HQLA2A) ,  (1/4) * adj_HQLA1 )   -- see note
                                                       -- note: the 1/4 limit applies where
                                                       -- the 40% cap is binding (Att A para 7)

HQLA2B counted = min(adj_HQLA2B, HQLA2B cap)
HQLA2 counted  = min(adj_HQLA2A + HQLA2B counted, HQLA2 cap)

Stock of HQLA  = adj_HQLA1 + HQLA2 counted        (plus CLF amount if any, sec. 8)
Excluded       = (HQLA1 + HQLA2A + HQLA2B after haircuts) - Stock of HQLA
```

The `min` line is a reading of para 7's two alternatives. Para 7 says the HQLA2B limit is 15/85 of the sum of the adjusted amounts of HQLA1 and HQLA2A, or "in cases where the 40 per cent cap is binding, up to one quarter" of adjusted HQLA1. The simplest implementation that always respects both caps is to apply the HQLA2B cap first and then the overall HQLA2 cap, as above, and to confirm the result with the percentage tests in para 6 (HQLA2 not above 40% of the stock; HQLA2B not above 15% of the stock). Treat the code above as a reading to confirm with the bank's regulatory reporting team, not as a quotation.

> **Example (what-if exercise 3, a hypothetical bank, not Example Bank):** HQLA1 is 60. HQLA2A has a market value of 100, worth 85 after the 15% haircut. Cap: HQLA2 may be at most two-thirds of 60 = 40. HQLA counted = 60 + 40 = 100. The amount excluded is 85 - 40 = 45. Check: HQLA2 is 40, which is 40% of the stock of 100.

> **Example (the 15/85 rule, hypothetical):** HQLA1 = 70. HQLA2A after haircut = 20. HQLA2B (RMBS) after its 25% haircut = 30. HQLA2B cap = 15/85 x (70 + 20) = 15.88. Counted HQLA2B = min(30, 15.88) = 15.88. HQLA2 total = 20 + 15.88 = 35.88, below the two-thirds cap of 46.67. Stock = 70 + 20 + 15.88 = 105.88. Check: HQLA2B is 15.88 / 105.88 = 15.0% of the stock.

> **Example (the one-quarter rule, hypothetical):** HQLA1 = 60. HQLA2A after haircut = 40. HQLA2 cap = two-thirds x 60 = 40, so the 40% cap already binds on HQLA2A alone. HQLA2B can then only come in by displacing HQLA2A, and its limit is one quarter of HQLA1 = 15. Counted: HQLA1 60 + HQLA2 40 (made up of at most 15 of HQLA2B and the rest HQLA2A) = 100. HQLA2B is 15 / 100 = 15% of the stock, which respects Att A para 6.

### 6.4 The adjusted amount: unwinding short-term transactions (Att A paras 7 and 8)

Before applying the caps, the bank must take into account "the impact on the stock of HQLA of the amounts of HQLA1 and HQLA2 involved in secured funding, secured lending and collateral swaps transactions maturing within 30 calendar days" (Att A para 7).

The definitions are in para 8. The **adjusted amount** of each class (HQLA1, HQLA2A, HQLA2B) is the amount that would result "after unwinding short-term secured funding, secured lending and collateral swap transactions involving the exchange of any HQLA for any" asset of that class that meets, or would meet if held unencumbered, the operational requirements in Att A paras 22 to 25. "Short-term transactions are transactions with a maturity date up to and including 30 calendar days" (Att A para 8).

Terms:

- **Secured funding:** borrowing against collateral (for example a repo where the bank gives a bond and receives cash).
- **Secured lending:** lending against collateral (for example a reverse repo where the bank gives cash and receives a bond).
- **Collateral swap:** an exchange of one set of securities for another, where no cash changes hands, to change the collateral each side holds.
- **Unwinding:** reversing the transaction in the calculation, as if it matured today and each party got its assets back.

Why it exists: transactions inside 30 days will complete during the window anyway. Without the unwind, a bank could swap a pile of HQLA2 for HQLA1 for 29 days, show a stock that is nearly all HQLA1, and escape the caps, even though the swap will reverse on day 29 and its stock will be mostly HQLA2 again. The unwind forces the caps to be measured on what the bank would own once the short-term deals reverse.

> **Example (an illustration of the mechanism, hypothetical):** A bank's stock today is 50 of HQLA1. Of that, 10 is cash it borrowed under a repo that matures in 20 days, for which it gave HQLA2A securities as collateral. Those securities are encumbered, so they are not in the stock today, and the stock looks like pure HQLA1. For the cap calculation the repo is unwound: the cash goes back, so adjusted HQLA1 is 40, and the securities return, so adjusted HQLA2A is their value after the 15% haircut, say 10. The caps are tested on 40 of HQLA1 and 10 of HQLA2A, which is what the bank will hold once the repo matures. Here HQLA2 is well inside its cap of two-thirds x 40 = 26.7, so nothing is excluded; with a much larger repo the cap would bite. A repo of HQLA1 securities for cash changes nothing in the adjusted amounts, because both legs are HQLA1.

> **Watch out:** The unwind affects only the *cap calculation*. It does not put encumbered assets into the stock. The securities pledged in the example above are still not HQLA today (Att A para 23). The standard does not give a worked example of the unwind. Test the bank's implementation against its regulatory reporting guidance.

APRA may also require a bank that actively uses collateral swaps for liquidity management to include the net cash flow impact of those swaps in its LCR, using a method APRA determines (Att A para 33).

## 7. Assembling the numerator: a recap

For each security, in order:

1. Is it on the day-one holdings list, owned, and unencumbered? (Att A paras 6, 22, 23)
2. Which class is it (HQLA1, HQLA2A, HQLA2B), and is it recognised? (Att A paras 9, 10, 12)
3. Is it at market value? Apply the haircut for its class (0%, 15%, 25%, 50%).
4. Compute the adjusted amounts for the cap test (unwind transactions of 30 days or less) (Att A para 8).
5. Apply the HQLA2B cap, then the HQLA2 cap (Att A paras 6 and 7).
6. Add any recognised CLF amount (Att A para 15; see section 8).
7. The result is the numerator.

| Class | Market value | Haircut | After haircut | Counted after caps |
|---|---|---|---|---|
| Example Bank HQLA1: cash and RBA balances | 5.0 | 0% | 5.0 | 5.0 |
| Example Bank HQLA1: government and semi-government securities | 12.0 | 0% | 12.0 | 12.0 |
| Example Bank HQLA2A, HQLA2B | 0 | not applicable | 0 | 0 |
| **Stock of HQLA** | | | | **17.0** |

Example Bank's A$3.0bn of "other debt securities (non-HQLA, over 1 year)" are not HQLA, so they contribute nothing to the numerator.

## 8. The Committed Liquidity Facility (Att A paras 13 to 21)

### 8.1 What it was

The CLF was an arrangement with the RBA that let an Australian bank count a committed borrowing line towards its liquid assets. The reason was a shortage: there were too few Australian Government and semi-government securities to cover all banks' needs. A locally incorporated LCR ADI "may establish a CLF with the RBA, sufficient in size to cover any shortfall in Australian dollars between the ADI's holdings of HQLA and net cash outflows" (Att A para 13). The CLF is a committed repo line: the ADI pays a fee, and in return the RBA agrees to lend against qualifying collateral. Qualifying collateral "will comprise all assets eligible for repurchase transactions with the RBA under normal market conditions and any other assets nominated by the RBA" (Att A para 13).

Att A para 14 limits its use: "The CLF must only be used by an ADI to manage any shortfall in Australian dollars between its holding of HQLA and its net cash outflows."

### 8.2 How much counted: the numerator formula (Att A para 15)

The numerator with a CLF is the market value of HQLA1 and HQLA2 held, after the haircuts in paras 10 and 12, **plus** the *lowest* of three amounts (Att A para 15):

| Limb | Amount | Plain English |
|---|---|---|
| (a) | The contractual amount of the CLF agreed with the RBA and approved by APRA for LCR purposes (paras 17 to 20) | The approved size of the facility |
| (b) | The contractual amount in (a), **less** the market value (after RBA margins) of eligible CLF securities pledged under maturing secured funding transactions that have a 0% run-off rate, **plus** the market value (after RBA margins) of eligible CLF securities received under maturing secured lending that have a 0% inflow rate, where the collateral received is not used to cover short positions (para 56) | The facility, adjusted so that collateral already committed in the next 30 days is not counted twice |
| (c) | The market value of the assets held by the ADI as collateral for the CLF, after applicable RBA margins | The amount the RBA would actually lend against what the bank holds |

The "lowest of" rule means the CLF can never count for more than the bank's approved facility, more than its free collateral (after the RBA's margins, which are its own haircuts), or more than the amount of collateral not already promised elsewhere.

### 8.3 Conditions and process (Att A paras 16 to 21)

| Para | Requirement |
|---|---|
| 16 | Assets held for the CLF must meet the operational requirements for HQLA (Att A paras 22 to 25) and be well diversified by type of asset, type of issuer and specific counterparty or issuer |
| 17 | An ADI needing a CLF for LCR purposes must apply to APRA for approval before establishing it |
| 18 | The funding strategy must clearly state the CLF amount required in the forecast period. The ADI must make "every reasonable effort" to manage liquidity risk through its own balance sheet management before applying |
| 19 | After initial approval, the ADI must apply annually for APRA's approval of the size recognised for LCR purposes |
| 20 | For unforeseen changes in circumstances, the ADI may apply to APRA at any time for a change, with an updated Board-approved funding and liquidity plan |
| 21 | If the ADI draws on the CLF other than for intraday purposes or to fund end-of-day balances at the RBA, senior management must attest that the proceeds will be used for AUD liquidity needs only. APRA must be advised of any proposed drawdown that is not for intraday or end-of-day balance purposes |

### 8.4 Current status

Paras 13 to 21 are still in the July 2025 text of APS 210, and Att A para 5 and Table 3 still refer to the CLF. In practice the facility has been withdrawn. Per APRA and the RBA, APRA reduced each ADI's CLF allocation to zero in steps during 2022, and APRA confirmed that as at 1 January 2023 the aggregate CLF had been fully phased out to zero. APRA has said the CLF remains available to be reactivated if there is a future shortfall of HQLA. The reasons given were that the supply of Australian Government and semi-government securities had grown enough for banks to meet the LCR without it. (Sources are listed in Appendix B; these are statements from apra.gov.au and rba.gov.au at the time of writing.)

For a dashboard: build the CLF line in the numerator (and the two CLF-related lines in Tables 3 and 4) but expect it to hold zero. A dashboard that hard-codes "no CLF" will break if APRA reactivates the facility.

> **Watch out:** Two lines of Table 3 and one line of Table 4 only apply "where the ADI pledging assets has a CLF with the RBA subject to the ADI's CLF limit". With a CLF allocation of zero, those lines should not receive any balance. Securities that would have been CLF-eligible then fall into the "all other" lines at 100%.

## 9. Operational requirements and the grace period (Att A paras 22 to 25)

An asset can be of the right type and still not count. It must be held and managed in a way that lets the bank actually sell it. The standard calls these the operational requirements. They apply to "All assets in the stock of eligible HQLA" (Att A para 22).

### 9.1 The three tests in para 22

| Limb | Requirement | Plain English |
|---|---|---|
| (a) | The assets must be available for the ADI to convert into cash at any time | No lock-up, no delay |
| (b) | The assets must be unencumbered and under the control of the function charged with managing the ADI's liquidity risk. This would typically be the treasurer, who must have continuous authority, and the legal and operational capability, to **monetise** any asset in the stock | Treasury can sell or repo it on its own say-so |
| (c) | Control must be evidenced either by (1) keeping the assets in a separate pool managed by the function with the sole intent of using it as a source of contingent funds, or (2) demonstrating that the function can monetise the asset at any point in the 30-day stress period and that the proceeds are available to the function throughout the period without directly conflicting with a stated business or risk management strategy | Prove it with either a separate pool or a demonstrated ability to sell |

**Monetise** means turn into cash, by selling the asset or by borrowing against it in a repo (Chapter 1).

### 9.2 No pledging, no earmarking (Att A para 23)

"The assets must not be pledged to secure, collateralise or credit enhance any transactions or be designated to cover operational costs (such as rents and salaries)" (Att A para 23). Two consequences:

- An asset already given as collateral (a repo, a derivative margin payment, a payment-system collateral account) is out of the stock.
- An asset that the bank has earmarked in its plans to pay for running costs is also out.

The para adds one inclusion: "Assets received in reverse repo and securities financing transactions that are held at the ADI, have not been rehypothecated and are legally and contractually available for the ADI's use may be considered as part of the stock of HQLA" (Att A para 23). **Rehypothecation** means the bank has re-used collateral it received, by pledging it onwards to someone else. Collateral that has been re-used is not available, so it does not count. A **securities financing transaction** is a repo, reverse repo, securities lending or borrowing (Chapter 4).

> **Example:** Example Bank has A$12.0bn of government securities. If A$2.0bn is pledged as collateral to a clearing house (that is, it is encumbered), only A$10.0bn counts as HQLA1. The A$2.0bn is not HQLA, even though it is still owned.

### 9.3 Grace period for assets that become ineligible (Att A para 25)

"If an eligible HQLA or eligible CLF liquid asset becomes ineligible (e.g. due to rating downgrade), an ADI may keep the asset in its stock of liquid assets for an additional 30 calendar days. This allows the ADI time to adjust its stock as needed or replace the asset" (Att A para 25). So a corporate bond downgraded from AA- to A+ drops out of HQLA2A, but the bank may keep counting it for up to 30 more days while it replaces it.

> **Watch out:** The para says the asset may be kept "for an additional 30 calendar days". It does not say whether the asset keeps its old class and haircut during that time. Confirm the treatment with APRA guidance before building a rule for the grace period.

## 10. Level 2 and offshore subsidiaries (Att A paras 24 and 26 to 29)

### 10.1 Level 1 and Level 2

"Level 1" means the ADI on its own. "Level 2" means the ADI and its subsidiaries combined, the consolidated banking group (APS 210 paras 3 to 4; Chapter 2). "The LCR is to be met by an ADI on both a Level 1 and Level 2 basis" (Att A para 26).

### 10.2 Offshore branches and subsidiaries (Att A paras 26 and 27)

Where an ADI has a branch or subsidiary in another country, "in calculating a subsidiary's LCR the ADI must apply the requirements outlined in this Prudential Standard", with two exceptions (Att A para 26):

1. For retail and small and medium enterprise (SME) deposits, the **host supervisor's** outflow assumptions must be applied (para 26(a)). A **host supervisor** is the prudential regulator in the country where the subsidiary operates.
2. "Alternative liquid assets" as provided for in the Basel Committee on Banking Supervision's global liquidity framework, and allowed by the host supervisor, may be included (para 26(b)).

If the offshore jurisdiction does not apply the Basel Committee's global framework for liquidity risk, "the cash flow assumptions outlined in this Prudential Standard must be applied in calculating the ADI's Level 2 LCR" (Att A para 27).

### 10.3 Material offshore banking subsidiaries (Att A para 28)

"An ADI with a material banking subsidiary in another offshore jurisdiction must ensure that the subsidiary maintains an LCR of at least 100 per cent." APRA may allow an ADI to include assets that are formally recognised as eligible liquid assets by the relevant offshore prudential regulator (Att A para 28).

### 10.4 Liquid assets held in a legal entity (Att A para 24)

At Level 2, an ADI may include liquid assets that qualify under paras 9 to 17, 22 to 23 and 28 in the stock of HQLA, where:

- they are held to meet **legal entity requirements** (a local rule requires that company to hold them) and the related risks, as measured by that legal entity's net cash outflows, are also reflected in the LCR; and
- any *surplus* of liquid assets in the legal entity is included only if the assets "would be freely available to the consolidated (parent) entity in times of stress" (Att A para 24).

### 10.5 Trapped liquidity (Att A para 29)

"For the calculation of the Level 2 LCR, an ADI must take into account restrictions on the transferability of liquid assets across borders. Excess liquidity is not to be recognised in the Level 2 LCR unless there is reasonable certainty about the availability of such liquidity" (Att A para 29).

> **Example (hypothetical):** A group's New Zealand subsidiary holds NZ$1bn more HQLA than its own outflows need. If local rules or practical limits stop that surplus moving to Australia in a crisis, the surplus is not counted in the Level 2 LCR. The subsidiary's own outflows still are.

> **Why it matters for data work:** An LCR at group level cannot be summed from entity LCRs. It needs each entity's HQLA, outflows and inflows separately, a transferability flag for surplus HQLA, and, for offshore entities, an indicator for whether host-supervisor outflow rates (retail and SME only) apply.

## 11. Net cash outflows: the denominator (Att A paras 30 to 33)

### 11.1 The formula and the 75% cap (Att A para 30)

"Total net cash outflows represent the total expected cash outflows minus total expected cash inflows in the specified stress scenario for the subsequent 30 calendar days" (Att A para 30).

- **Expected outflows** are the outstanding balance of each liability or off-balance-sheet commitment category multiplied by its run-off or drawdown rate in Table 3 (Att A paras 30 and 53). The **run-off rate** is the share of a balance the scenario assumes will leave (or be drawn) within 30 days.
- **Expected inflows** are the outstanding balance of each category of contractual receivable multiplied by its inflow rate (Att A paras 54 to 66), "up to an aggregate cap of 75 per cent of total expected cash outflows" (Att A para 30).

```
Total net cash outflows over the next 30 calendar days
  =  Total expected cash outflows
     - Min { total expected cash inflows ; 75% x total expected cash outflows }
```

The standard writes the formula this way (Att A para 30). Two consequences:

- Net outflows can never be less than 25% of gross outflows.
- The cap is on the *total* inflows after rates are applied, not on any single line.

**Why the cap exists:** a bank must not assume that its own debtors repay it so reliably that it needs almost no liquid assets. Always hold enough HQLA to cover at least a quarter of gross outflows.

> **Example (what-if exercise 4, hypothetical):** Outflows 100, inflows 90. The cap is 75% x 100 = 75. Inflows counted = min(90, 75) = 75. Net outflows = 100 - 75 = 25, not 10.

> **Example (Example Bank):** Outflows 13.45. Cap = 75% x 13.45 = 10.0875, shown as 10.09. Inflows are 1.90, well below the cap, so the cap is not binding. Net outflows = 13.45 - 1.90 = 11.55.

APRA may set an alternative limit on cash inflows where it considers the ADI overly reliant on inflows from one or a limited number of wholesale counterparties (Att A para 54; section 18).

### 11.2 No double counting (Att A para 31)

"An ADI must not double-count items. That is, if assets are included as part of the stock of HQLA (the numerator of the LCR), the associated cash inflows cannot also be counted as cash inflows" (Att A para 31).

> **Example:** A A$1.0bn government bond is in the stock of HQLA and matures in 10 days. The bank has already counted the bond as A$1.0bn of HQLA. It may not also count the A$1.0bn repayment as an inflow, because that would count the same money twice. Footnote 5 applies the same logic to derivatives: payables and receivables are shown net of HQLA1 and HQLA2 collateral "to the extent that this collateral is not already counted in the stock of HQLA" (Att A Table 3, footnote 5).

### 11.3 Evidence for derived assumptions (Att A para 32)

"APRA will assess the suitability of an ADI's assumptions made for those cash flow items that are derived. An ADI must be in a position to provide analysis and evidence to justify the assumptions" (Att A para 32). *Derived* items are those where the ADI sets its own rate or amount, such as the "to be set by the ADI" rows in Table 3 (section 17).

### 11.4 Collateral swaps (Att A para 33)

Where APRA determines that an ADI is actively using collateral swaps for liquidity management purposes, APRA may require it to include the net cash flow impact of those swaps, using a method APRA determines (Att A para 33).

## 12. Retail deposit outflows (Att A paras 34 to 43)

### 12.1 What is a retail deposit? (Att A para 34)

"For the purposes of the LCR, retail deposits are defined as deposits placed with an ADI by a natural person." A **natural person** is a human being. "Deposits from legal entities, sole proprietorships or partnerships are captured in wholesale deposit categories." Retail deposits include demand deposits and term deposits, unless excluded by the criteria in paras 41 and 42 (Att A para 34).

- **Demand deposit (at-call):** money the customer can withdraw at any time (Chapter 4).
- **Term deposit:** money locked up for an agreed period (Chapter 4).

> **Watch out:** A sole trader's account (a person trading under their own name) is **not** retail for the LCR. It is wholesale (Att A para 34), unless it qualifies under the SME treatment (Att A para 46; section 13.3). This differs from the everyday meaning of "retail customer".

### 12.2 Deposits through an intermediary (Att A para 35)

If a person places funds with an intermediary (such as a platform or an adviser), and the intermediary places the money with the ADI, the ADI's deposit "is considered to be a deposit from a financial institution" (so it runs off at 100%, see section 13.5) unless, during the next 30 days, all of these hold (Att A para 35):

| Limb | Condition |
|---|---|
| (a) | The person retains all legal rights regarding withdrawal or other movement of the funds |
| (b) | The person exercises these rights in practice and cannot transfer them to the intermediary |
| (c) | There is clear and prominent disclosure to the person that the funds will be placed with the ADI |
| (d) | The intermediary or an associated entity can neither make investment decisions on behalf of the person regarding the deposit, nor withdraw funds from the ADI without specific directions from the person (other than miscellaneous items such as fees, expense reimbursements, taxes) |

If all are satisfied, the ADI may treat the funds as if they are from the person, and "must be able to demonstrate how this treatment satisfies the conditions" (Att A para 35). An intermediated deposit is also called a brokered deposit (Chapter 4).

### 12.3 Stable and less stable (Att A paras 36 to 40)

Retail deposits are divided into stable and less stable portions (Att A para 36).

**Stable deposits (Att A para 37)** are "the portion of deposits that are fully covered by the Financial Claims Scheme (or an effective government deposit insurance scheme)" **and** where either:

- (a) the depositor has other established relationships with the ADI that make deposit withdrawal highly unlikely; or
- (b) the deposits are in transactional accounts (for example accounts where salaries are automatically credited).

The **Financial Claims Scheme (FCS)** is the Australian Government's deposit guarantee. As generally understood, it covers deposits up to A$250,000 per account holder per ADI (Chapter 2). Both conditions are needed: the amount must be inside the guarantee *and* the customer must be sticky.

**Less stable deposits (Att A para 38)** are the portion that does not meet the stable requirements.

**Factors that make a deposit more likely to leave in stress (Att A para 39):**

- high-value deposits (above any government deposit guarantee limit);
- deposits from customers with no established relationship with the ADI;
- on-line accounts (where the internet is integral to the design, marketing and use of the account);
- deposits with promotional interest rates ("heavily rate-driven").

### 12.4 The scorecard (Att A para 40, Tables 1 and 2)

"An ADI must assess each less stable account or product balance against the following scorecard" (Att A para 40).

**Table 1: the scorecard (Att A para 40)**

| Criterion | Score |
|---|---|
| Deposit balance is greater than any government deposit guarantee limit where it exists and, in its absence, greater than the equivalent of AUD 250,000 | 2 |
| Deposit is an on-line account | 2 |
| Absence of an established customer relationship | 1 |
| Deposit is heavily rate-driven | 1 |

**Table 2: less stable deposit allocations (Att A para 40)**

| Total score | Run-off rate |
|---|---|
| 0 to 2 | 10% |
| 3 or more | 25% |

These rows map to Table 3 of para 53: "Less stable retail deposits" at 10% and "Higher run-off less stable retail deposits" at 25%. The maximum possible score is 2 + 2 + 1 + 1 = 6.

(The text extraction of Table 1 in the plain-text version of the standard separates scores from criteria. The scores above were matched to the criteria by their positions in the PDF: 2 for the balance test, 2 for on-line, 1 for no relationship, 1 for rate-driven.)

> **Example 1 (scored):** Ruth holds A$320,000 in an on-line savings account with a bonus rate that applies only if she makes no withdrawals. She has no other product with the ADI.
> - Balance above A$250,000: 2
> - On-line account: 2
> - No established relationship: 1
> - Heavily rate-driven: 1
> - Total = 6, so the run-off rate is 25%. Run-off on A$320,000 = A$80,000. (Para 37 speaks of "the portion of deposits" that is fully covered, so a bank may need to split a large balance into a covered and an uncovered portion. The standard gives no worked example of that split. Here the covered portion is not stable anyway, because Ruth has no other relationship and the account is not transactional.)

> **Example 2 (scored):** Chen holds A$45,000 in a branch savings account at the same ADI where he has had a home loan for years. The rate is the standard rate. The account is not an on-line account.
> - Balance above A$250,000: 0
> - On-line: 0
> - No relationship: 0
> - Rate-driven: 0
> - Total = 0, so the run-off rate is 10%. Run-off on A$45,000 = 4,500.
> Note: Chen's deposit is inside the guarantee and he has an established relationship, so it could instead be **stable** (5%) under para 37(a). The scorecard is only used for balances that do not qualify as stable (Att A paras 37, 38 and 40).

> **Example 3 (scored):** Mia holds A$60,000 in an on-line account paying a promotional rate for new customers, and has no other relationship. On-line 2 + no relationship 1 + rate-driven 1 = 4. Run-off 25%, so A$15,000. If the promotional rate ends, the score is 2 + 1 = 3, still 25%. If she also had an established relationship with the ADI and the rate were ordinary, only the on-line score of 2 would remain, giving 10%.

**Data implication:** the scorecard works on each "account or product balance". A data model needs flags for balance above the guarantee limit, on-line, established relationship, and rate-driven, per account or product. The 25% bucket cannot be derived from balance bands alone.

### 12.5 Term deposits (Att A paras 41 to 43)

"Cash outflows related to fixed or term deposits with a residual maturity or withdrawal notice period of greater than 30 days will be excluded from LCR calculations if the depositor has no legal right to withdraw deposits within the 30-day horizon of the LCR, or if early withdrawal results in a significant penalty that is materially greater than the loss of interest" (Att A para 41).

So a term deposit has a 0% run-off only when:

1. its residual maturity or notice period is **more than 30 days**; and
2. either the depositor has **no legal right** to withdraw early, or early withdrawal involves **a significant penalty materially greater than the loss of interest**.

Otherwise, treat it as a demand deposit (stable or less stable) or, if it matures within 30 days, as a deposit that is callable inside the window.

**The "entire category" rule (Att A para 42):** "If an ADI allows a depositor to withdraw such deposits despite a clause that says the depositor has no legal right to withdraw, the entire category of these funds must be treated as demand deposits." A bank's policy of letting customers out early, even though the contract says they cannot, ruins the 0% treatment for the whole category.

**Hardship exception (Att A para 43):** an ADI "may allow depositors experiencing hardship to withdraw their term deposits without changing the treatment of the entire pool of deposits". The ADI "must have a policy defining hardship".

> **Example:** Example Bank has A$10.0bn of retail term deposits (over 30 days, under 1 year, no early withdrawal). They qualify under para 41, so the run-off is 0% (Att A para 41). Outflow = 10.0 x 0% = 0. But if Example Bank routinely lets customers break these deposits on request without a hardship policy, para 42 would require the whole A$10.0bn to be treated as demand deposits. It would then be less stable retail at 10% or more, adding at least 1.00 to outflows.

> **Watch out:** Residual maturity means the time remaining, not the original term. A 5-year term deposit with 20 days left is a within-30-days deposit.

## 13. Unsecured wholesale funding outflows (Att A paras 44 to 50, and Table 3)

### 13.1 Definition (Att A para 44)

"Unsecured wholesale funding is defined as those liabilities and general obligations that are raised from non-natural persons (i.e. legal entities, including sole proprietorships and partnerships) and are not collateralised by legal rights to specifically designated assets owned by the borrowing institution in the case of bankruptcy, insolvency, liquidation or resolution. Obligations related to derivative contracts are explicitly excluded from this definition" (Att A para 44).

In plain words:

- It comes from a company, trust, government body, fund, bank or other organisation, or from a sole trader or partnership. It does not come from a person acting as an individual.
- If the bank fails, the lender has no special claim on particular assets. That is what "unsecured" means. (Compare covered bonds and repos, which are secured; section 14.)
- Derivative obligations are excluded here and treated separately (section 15).

### 13.2 What falls in the 30-day window (Att A para 45)

Wholesale funding included in the LCR is "all funding that is callable within the LCR's horizon of 30 days or that has its earliest possible contractual maturity date within this horizon (such as maturing term deposits and unsecured debt securities), as well as funding with an undetermined maturity" (Att A para 45).

The paragraph adds two refinements:

- This "must include all funding with options that are exercisable at the investor's discretion within the 30-day horizon." (An investor option, such as a right to demand early repayment, counts at the *earliest* date the investor could use it.)
- Wholesale funding "that is callable by the provider of the funds, subject to a contractually defined and binding notice period surpassing the 30-day horizon, may be excluded."

| Funding | In the 30-day window? | Reference |
|---|---|---|
| Matures within 30 days | Yes | (Att A para 45) |
| At-call (can be demanded any time) | Yes | (Att A para 45) |
| Undetermined (no stated) maturity | Yes | (Att A para 45) |
| Matures after 30 days, but investor can put it back within 30 days | Yes, at its earliest possible date | (Att A para 45) |
| Matures after 30 days; provider can call it only after a binding notice period longer than 30 days | May be excluded | (Att A para 45) |
| Matures after 30 days, no early rights | No | (Att A para 45) |

> **Example:** Example Bank has A$1.0bn of wholesale debt maturing within 30 days, A$3.0bn between 30 days and 6 months, A$2.0bn from 6 months to under 1 year, and A$15.0bn of 1 year or more. Only the first A$1.0bn is inside the window, at 100% (Att A Table 3 "Unsecured debt issuance"). The other A$20.0bn contributes nothing to the LCR denominator. This is why the LCR looks only at the next 30 days, and the Net Stable Funding Ratio (Chapter 6) is used to monitor the longer tail.

### 13.3 SME deposits (Att A para 46)

A **small and medium enterprise (SME)** is a small to mid-sized business. For LCR purposes, "unsecured wholesale funding provided by SME customers may be treated as retail deposits where" (Att A para 46):

- (a) the deposits and other extensions of funds made by non-financial SME customers are managed as retail exposures and are generally considered as having similar liquidity risk characteristics to retail accounts; and
- (b) the total aggregated funding raised from an SME customer is less than AUD 2 million (on a consolidated basis where applicable).

Footnote 7 (to Att A para 61): where the SME definition in para 46 cannot be applied because of "the absence of liability products", the definition in para 40 of Prudential Standard APS 113 may be used instead.

Qualifying SME deposits are then split into stable and less stable using the retail tests, so that the retail rates of 5%, 10% and 25% apply (Att A Table 3 heading "Retail and qualifying SME deposits (refer to paragraphs 34 to 40 and 46)").

An SME with A$2 million or more of funding is not retail. Its deposits fall in the corporate rows ("SMEs of greater than AUD 2m", Att A Table 3) and run off at 20% or 40% if non-operational (section 13.6).

> **Example:** Example Bank has A$5.0bn of qualifying, less stable SME deposits. They are treated as retail, less stable, at 10% (Att A paras 46 and 40, Table 3). Outflow = 5.0 x 10% = 0.50.

### 13.4 Operational deposits (Att A paras 47 to 50)

An **operational deposit** is one the customer keeps with the bank because it needs it to run payments and similar services, not mainly to earn interest. The idea is that the customer cannot easily move it without disrupting its own business.

| Para | Rule |
|---|---|
| 47 | Operational deposits are those where customers place or leave deposits with an ADI "to facilitate their access and ability to use payment and settlement systems and otherwise make payments". They qualify only if "the customer has a substantive dependency on the ADI and the deposit is required for such activities" |
| 48 | Qualifying activities are **clearing, custody or cash management** where the customer is reliant on the ADI as an independent third-party intermediary to fulfil its normal banking activities over the next 30 days. The services must be provided to **institutional customers** under a **legally binding agreement**, and termination must be subject to either a notice period of at least 30 days or significant switching costs borne by the customer if the deposits are moved before 30 days |
| 49 | Qualifying deposits are those that are (a) by-products of the underlying services, (b) not offered by the ADI in the wholesale market for the sole purpose of offering interest income, and (c) held in specifically designated accounts and priced without giving an economic incentive to leave excess funds in them |
| 50 | "Any excess balances that could be withdrawn without jeopardising these clearing, custody or cash management activities do not qualify as operational deposits" |

Terms:

- **Clearing:** processing and settling payments or trades between parties.
- **Custody:** holding assets (such as securities) safely for a client.
- **Cash management:** services that help a business collect, hold and pay out its cash.

> **Watch out:** Only the *operational* part of a corporate account counts as an operational deposit. The rest is excess and is non-operational (Att A para 50), which runs off at a higher rate. A dashboard needs the split, not a single "operational" flag per customer.

### 13.5 Every wholesale line of Table 3 (Att A para 53)

Table 3 is the master table of outflow rates (Att A para 53). Its wholesale unsecured section reads:

| Table 3 line | Run-off | What it means in plain words |
|---|---|---|
| Operational deposit balances from all counterparties **fully covered by deposit insurance** | 5% | Operational accounts that are completely inside the Financial Claims Scheme limit. They are both needed by the customer and guaranteed, so very sticky |
| Operational deposit balances from all counterparties **not fully covered by deposit insurance** | 25% | Operational accounts above the guarantee (typical for corporates). Needed for operations, but uninsured, so a worry about the bank would still drive some out |
| Non-operational deposits from non-financial corporations, sovereigns, central banks, PSEs, MDBs and SMEs of greater than AUD 2m, **where the entire amount is fully covered by deposit insurance** | 20% | Not needed for payments, but insured; a guarantee reduces the reason to run |
| The same group, **where the entire amount is not fully covered by deposit insurance** | 40% | Not needed for payments, and uninsured. Treasurers of large companies move money fast when they worry |
| **All other non-operational deposits** | 100% | Includes deposits from financial institutions (banks, insurers, funds) and any other legal entity not in the line above. Financial institutions are assumed to be the most informed and fastest to withdraw |
| **Unsecured debt issuance** | 100% | Bonds, notes and bills the ADI issued that mature (or can be put back) inside the window. Investors are assumed not to roll over |

All references: (Att A Table 3).

> **Example:** Example Bank's wholesale deposit lines:
> - Corporate operational deposits (not fully insured) A$4.0bn x 25% = 1.00 (Att A Table 3, para 47)
> - Corporate non-operational deposits (not fully insured) A$6.0bn x 40% = 2.40 (Att A Table 3)
> - Financial institution deposits (at call) A$4.0bn x 100% = 4.00 ("All other non-operational deposits", Att A Table 3)
> - Wholesale debt maturing within 30 days A$1.0bn x 100% = 1.00 ("Unsecured debt issuance", Att A Table 3)
> Wholesale deposits and debt together: 8.40.

> **In the standard:** Table 3 heading reads "Unsecured wholesale funding (refer to paragraphs 44 to 46)". Operational deposits have their own definition in paras 47 to 50, which Table 3 relies on, though its heading does not name those paragraphs.

> **Why it matters:** In Example Bank, financial institution deposits are 4.0 of the 69.0 deposits but produce 4.00 of the 13.45 total outflows, nearly 30%. A bank's LCR is very sensitive to how much it funds from other financial institutions at call.

## 14. Secured funding outflows (Att A Table 3)

### 14.1 The idea

**Secured funding** is borrowing in which the lender takes collateral: a repo, or any loan secured on specific assets. In stress, a secured lender is more willing to keep lending if the collateral is easy to sell. If the borrower fails, the lender sells the collateral. So Table 3 assumes the lender rolls over at 0% loss against the best collateral, and increasingly refuses as the collateral gets weaker. The principle is simple: better collateral means the lender is more likely to roll.

The run-off rate here is applied to the **amount of the funding** (the cash borrowed) that matures within 30 days. The rate reflects the share the lender would not roll.

### 14.2 Every secured funding line

Reconstruction note: in the plain-text extraction of the standard, rates and row labels are separated across pages. Re-extracting the PDF and matching each rate to its row by position gives the table below. One cell needs care: the RMBS row. See the note under the table.

| Table 3 line (secured funding) | Run-off | Logic |
|---|---|---|
| Secured funding transactions backed by **HQLA1**, with any counterparty | 0% | The best collateral. The lender can always sell it or repo it with the central bank. Assumed to roll |
| Secured funding transactions **with any counterparty backed by CLF-eligible debt securities**, where the ADI pledging the assets has a CLF with the RBA, **subject to the ADI's CLF limit** | 0% | Assets the RBA would lend against. Treated like HQLA1 because the ADI has a backstop. With a CLF of zero (section 8.4), this line is empty |
| Secured funding transactions backed by **HQLA2A**, with any counterparty | 15% | Matches the 15% HQLA2A haircut (Att A para 10). The lender is assumed to lend 15% less when it re-sets |
| Secured funding transactions **not eligible for the 0 or 15 per cent categories** above, where the counterparties are **domestic sovereigns, PSEs (but not the RBA) or MDBs with a risk weight of 20 per cent or lower under APS 112** | 25% | Weaker collateral, but the borrower is dealing with a government-type lender who is unlikely to run |
| Secured funding transactions backed by **RMBS eligible for inclusion as HQLA2B** | 25% | Matches the 25% RMBS haircut (Att A para 12(a)) |
| Secured funding transactions backed by **other HQLA2B**, with any counterparty | 50% | Matches the 50% haircut on corporate debt and equities (Att A para 12(b) and (c)) |
| **All other** secured funding transactions | 100% | Collateral that is not HQLA, such as the ADI's own non-HQLA loans or RMBS, is assumed to be refused entirely |

All references: (Att A Table 3).

> **Watch out (matching confidence):** In the published PDF, the rate "25" is printed once in the left column. It lines up with the row about domestic sovereigns, PSEs and MDBs, and no separate number is printed against the RMBS row, which sits directly beneath it. The 25% cell spans both rows, so 25% applies to each. This agrees with the 25% haircut for eligible RMBS in Att A para 12(a) and with the 25% inflow rate for the same collateral in Table 4.

The 0%, 15%, 25%, 25%, 50% and 100% sequence matches the HQLA haircuts exactly (0, 15, 25, 50, and 100 for non-HQLA). A simple way to remember it: **the run-off rate on secured funding is roughly the haircut on the collateral.** The lender's willingness to roll is the same logic as a haircut: it will not lend the part of the value that might not be recovered.

> **Example (hypothetical, not Example Bank):** A bank has repo borrowings maturing in 20 days of A$2.0bn against HQLA2A bonds (15%) and A$1.0bn against its own non-HQLA bonds (100%). Outflows = 2.0 x 15% + 1.0 x 100% = 0.30 + 1.00 = 1.30. Had the A$2.0bn been against Australian Government bonds (HQLA1), the outflow would be zero. Example Bank itself has no secured funding in its balance sheet, so this line is zero.

> **Watch out:** Secured funding that matures *after* 30 days does not run off. And a bank that repos out HQLA1 for 20 days must remove that HQLA1 from its stock (encumbered, Att A para 23) *and* the repo, being at 0%, adds no outflow. The two effects are separate: the bank has less HQLA but no extra outflow.

## 15. Structured financing and the derivative and collateral lines (Att A Table 3)

### 15.1 Asset-backed commercial paper, asset-backed securities, covered bonds and structured financing (Att A Table 3)

This section of Table 3 deals with funding raised through securitisation vehicles and structures. Terms (Chapter 4 has the detail):

- **Asset-backed commercial paper (ABCP):** short-term paper issued by a vehicle and backed by a pool of assets.
- **Asset-backed security:** a bond backed by a pool of loans or receivables.
- **Special purpose vehicle (SPV):** a separate company set up for a specific financing, such as holding a pool of loans.
- **Conduit:** an SPV that funds itself with short-term paper to buy longer-term assets.
- **Structured investment vehicle (SIV):** a vehicle that borrows short term to hold longer-dated securities.

| Table 3 line | Run-off | Logic |
|---|---|---|
| **Maturing transactions issued by the ADI itself** (ABCP, asset-backed securities, covered bonds and other structured financing instruments or facilities) | 100% | Investors are assumed not to buy the bank's new paper or to roll maturing paper. The full maturing amount goes out |
| **Loss of funding on SPVs, conduits and structured investment vehicles** due to inability to refinance maturing debt, embedded options and other potential loss of funding | 100% | If a vehicle that the bank supports cannot roll its debt, the bank is assumed to have to fund it. Applied to the whole potential loss of funding |

(Att A Table 3.)

These lines catch a lesson from the 2007 to 2009 crisis (Chapter 1): banks that sponsored vehicles found they had to put the vehicles' debts back on their own balance sheets.

### 15.2 Increased liquidity needs related to derivatives and other transactions (Att A Table 3 and footnotes 5 and 6)

A **derivative** is a contract whose value depends on something else, such as an interest rate or exchange rate (Chapter 4). Derivatives create liquidity needs because payments and **collateral** (assets handed over to protect the other side) move as values change.

| Table 3 line | Run-off | Plain-words explanation |
|---|---|---|
| **Derivatives cash outflows** (footnote 5) | 100% | The net cash the bank expects to pay on derivatives within 30 days. Footnote 5: payables and receivables are taken into account **net by counterparty**, only where a valid master netting agreement exists, and net of HQLA1 and HQLA2 collateral that is not already counted in the stock of HQLA. An ADI may net payments subject to industry-wide netting agreements with APRA approval. Foreign exchange (FX) derivative cash flows that involve a full simultaneous (or same-day) exchange of principal may be shown net, even without a master netting agreement |
| **Collateral that would need to be posted as a result of a downgrade of 3-notches of the ADI** | 100% | Many derivative contracts say that if the bank's credit rating falls, it must post extra collateral. The scenario assumes a three-notch downgrade (for example AA- to A, counting each step on the rating scale as a notch) and counts the collateral called |
| **Excess non-segregated collateral held by the ADI that could contractually be called at any time by the counterparty** | 100% | Collateral the bank holds, in excess of what it must hold, where the counterparty may demand it back at any time. **Non-segregated** means the collateral is not kept in a separate account, so the bank has mixed it with its own assets and may have used it. The bank is assumed to have to return all of it |
| **Contractually required collateral on transactions for which the counterparty has not yet demanded the collateral be posted** | 100% | Collateral the bank owes under the contract, but the other side has not yet asked for. The bank is assumed to pay once asked, so it counts it all |
| **Contracts that allow collateral substitution to non-HQLA**: the amount of HQLA that may be substituted without the ADI's consent | 100% | The counterparty may swap the HQLA collateral the bank holds for lower-quality assets. The bank loses HQLA it was counting on, so the amount that may be substituted without its consent is treated as lost |
| **Collateral outflows due to market valuation changes on derivative transactions and other transactions** (footnote 6) | 100% of the largest absolute net 30-day collateral flow realised in the past 24 months | A look-back stress. The bank finds the largest 30-day net collateral flow (in either direction, taken as an absolute value) over the past two years and assumes the same happens again. Footnote 6: an ADI may, in certain circumstances, apply to APRA for approval to use an alternative method to calculate these outflows |
| **Valuation changes on posted non-HQLA1 collateral securing derivatives and other transactions** | 20% | If the bank posts non-HQLA1 collateral (for example corporate bonds), its value may fall, so the counterparty may call more. 20% of the posted amount is added to cover this |

All references: (Att A Table 3, footnotes 5 and 6).

> **Example:** Example Bank has net derivative cash outflows within 30 days of A$0.3bn, so 0.3 x 100% = 0.30, and A$0.2bn of collateral to be posted on a 3-notch downgrade, so 0.2 x 100% = 0.20. Total 0.50. Example Bank's other derivative collateral lines are zero (the example keeps the numbers simple).

> **Watch out:** The derivatives amounts are **net** by counterparty, only where there is a valid master netting agreement. Without one, payables and receivables must be treated gross. A **master netting agreement** is a legal contract that lets two parties offset all amounts they owe each other into one net number (Chapter 4). If a bank's data does not record which counterparties have enforceable netting, it cannot use the net number.

## 16. Committed facilities (Att A paras 51 and 52, and Table 3)

### 16.1 Credit facility versus liquidity facility

A **committed facility** is a promise to lend that the bank cannot withdraw. The customer may draw it at any time within its terms. The **undrawn** part is the amount not yet borrowed. In stress, customers rush to draw. The standard divides committed facilities in two (Att A paras 51 and 52).

A **liquidity facility** "is any committed, undrawn back-up facility that would be used to refinance the debt obligations of a customer in situations where such a customer is unable to rollover that debt in financial markets" (Att A para 51). For example, a company issues short-term paper and holds a bank facility as a back-up in case investors will not buy the next issue.

Para 51 also says:

- The amount treated as a liquidity facility is "the amount of the outstanding debt issued by the customer (or proportionate share of a syndicated facility) maturing within a 30-day period that is backstopped by the facility."
- "Any additional capacity of the facility is to be treated as a committed credit facility."
- "General working capital facilities for corporate entities (e.g. revolving credit facilities in place for general corporate or working capital purposes) must not be classified as liquidity facilities, but as credit facilities."

A **credit facility** is a general committed line for ordinary borrowing, such as working capital, expansion, or a revolving credit facility.

**Special rule (Att A para 52):** "Notwithstanding paragraph 51 of this Attachment, any facilities provided to hedge funds, money market funds and special purpose funding vehicles, or other vehicles used to finance an ADI's own assets, must be captured in their entirety as a liquidity facility to a financial institution." So a facility to a hedge fund, money market fund or funding vehicle is always a liquidity facility, for its whole amount, and to a financial institution (so it uses the financial institution rate in section 16.2).

- A **hedge fund** is an investment fund that uses leverage and complex strategies.
- A **money market fund** is a fund that invests in short-term, high-quality debt.

### 16.2 Every rate by counterparty (Att A Table 3)

The rate applies to the **undrawn portion** of committed credit and liquidity facilities (Att A Table 3).

| Counterparty and facility type | Run-off (drawdown) rate |
|---|---|
| Retail and SME customers (credit and liquidity facilities) | 5% |
| Non-financial corporates, sovereigns and central banks, PSEs: **credit facilities** | 10% |
| Non-financial corporates, sovereigns and central banks, PSEs: **liquidity facilities** | 30% |
| Banks and other ADIs subject to prudential supervision (credit and liquidity facilities) | 40% |
| Other financial institutions: **credit facilities** | 40% |
| Other financial institutions: **liquidity facilities** | 100% |
| Other legal entity customers (credit and liquidity facilities) | 100% |

All references: (Att A Table 3).

Reconstruction note: the left-hand rates in this section run 5, 10, 30, 40, then (on the next page) 40, 100, 100. Matching them in order to the rows (retail and SME; corporate credit; corporate liquidity; banks and ADIs; other financial institutions credit; other financial institutions liquidity; other legal entities) was checked against the position of each number in the PDF and gives one rate per row with no ambiguity.

The logic: a corporate with a general credit line usually draws only part of it in a crisis (10%). A corporate that uses a liquidity facility is in the position of having failed to roll its debt, so it is very likely to draw (30%). Other financial institutions (funds, insurers and so on) are the fastest to draw their liquidity lines, which is why those are at 100%, and why any facility to a hedge fund, money market fund or funding vehicle goes there too (Att A para 52). A rate of 100% for other legal entity customers is a catch-all.

> **Example:** Example Bank's committed facilities:
> - Retail and SME undrawn facilities A$10.0bn x 5% = 0.50
> - Non-financial corporate undrawn credit facilities A$5.0bn x 10% = 0.50
> - Non-financial corporate undrawn liquidity facilities A$1.0bn x 30% = 0.30
> Total 1.30.

> **Watch out:** Misclassifying a general revolving credit facility as a liquidity facility moves it from 10% to 30% (for a non-financial corporate). The classification must follow para 51: a liquidity facility is only for refinancing debt the customer cannot roll, and only the amount of debt maturing within 30 days counts. The remaining capacity of the same facility is a credit facility.

## 17. Other contingent funding obligations and other outflows (Att A Table 3)

These are obligations that may call on the bank's cash without a simple balance to apply a rate to.

| Table 3 line | Run-off | Plain-words explanation |
|---|---|---|
| **Revocable credit and liquidity facilities** | 5% | The bank can cancel these at will (unlike committed facilities). It would normally cancel in stress, but may keep funding to protect relationships or its reputation, so a small drawdown is assumed |
| **Trade finance related obligations** | Average of actual monthly net outflows in a recent 12-month period | **Trade finance** is lending and guarantees that support import and export deals (Chapter 4). The rate is not a fixed percentage. The bank uses the average of its actual monthly net outflows over a recent 12-month period |
| **Guarantees and letters of credit other than trade finance related obligations** | 50% of the average of actual monthly net outflows in a recent 12-month period | A **guarantee** is a promise to pay if a customer does not; a **letter of credit** is a bank's promise to pay a seller on the buyer's behalf. These are called on only if the customer fails to perform. The rate is half the average of actual monthly net outflows |
| **Buybacks of domestic Australian debt securities** | 10% for short-term securities and 5% for long-term securities, unless otherwise agreed with APRA | A **buyback** is when the bank repurchases its own debt before it matures, to keep the market liquid or to protect its name. The rate covers a small assumed volume |
| **Non-contractual obligations related to structured products and managed funds** | 5% | The bank has no legal duty to support these, but may feel it must (for example, a fund it manages loses value) |
| **Issuers with an affiliated dealer or market maker** | To be set by the ADI unless APRA determines the rate for the ADI | If the bank (or an affiliate) makes a market in its own securities, it may need to buy them back to keep the market going |
| **Other non-contractual contingent funding obligations** | To be set by the ADI unless APRA determines the rate for the ADI | A catch-all for moral obligations the bank expects to honour |
| **Other contractual cash outflows** | 100% | Any contractual payment due within 30 days that is not covered by another line, such as tax or a supplier invoice. No run-off assumption: the full amount goes out |

All references: (Att A Table 3).

Reconstruction note: the plain text for these rows separates "Average of actual monthly net outflows..." from its row label. Matching by position in the PDF, "Average of actual monthly net outflows in a recent 12-month period" belongs to "Trade finance related obligations", and "50 per cent of the average of actual monthly net outflows in a recent 12-month period" belongs to "Guarantees and letters of credit other than trade finance related obligations". The 10% and 5% apply to buybacks, and the 5% on the next row applies to non-contractual obligations related to structured products and managed funds.

**Rates the ADI sets itself.** Two lines are "to be set by the ADI unless APRA determines the rate for the ADI" (issuers with an affiliated dealer or market maker; other non-contractual contingent funding obligations). Para 32 then applies: the ADI "must be in a position to provide analysis and evidence to justify the assumptions" (Att A para 32). A bank should keep a documented method, data and approval for each such rate. The two trade finance and guarantee lines are also derived from the bank's own history (an average of monthly net outflows), so para 32 applies to them too.

> **Example:** Example Bank has no balances in these lines. If it had A$2.0bn of guarantees (not trade finance), and its average monthly net outflow on them over the last 12 months was A$40m, the outflow would be 50% x 40m = A$20m, not 50% of A$2.0bn. This calculation uses the history of *outflows*, not the face amount of the guarantees.

> **Watch out:** The "average of actual monthly net outflows" is a measure of *cash that actually left*, net of cash that came back. It is not the notional value of guarantees outstanding. A data team that applies a flat percentage to the outstanding guarantee balance is using the wrong base.

## 18. Cash inflows (Att A paras 54 to 66, and Table 4)

### 18.1 Conditions: only performing, contractual inflows (Att A para 54)

"When considering its available cash inflows, an ADI must only include contractual inflows from outstanding exposures that are fully performing and for which it has no reason to expect a default within the 30-day time horizon" (Att A para 54). A **performing** loan is one where the borrower is paying as agreed. So:

- Contractual means written in the loan or contract. Hoped-for or behavioural inflows are not counted.
- Past-due or doubtful loans are excluded.

APRA's safeguard: "Where APRA is of the view that an ADI is overly reliant on cash inflows from one or a limited number of wholesale counterparties, APRA may set an alternative limit on the level of cash inflows that may be included in the LCR in consultation with the ADI" (Att A para 54).

Para 60 adds two timing rules: "All inflows are to be taken only at the latest possible date, based on the contractual rights available to counterparties." And "Inflows from loans that have no specific maturity are not included, with the exception of minimum payments of principal, fee or interest associated with an open maturity loan" (Att A para 60).

> **Example:** A borrower can repay anywhere between day 10 and day 50. The bank takes the inflow at the *latest* possible date, day 50, so it falls outside the 30-day window and counts as zero.

### 18.2 Secured lending: reverse repos and securities borrowing (Att A paras 55 and 56, Table 4)

A **reverse repo** is a repo from the lender's side: the bank gives cash and takes securities as collateral. **Securities borrowing** is a similar arrangement in which the bank borrows securities (Chapter 4).

**The rule (Att A para 55):** the ADI "must assume that maturing reverse repurchase or securities borrowing agreements secured by HQLA1 will be rolled over and will not give rise to any cash inflows (zero per cent)." Agreements secured by other HQLA "are to be modelled as cash inflows, as outlined in Table 4 below, due to the reduction of funds extended against the collateral."

The logic: when a reverse repo matures, the bank lends again. It is assumed to lend a smaller amount if the collateral is weaker, with the difference (the haircut) coming back as a cash inflow. That is why the inflow rates in Table 4 match the haircuts.

**Leveraged trading (Att A para 55):** "Collateralised loans extended to customers for the purpose of taking leveraged trading positions are to be modelled with a 50 per cent cash inflow from contractual inflows made against non-HQLA1 or non-HQLA2." (Table 4's "margin lending" row is at 50%.) **Margin lending** is a loan to buy shares or other securities, secured on those securities (Chapter 4).

**Re-used collateral (Att A para 56):** if collateral obtained through reverse repo, securities borrowing or collateral swaps, maturing within 30 days, "is re-used (i.e. rehypothecated) and is tied up for 30 days or longer to cover short positions", the ADI "must assume that such reverse repo or securities borrowing arrangements will be rolled over and will not give rise to any cash inflows (zero per cent)". A **short position** is a position in which the bank has sold securities it did not own and must buy them back. It must keep the cover in place.

**Table 4: maturing secured lending inflow rates (Att A para 55 and Table 4)**

| Maturing secured lending backed by | Inflow rate (%) if collateral is **not** used to cover short positions | Inflow rate (%) if collateral **is** used to cover short positions |
|---|---|---|
| HQLA1 | 0 | 0 |
| CLF-eligible debt securities, where the ADI receiving assets has a CLF with the RBA subject to the ADI's CLF limit | 0 | 0 |
| HQLA2A | 15 | 0 |
| HQLA2B (eligible residential mortgage-backed securities) | 25 | 0 |
| Other HQLA2B | 50 | 0 |
| Margin lending backed by securities that are not HQLA1, HQLA2 or CLF-eligible securities | 50 | 0 |
| All other collateral | 100 | 0 |

All references: (Att A Table 4).

Reconstruction note: in the plain-text version, the two rate columns are printed apart from the row labels. Using the positions of each number in the PDF, each row shows its first-column rate and a second-column value of 0. The values in the first column in order are 0, 0, 15, 25, 50, 50, 100, matched to the seven rows. This is a confident reading because there are exactly seven rates and seven rows.

> **Why it matters:** Compare the pattern with secured funding (section 14). For secured *funding* the bank borrows, and weaker collateral means a higher run-off. For secured *lending* the bank lends, and weaker collateral means a higher inflow rate. Both reflect the same idea: weaker collateral means the loan is not rolled at full size. For the lender, the part not rolled comes back as cash.

> **Example (hypothetical, not Example Bank):** A bank has a reverse repo of A$1.0bn maturing in 12 days. The collateral is HQLA2A, not re-used for short positions. Inflow = 1.0 x 15% = 0.15. If the collateral were Australian Government bonds (HQLA1), the inflow would be zero. If it were the borrower's own mortgage portfolio (all other collateral), the inflow would be 1.0 x 100% = 1.00.

### 18.3 Lines of credit the ADI holds (Att A para 57)

"Lines of credit, liquidity facilities and other contingent funding facilities that an ADI holds at other institutions for its own purposes receive a zero per cent inflow rate" (Att A para 57). A bank cannot count an undrawn standby line from another bank as an inflow. The bank may not assume its facilities will be honoured in stress. (This also means the CLF counts only through the numerator route in section 8, never as an inflow.)

### 18.4 Foreign ADI head office facility (Att A paras 58 and 59)

APRA may allow a **foreign ADI** to recognise "access to head office funds via a committed funding facility". The facility must meet all of (Att A para 58):

- (a) it is an irrevocable commitment from the branch's head office and is appropriately documented; and
- (b) it is quantified.

This does not apply to a foreign ADI that is part of a group that also has a locally incorporated banking subsidiary in Australia (Att A para 58).

"A foreign ADI may meet up to 50 per cent of its LCR requirement with a head office committed funding facility. The remaining liquidity requirement must be met with eligible liquid assets as detailed in this Attachment" (Att A para 59).

> **Example (hypothetical):** A foreign ADI branch has net cash outflows of A$10.0bn. Its minimum LCR is 40% on an all currencies basis (APS 210 para 55(b)), so the requirement is 40% x 10.0 = A$4.0bn. It may satisfy up to 50% of that requirement with an approved head office facility = A$2.0bn. At least A$2.0bn must be eligible liquid assets.

### 18.5 Retail and SME inflows (Att A para 61)

"An ADI is assumed to receive all fully performing contractual inflows from retail and SME customers. At the same time, however, an ADI is assumed to continue to extend loans to retail and SME customers, at a rate of 50 per cent of contractual inflows. This results in a net inflow rate of 50 per cent of the contractual amount" (Att A para 61).

This is the *rollover assumption*: the bank keeps lending to customers. If A$1.0bn of loan repayments is due, the bank lends out A$0.5bn of new loans, and the net inflow is A$0.5bn.

### 18.6 Other wholesale inflows (Att A para 62)

"An ADI is assumed to receive all fully performing contractual wholesale cash inflows. In addition, an ADI is assumed to continue to extend loans to wholesale clients, at a rate of zero per cent of inflows for financial institutions and central banks, and 50 per cent for all others, including non-financial corporates, sovereigns, PSEs and MDBs. This will result in an inflow rate of" (Att A para 62):

| Counterparty | Assumed new lending | Net inflow rate | Reference |
|---|---|---|---|
| Financial institutions and central banks | 0% | 100% | (Att A para 62(a)) |
| Other entities: non-financial corporates, sovereigns, PSEs, MDBs | 50% | 50% | (Att A para 62(b)) |

"Inflows from maturing securities not included in the stock of HQLA receive an inflow rate of 100 per cent" (Att A para 62).

Footnote 7 applies to SME customers (the definition in para 46, or failing that APS 113 para 40).

### 18.7 Operational deposits placed with others (Att A paras 63 and 64)

"A zero per cent inflow rate applies to deposits held at other financial institutions for operational purposes" (Att A para 63). If your bank holds an operational deposit at another bank, it cannot count that money as an inflow, because it is assumed to be needed there.

"Likewise, the depositing ADI must not count any inflow for deposits held at the centralised institution in a cooperative banking network, which are assumed to stay at the centralised institution. These funds will receive a zero per cent inflow rate" (Att A para 64).

### 18.8 Derivatives and other contractual inflows (Att A paras 65 and 66)

- **Derivatives cash inflows:** "These derivative items receive an inflow rate of 100 per cent" (Att A para 65). Footnote 8: "The treatment in footnote 5 also applies here" (net by counterparty under a valid master netting agreement, net of collateral not already in the HQLA stock, and so on).
- **Other contractual cash inflows:** "receive an inflow rate of 100 per cent. Cash inflows related to non-financial revenues are not taken into account in the calculation of the net cash outflows for the purposes of the LCR" (Att A para 66). So fees for banking services and interest on loans can count if they are contractual; revenue from non-financial activities (such as the sale of property) does not.

### 18.9 Every inflow rate in one table

| Inflow category | Inflow rate | Reference |
|---|---|---|
| Maturing reverse repo or securities borrowing backed by HQLA1 | 0% | (Att A para 55, Table 4) |
| Same, backed by CLF-eligible debt securities (ADI has a CLF) | 0% | (Att A Table 4) |
| Same, backed by HQLA2A | 15% | (Att A Table 4) |
| Same, backed by eligible RMBS (HQLA2B) | 25% | (Att A Table 4) |
| Same, backed by other HQLA2B | 50% | (Att A Table 4) |
| Margin lending backed by non-HQLA, non-CLF securities | 50% | (Att A para 55, Table 4) |
| Same, all other collateral | 100% | (Att A Table 4) |
| Any of the above where the collateral is used to cover short positions | 0% | (Att A para 56, Table 4) |
| Lines of credit, liquidity and contingent facilities held at other institutions | 0% | (Att A para 57) |
| Head office facility of a foreign ADI | Counts towards LCR requirement, up to 50% of it | (Att A paras 58 to 59) |
| Retail and SME performing loans | 50% | (Att A para 61) |
| Wholesale: financial institutions and central banks | 100% | (Att A para 62(a)) |
| Wholesale: non-financial corporates, sovereigns, PSEs, MDBs | 50% | (Att A para 62(b)) |
| Maturing securities not in the HQLA stock | 100% | (Att A para 62) |
| Operational deposits held at other financial institutions | 0% | (Att A para 63) |
| Deposits at the centralised institution of a cooperative banking network | 0% | (Att A para 64) |
| Derivatives cash inflows | 100% | (Att A para 65) |
| Other contractual cash inflows (not non-financial revenues) | 100% | (Att A para 66) |

> **Example (Example Bank):** Contractual repayments due within 30 days:
> - Retail and SME A$1.0bn x 50% = 0.50 (Att A para 61)
> - Non-financial corporates A$0.8bn x 50% = 0.40 (Att A para 62(b))
> - Other banks A$1.0bn x 100% = 1.00 (Att A para 62(a))
> Total inflows = 1.90. (Of Example Bank's A$2.0bn of loans to other banks under 6 months, only the A$1.0bn contractually due within 30 days is in the window.)

## 19. The full Example Bank LCR

All figures in A$ billions. Example Bank is the shared fictional bank used across this guide. It has no CLF, no foreign currency and no secured funding. The derivatives lines are the net amounts given in the guide's data set.

### 19.1 Numerator

| Line | Market value | Haircut | Counted | Reference |
|---|---|---|---|---|
| Cash and balances with the RBA (HQLA1) | 5.0 | 0% | 5.0 | (Att A para 9(a), (b)) |
| Government and semi-government securities (HQLA1) | 12.0 | 0% | 12.0 | (Att A para 9(c)) |
| HQLA2A, HQLA2B | 0.0 | n/a | 0.0 | (Att A paras 10, 12) |
| **Stock of HQLA** | | | **17.0** | (Att A para 6) |

All HQLA1, so the 40% and 15% caps cannot bind (Att A para 6). There is no CLF amount to add.

### 19.2 Cash outflows

| # | Line | Balance | Run-off | Outflow | Reference |
|---|---|---|---|---|---|
| 1 | Retail deposits, stable | 25.0 | 5% | 1.25 | (Att A para 37, Table 3) |
| 2 | Retail deposits, less stable (scorecard 0 to 2) | 15.0 | 10% | 1.50 | (Att A paras 38, 40, Tables 2 and 3) |
| 3 | Retail term deposits (over 30 days, no early withdrawal) | 10.0 | 0% | 0.00 | (Att A paras 41, 42) |
| 4 | SME deposits (qualifying, less stable) | 5.0 | 10% | 0.50 | (Att A para 46, Table 3) |
| 5 | Corporate operational deposits (not fully insured) | 4.0 | 25% | 1.00 | (Att A paras 47 to 50, Table 3) |
| 6 | Corporate non-operational deposits (not fully insured) | 6.0 | 40% | 2.40 | (Att A Table 3) |
| 7 | Financial institution deposits (at call) | 4.0 | 100% | 4.00 | (Att A Table 3) |
| 8 | Wholesale debt maturing within 30 days | 1.0 | 100% | 1.00 | (Att A paras 44, 45, Table 3) |
| 9 | Undrawn committed facilities, retail and SME | 10.0 | 5% | 0.50 | (Att A Table 3) |
| 10 | Undrawn committed credit facilities, non-financial corporates | 5.0 | 10% | 0.50 | (Att A para 51, Table 3) |
| 11 | Undrawn committed liquidity facilities, non-financial corporates | 1.0 | 30% | 0.30 | (Att A para 51, Table 3) |
| 12 | Net derivative cash outflows due within 30 days | 0.3 | 100% | 0.30 | (Att A Table 3, fn 5) |
| 13 | Collateral to be posted on a 3-notch downgrade | 0.2 | 100% | 0.20 | (Att A Table 3) |
| | **Total expected cash outflows** | | | **13.45** | |

Not in the table (outside the 30-day window or not an outflow category): wholesale debt of 30 days to 6 months (A$3.0bn), 6 months to under 1 year (A$2.0bn), 1 year or more (A$15.0bn); other liabilities with no stated maturity (A$2.0bn, see the note below); and shareholders' equity (A$8.0bn).

Check the sum: 1.25 + 1.50 + 0.00 + 0.50 + 1.00 + 2.40 + 4.00 + 1.00 + 0.50 + 0.50 + 0.30 + 0.30 + 0.20 = 13.45.

> **Note on "other liabilities (no stated maturity)":** the shared dataset gives Example Bank's A$2.0bn of other liabilities no outflow rate. Para 45 would bring "funding with an undetermined maturity" into the window for *wholesale funding*. Other liabilities here (such as accruals and provisions) are treated in the worked answer as not being wholesale funding and as having no run-off, in line with the answer figures. In a real bank, each component would be classified, and any that is a contractual payment due within 30 days would fall in "Other contractual cash outflows" at 100% (Att A Table 3).

### 19.3 Cash inflows

| # | Line | Contractual amount | Inflow rate | Inflow | Reference |
|---|---|---|---|---|---|
| 1 | Contractual loan repayments, retail and SME | 1.0 | 50% | 0.50 | (Att A para 61) |
| 2 | Contractual loan repayments, non-financial corporates | 0.8 | 50% | 0.40 | (Att A para 62(b)) |
| 3 | Contractual repayments from other banks | 1.0 | 100% | 1.00 | (Att A para 62(a)) |
| | **Total expected cash inflows** | | | **1.90** | |

### 19.4 Net cash outflows and the ratio

```
Inflow cap            = 75% x 13.45                    = 10.09   (10.0875)
Inflows counted       = min(1.90, 10.09)               = 1.90    (cap not binding)
Net cash outflows     = 13.45 - 1.90                   = 11.55
LCR                   = 17.0 / 11.55                   = 147.2%
Surplus HQLA above 100% = 17.0 - 11.55                 = 5.45
```

(Att A paras 3 and 30.) Example Bank meets the minimum of 100% (APS 210 para 55(a)) with a buffer of 47.2 percentage points.

> **Why it matters:** The largest single contributor to outflows is the 4.00 from financial institution deposits (29.7% of the 13.45), although they are only A$4.0bn of the A$69.0bn of deposits. Next come corporate non-operational deposits (2.40, 17.8%), then stable and less stable retail deposits together (2.75, 20.4%). All A$65.0bn of customer deposits together produce 6.65, or 49.4% of outflows.

## 20. What-if exercises (LCR part)

### 20.1 What-if 1: replace financial institution deposits with retail term deposits

Example Bank replaces A$2.0bn of at-call financial institution deposits with A$2.0bn of retail term deposits over 30 days.

| Line | Before | After |
|---|---|---|
| Financial institution deposits, at call | 4.0 x 100% = 4.00 | 2.0 x 100% = 2.00 |
| Retail term deposits | 10.0 x 0% = 0.00 | 12.0 x 0% = 0.00 |
| **Change in outflows** | | -2.00 |

```
Total outflows  = 13.45 - 2.00 = 11.45
Inflows         = 1.90 (cap: 75% x 11.45 = 8.59, not binding)
Net outflows    = 11.45 - 1.90 = 9.55
LCR             = 17.0 / 9.55 = 178.0%
```

The ratio rises from 147.2% to 178.0%. The funding mix improves because the replaced money was assumed to leave entirely (100%) and the new money is locked up (0%). HQLA is unchanged because the new term money replaces the old money one for one, so the cash held does not change. The effect on the NSFR is in Chapter 6.

### 20.2 What-if 2: lend A$3.0bn of cash as new mortgages

Example Bank lends A$3.0bn of its cash as new standard residential mortgages.

```
HQLA        = 17.0 - 3.0 = 14.0
Net outflows = 11.55 (unchanged: the mortgages are long-term and generate no inflow in 30 days)
LCR          = 14.0 / 11.55 = 121.2%
```

The ratio falls from 147.2% to 121.2%. The bank earns more interest on the mortgages than on cash, but it has lost liquid assets. (The NSFR effect, where the required stable funding rises by 3.0 x 65% = 1.95, is in Chapter 6.)

### 20.3 A third illustration: stable versus term

If instead Example Bank's A$10.0bn retail term deposits were reclassified as demand deposits (for instance because para 42 applies), and treated as less stable at 10%, outflows would rise by 10.0 x 10% = 1.00 to 14.45. Net outflows = 14.45 - 1.90 = 12.55. LCR = 17.0 / 12.55 = 135.5%. This shows how sensitive the ratio is to the classification of a single product. (Cap check: 75% x 14.45 = 10.84, not binding.)

## 21. AUD LCR versus all currencies LCR; the foreign ADI at 40%

### 21.1 Two ratios for a locally incorporated ADI

A locally incorporated LCR ADI must meet a minimum of 100% on **both** an AUD LCR and an all currencies LCR (APS 210 para 55(a)).

- The **all currencies LCR** adds up HQLA and net outflows across every currency, converted into Australian dollars.
- The **AUD LCR** applies the same formula to the Australian-dollar part of the balance sheet only. As generally understood, it uses AUD-denominated HQLA and AUD flows. APS 210 requires the ratio (para 55(a)) but the paragraphs of Attachment A covered in this chapter do not set out a separate AUD calculation procedure. Check APRA's reporting guidance for the exact rules.

Why both? The CLF was designed to cover the AUD shortfall only (Att A paras 13 and 14). Australian banks fund themselves heavily offshore in foreign currency and swap into AUD, and a bank could look healthy in total while being short of AUD assets. The AUD LCR tests the currency the Australian payment system settles in.

APS 210 para 43 requires an ADI active in multiple currencies to maintain liquid assets consistent with the distribution of its liquidity needs by currency (Chapter 8).

For Example Bank, which is all AUD for simplicity, the AUD LCR and the all currencies LCR are both 147.2%.

### 21.2 Foreign ADI

A foreign ADI's minimum is 40%, all currencies basis only (APS 210 para 55(b)). It may meet up to 50% of its LCR requirement with an approved head office committed facility (Att A paras 58 and 59; section 18.4). It must also assess its local operational capacity (APS 210 paras 67 to 69; Chapter 8).

## 22. Common mistakes when computing an LCR from data

| # | Mistake | Why it is wrong | Reference |
|---|---|---|---|
| 1 | **Double counting.** Counting a maturing HQLA bond as both HQLA and an inflow; counting the same collateral in the stock and in the net derivatives figure | A single item cannot appear in both numerator and denominator | (Att A para 31, Table 3 fn 5) |
| 2 | **Treating encumbered assets as HQLA.** Including bonds pledged in repos, in clearing house margin or in payment-system collateral | Only unencumbered, controlled assets count | (Att A paras 22, 23) |
| 3 | **Using original maturity instead of residual maturity.** Excluding a 5-year bond from the 30-day window because it was issued for 5 years | The test is the time remaining. Maturity date minus the reporting date | (Att A paras 6, 41, 45) |
| 4 | **Ignoring the 30-day window.** Including all wholesale debt, or leaving out funding that can be called within 30 days | Only funding that is callable or matures inside 30 days, including undetermined maturity, is counted | (Att A para 45) |
| 5 | **Netting inflows against specific outflows.** Subtracting a bank's loan repayment from the deposit it expects to pay out | Inflows and outflows are summed separately, then the inflow cap is applied once at the total. The only netting allowed is derivatives by counterparty under a valid master netting agreement (and the FX same-day exception) | (Att A para 30, Table 3 fn 5) |
| 6 | **Applying inflow rates to non-performing loans, or to inflows beyond 30 days** | Only performing contractual inflows within the window count, at the latest possible date | (Att A paras 54, 60) |
| 7 | **Forgetting the 75% inflow cap** | Net outflows must be at least 25% of gross outflows | (Att A para 30) |
| 8 | **Applying haircuts to book value or face value** | Haircuts apply to the market value | (Att A paras 9, 10) |
| 9 | **Applying the caps to values before haircut, or forgetting the unwind** | The caps use the adjusted amounts after haircuts, with 30-day secured transactions unwound | (Att A paras 7, 8) |
| 10 | **Classifying sole traders and partnerships as retail** | They are wholesale unless they qualify as SMEs under A$2 million | (Att A paras 34, 46) |
| 11 | **Classifying a term deposit as 0% when customers can break it freely** | It must be a legal no-withdrawal, or a penalty materially greater than lost interest. Practice of waiving this converts the whole category | (Att A paras 41, 42) |
| 12 | **Treating all corporate deposits as operational** | Only deposits tied to clearing, custody or cash management, and not the excess balance, qualify | (Att A paras 47 to 50) |
| 13 | **Misclassifying credit facilities as liquidity facilities** (or the reverse) | A general working capital facility is a credit facility | (Att A para 51) |
| 14 | **Counting CLF or head-office facilities as inflows, or counting standby lines held at other banks** | These receive 0% as inflows | (Att A para 57) |
| 15 | **Counting intermediated deposits as retail without evidence** | They are financial institution deposits (100%) unless all four conditions hold and can be shown | (Att A para 35) |
| 16 | **Assuming a downgraded asset remains eligible forever** | It may stay for an additional 30 days only | (Att A para 25) |
| 17 | **Summing entity LCRs to get a group LCR, or counting trapped surplus liquidity** | The LCR must be met at Level 1 and Level 2, and surplus liquidity is recognised only if freely available | (Att A paras 24, 26, 29) |
| 18 | **Using one rate for both AUD and all currencies** | Both ratios are separately tested | (APS 210 para 55(a)) |

## 23. A checklist of data fields

For each LCR line, a data model should carry at least:

| Area | Fields needed | Reference |
|---|---|---|
| Securities | Security identifier, issuer, issuer type (sovereign, PSE, corporate, financial), currency, market value, class (HQLA1, HQLA2A, HQLA2B, none), rating, encumbrance flag, controlling function, maturity of any secured transaction | (Att A paras 6, 9, 10, 12, 22, 23) |
| Deposits | Customer type (natural person, sole trader, SME, corporate, financial institution, other), aggregate funding per SME, guarantee coverage, operational flag and excess, residual maturity or notice period, early-withdrawal right and penalty, scorecard flags, intermediated flag | (Att A paras 34 to 50) |
| Debt | Residual maturity, earliest investor option date, notice period, secured or unsecured, collateral class | (Att A paras 44, 45, Table 3) |
| Facilities | Committed or revocable, undrawn amount, counterparty type, credit or liquidity, debt backstopped maturing within 30 days | (Att A paras 51, 52, Table 3) |
| Derivatives | Counterparty, netting agreement flag, collateral held and posted, segregated flag, downgrade trigger amounts, 24-month collateral flow history | (Att A Table 3, fns 5, 6) |
| Receivables | Contractual date, latest possible date, performing flag, counterparty type, collateral class and re-use flag | (Att A paras 54 to 66, Table 4) |
| Entity | Legal entity, Level 1 or Level 2, transferability flag, host supervisor rule flag | (Att A paras 24, 26 to 29) |

## Key points

- The LCR is HQLA divided by total net cash outflows over the next 30 calendar days, with a 100% minimum for a locally incorporated ADI on both an AUD and an all currencies basis, and 40% (all currencies) for a foreign ADI (Att A para 3; APS 210 para 55).
- The stock holds only unencumbered, controlled assets in three classes: HQLA1 (no haircut, no limit), HQLA2A (15% haircut) and HQLA2B (25% for eligible RMBS, 50% for corporate debt and equities). HQLA2 is capped at 40% of the stock and HQLA2B at 15% (Att A paras 6, 9, 10, 12).
- The caps are applied after haircuts and after unwinding secured transactions of 30 days or less. In calculation terms HQLA2 is at most two-thirds of adjusted HQLA1 (Att A paras 7, 8).
- As generally understood, Australian HQLA is notes and coin, RBA balances, and Australian Government and semi-government securities. The CLF is still described in APS 210 but has been phased out to zero (Att A paras 13 to 21).
- Outflows are balances multiplied by the Table 3 rates. Retail deposits depend on the stable test and the scorecard; wholesale on counterparty type, operational status and insurance; secured funding on collateral quality; facilities on counterparty and facility type (Att A paras 34 to 53).
- Inflows count only performing contractual amounts at the latest possible date. They are rated 50% for retail, SME and non-financial corporates, 100% for banks and central banks, with secured lending rated by Table 4. Total inflows are capped at 75% of outflows (Att A paras 30, 54 to 66).
- Never double count: an HQLA asset's maturity is not also an inflow (Att A para 31).
- The ratio is very sensitive to classification: a product moved between "term" and "demand", "operational" and "non-operational", or "credit" and "liquidity" can change outflows materially.
- The ADI must keep a buffer above 100%, may use it in stress, and must tell APRA immediately of an actual or likely breach (Att A paras 4, 5).

## Check your understanding

**1.** A locally incorporated ADI has an all currencies LCR of 130% but an AUD LCR of 92%. Does it meet the requirement? Why?

**Answer:** No. A locally incorporated ADI must have each of the AUD LCR and the all currencies LCR at no less than 100% (APS 210 para 55(a)). The AUD LCR of 92% is a breach, even though the all currencies ratio passes. Absent financial stress it must also inform APRA immediately of an actual breach (Att A para 5).

**2.** A hypothetical bank has HQLA1 of 90 and HQLA2A with a market value of 100. How much HQLA2A counts, and what is the stock of HQLA?

**Answer:** After the 15% haircut HQLA2A is worth 100 x 85% = 85. The HQLA2 cap is two-thirds of adjusted HQLA1 = 2/3 x 90 = 60 (Att A para 7). Counted HQLA2A = 60. Stock = 90 + 60 = 150. Excluded = 85 - 60 = 25. Check: 60 / 150 = 40%, which is the 40% cap (Att A para 6).

**3.** Using Example Bank's figures, a corporate customer deposits A$1.0bn as a non-operational deposit that is not fully insured, and the bank holds the cash at the RBA. What is the new LCR?

**Answer:** HQLA rises by 1.0 to 18.0 (cash at the RBA, Att A para 9(b)). The new deposit is a non-operational deposit not fully insured, so the outflow rises by 1.0 x 40% = 0.40 (Att A Table 3), to 13.85. Inflows stay at 1.90 (cap 75% x 13.85 = 10.39, not binding). Net outflows = 13.85 - 1.90 = 11.95. LCR = 18.0 / 11.95 = 150.6%. The ratio improves, because the HQLA gained exceeds the run-off assumed.

**4.** A bank has total expected outflows of 200 and total expected inflows (after applying inflow rates) of 170. What are the net cash outflows? Explain.

**Answer:** The inflow cap is 75% x 200 = 150. Inflows counted = min(170, 150) = 150. Net outflows = 200 - 150 = 50 (Att A para 30). Without the cap it would be 30, which understates the need.

**5.** A government bond that is in the HQLA stock matures in 8 days. Can the bank also count the A$500m repayment as a cash inflow? Why or why not?

**Answer:** No. The bond is already counted as HQLA in the numerator. Counting the repayment as an inflow as well would count the same money twice, which para 31 forbids (Att A para 31). The bond counts in the stock because assets are included as held on day one, irrespective of residual maturity (Att A para 6).

**6.** A depositor has A$300,000 in an on-line account with a promotional rate, and no other products with the ADI. What is the scorecard total and the run-off rate? What would change if the balance were A$100,000?

**Answer:** Balance above A$250,000: 2. On-line: 2. No established relationship: 1. Heavily rate-driven: 1. Total = 6, so 25% (Att A para 40, Tables 1 and 2). If the balance were A$100,000 the balance criterion would score 0, so the total would be 4, still 25%.

**7.** A bank offers a 12-month term deposit with no right to early withdrawal, but in practice lets customers break any deposit on request for a small fee. Which paragraph is relevant, and what is the effect on the LCR?

**Answer:** Paras 41 and 42 apply. A 0% rate is allowed only if the depositor has no legal right to withdraw, or the penalty is materially greater than the loss of interest (Att A para 41). If the ADI allows withdrawal despite a clause saying there is no right, "the entire category of these funds must be treated as demand deposits" (Att A para 42). Outflows therefore rise for the whole pool, at the stable or less stable rate. A hardship policy exception exists (Att A para 43), but a routine fee-based waiver is not hardship.

**8.** Compare the run-off rate on secured funding backed by HQLA1 with that backed by "all other" collateral, and explain the logic.

**Answer:** HQLA1-backed secured funding runs off at 0% and "all other" at 100% (Att A Table 3). The lender holding HQLA1 can always sell or repo the collateral and recover the loan, so it is assumed to roll. A lender holding collateral that is not HQLA may not be able to sell it in a crisis, so it is assumed to refuse to roll. In between, the rate follows the quality of the collateral: 15% for HQLA2A, 25% for eligible RMBS, 50% for other HQLA2B.

## LCR quick reference

### Table A: HQLA classes, haircuts and caps

| Class | Asset | Haircut | Cap | Reference |
|---|---|---|---|---|
| HQLA1 | Notes and coin | 0% | None | (Att A para 9(a)) |
| HQLA1 | Central bank balances drawable in stress | 0% | None | (Att A para 9(b)) |
| HQLA1 | Marketable securities, 0% risk-weighted sovereigns, central banks, PSEs, BIS, IMF, ECB, EU, MDBs, meeting conditions (i) to (iv) | 0% | None | (Att A para 9(c)) |
| HQLA1 | Non-zero risk-weighted sovereign or central bank debt in domestic currency | 0% | None | (Att A para 9(d)) |
| HQLA1 | Non-zero risk-weighted sovereign or central bank foreign-currency debt, up to stressed net outflows in that currency | 0% | None | (Att A para 9(e)) |
| HQLA2A | 20% risk-weighted sovereign, central bank, PSE and MDB securities | 15% | HQLA2 at most 40% of stock (two-thirds of adjusted HQLA1) | (Att A paras 6, 7, 10(a)) |
| HQLA2A | Corporate debt securities (including commercial paper) and covered bonds rated at least AA- | 15% | As above | (Att A para 10(b)) |
| HQLA2B | Eligible residential mortgage-backed securities | 25% | HQLA2B at most 15% of stock (15/85 of adjusted HQLA1 plus HQLA2A, or one quarter of adjusted HQLA1 when the 40% cap binds) | (Att A paras 6, 7, 12(a)) |
| HQLA2B | Corporate debt securities (including commercial paper) rated A+ to BBB- | 50% | As above | (Att A para 12(b)) |
| HQLA2B | Common equity shares meeting conditions | 50% | As above | (Att A para 12(c)) |
| CLF | Contractual CLF amount, lowest of three limbs | Via RBA margins | Approved by APRA, annual review | (Att A paras 13 to 21) |
| Other | Eligible but newly ineligible assets | Kept for an additional 30 calendar days | | (Att A para 25) |

### Table B: every outflow rate (Att A Table 3 and paragraph 53)

| Category | Run-off | Reference |
|---|---|---|
| Retail and qualifying SME: stable deposits | 5% | (Att A para 37, Table 3) |
| Retail and qualifying SME: less stable (score 0 to 2) | 10% | (Att A para 40, Tables 2 and 3) |
| Retail and qualifying SME: higher run-off less stable (score 3 or more) | 25% | (Att A para 40, Tables 2 and 3) |
| Term deposits over 30 days with no withdrawal right or heavy penalty | 0% (excluded) | (Att A para 41) |
| Operational deposits fully covered by deposit insurance | 5% | (Att A Table 3) |
| Operational deposits not fully covered by deposit insurance | 25% | (Att A Table 3) |
| Non-operational, non-financial corporations, sovereigns, central banks, PSEs, MDBs and SMEs over A$2m: fully insured | 20% | (Att A Table 3) |
| Same group: not fully insured | 40% | (Att A Table 3) |
| All other non-operational deposits | 100% | (Att A Table 3) |
| Unsecured debt issuance | 100% | (Att A Table 3) |
| Secured funding backed by HQLA1, any counterparty | 0% | (Att A Table 3) |
| Secured funding backed by CLF-eligible debt securities (ADI has a CLF) | 0% | (Att A Table 3) |
| Secured funding backed by HQLA2A, any counterparty | 15% | (Att A Table 3) |
| Other secured funding with domestic sovereigns, PSEs (not the RBA) or MDBs at risk weight 20% or lower | 25% | (Att A Table 3) |
| Secured funding backed by RMBS eligible as HQLA2B | 25% | (Att A Table 3) |
| Secured funding backed by other HQLA2B, any counterparty | 50% | (Att A Table 3) |
| All other secured funding | 100% | (Att A Table 3) |
| ABCP, asset-backed securities, covered bonds etc.: maturing transactions issued by the ADI | 100% | (Att A Table 3) |
| Loss of funding on SPVs, conduits and SIVs | 100% | (Att A Table 3) |
| Derivatives cash outflows (net by counterparty) | 100% | (Att A Table 3, fn 5) |
| Collateral on a 3-notch downgrade | 100% | (Att A Table 3) |
| Excess non-segregated collateral callable at any time | 100% | (Att A Table 3) |
| Contractually required collateral not yet demanded | 100% | (Att A Table 3) |
| Collateral substitution to non-HQLA (HQLA substitutable without ADI consent) | 100% | (Att A Table 3) |
| Collateral flows from market valuation changes | 100% of the largest absolute net 30-day collateral flow in the past 24 months | (Att A Table 3, fn 6) |
| Valuation changes on posted non-HQLA1 collateral | 20% | (Att A Table 3) |
| Undrawn committed facilities: retail and SME | 5% | (Att A Table 3) |
| Undrawn: non-financial corporates, sovereigns, central banks, PSEs, credit facilities | 10% | (Att A Table 3) |
| Undrawn: same counterparties, liquidity facilities | 30% | (Att A Table 3) |
| Undrawn: banks and other ADIs subject to prudential supervision | 40% | (Att A Table 3) |
| Undrawn: other financial institutions, credit facilities | 40% | (Att A Table 3) |
| Undrawn: other financial institutions, liquidity facilities | 100% | (Att A Table 3) |
| Undrawn: other legal entity customers | 100% | (Att A Table 3) |
| Revocable credit and liquidity facilities | 5% | (Att A Table 3) |
| Trade finance related obligations | Average of actual monthly net outflows in a recent 12-month period | (Att A Table 3) |
| Guarantees and letters of credit other than trade finance | 50% of the average of actual monthly net outflows in a recent 12-month period | (Att A Table 3) |
| Buybacks of domestic Australian debt securities | 10% short-term, 5% long-term, unless otherwise agreed with APRA | (Att A Table 3) |
| Non-contractual obligations related to structured products and managed funds | 5% | (Att A Table 3) |
| Issuers with an affiliated dealer or market maker | Set by the ADI unless APRA determines the rate | (Att A Table 3) |
| Other non-contractual contingent funding obligations | Set by the ADI unless APRA determines the rate | (Att A Table 3) |
| Other contractual cash outflows | 100% | (Att A Table 3) |

### Table C: every inflow rate (Att A paras 54 to 66 and Table 4)

| Category | Inflow rate | Reference |
|---|---|---|
| Reverse repo / securities borrowing backed by HQLA1 | 0% | (Att A para 55, Table 4) |
| Backed by CLF-eligible debt securities (ADI has a CLF) | 0% | (Att A Table 4) |
| Backed by HQLA2A | 15% | (Att A Table 4) |
| Backed by eligible RMBS (HQLA2B) | 25% | (Att A Table 4) |
| Backed by other HQLA2B | 50% | (Att A Table 4) |
| Margin lending backed by securities that are not HQLA1, HQLA2 or CLF-eligible | 50% | (Att A para 55, Table 4) |
| All other collateral | 100% | (Att A Table 4) |
| Any of the above, collateral re-used to cover short positions | 0% | (Att A para 56, Table 4) |
| Lines of credit, liquidity facilities and contingent facilities the ADI holds elsewhere | 0% | (Att A para 57) |
| Retail and SME performing contractual inflows | 50% | (Att A para 61) |
| Wholesale inflows from financial institutions and central banks | 100% | (Att A para 62(a)) |
| Wholesale inflows from non-financial corporates, sovereigns, PSEs, MDBs | 50% | (Att A para 62(b)) |
| Maturing securities not in the HQLA stock | 100% | (Att A para 62) |
| Operational deposits held at other financial institutions | 0% | (Att A para 63) |
| Deposits at the centralised institution of a cooperative network | 0% | (Att A para 64) |
| Derivatives cash inflows | 100% | (Att A para 65) |
| Other contractual cash inflows (excluding non-financial revenues) | 100% | (Att A para 66) |
| Overall cap on inflows | 75% of total expected outflows | (Att A para 30) |

---

# Chapter 6: The Net Stable Funding Ratio, line by line

## 6.1 What the NSFR is and why it exists

The **net stable funding ratio (NSFR)** is a structural test of a bank's balance sheet. Its objective is "to reduce the funding risk of an ADI over a one-year time horizon by requiring an ADI to fund its activities with sufficiently stable sources of funding in order to mitigate the risk of future funding stress" (Att C para 1). An **ADI** is an authorised deposit-taking institution: a bank, building society or credit union licensed under the Banking Act 1959. This chapter uses "bank" and "ADI" interchangeably.

The Liquidity Coverage Ratio (Chapter 5) asks a short question: "if the next 30 days go badly, do we hold enough cash-like assets to get through?" The NSFR asks a slower question: "is the way we fund our loans and securities sensible over a full year?" A bank that funds 25-year mortgages with money that can leave next week is fragile even if it holds a large pile of liquid assets today. The NSFR forces a match between how sticky the funding is and how hard it is to turn the assets into cash.

APS 210 states the principle in the key principles section: "An ADI must ensure that its activities are funded with stable sources of funding on an ongoing basis" (APS 210 para 13).

### Who must meet it

Only some ADIs have to meet the NSFR. "A locally incorporated ADI classified as an LCR ADI must meet the NSFR requirements" (APS 210 para 59), and it "must maintain an NSFR of at least 100 per cent at all times" (APS 210 para 60). APRA may require a higher minimum if it has concerns about the ADI's funding or liquidity risk profile or the quality of its liquidity risk management (APS 210 para 61). Two groups are outside the NSFR:

- **Minimum liquidity holdings (MLH) ADIs**, which are smaller or simpler institutions that follow the regime in Chapter 7 instead (APS 210 paras 52 to 54, 57).
- **Foreign ADIs** (branches of overseas banks), because para 59 refers only to locally incorporated ADIs.

Para 54 adds that an ADI must meet the requirements for its classification "on a continuous basis, absent a situation of financial stress" (APS 210 para 54). In addition, "an ADI must maintain an appropriate buffer above its required NSFR under this Prudential Standard, in line with its liquidity risk tolerance, at all times" (Att C para 4). So 100% is a floor, not a target.

The securitisation carve-out in the application section also matters: an originating ADI that meets the operational requirements for capital relief under APS 120 "may exclude the assets and liabilities of the relevant special purpose vehicles (SPVs) from the calculation of its ... net stable funding ratio (NSFR), as applicable" (APS 210 para 5). For the LCR, by contrast, the SPV cash flows must be included.

Para 5 of Att C says the meanings and definitions in Attachment A (the LCR) apply unless otherwise indicated (Att C para 5). That is why many NSFR categories point back to Attachment A: for example HQLA1, HQLA2A, HQLA2B, stable and less stable deposits, operational deposits, SME and intermediated deposits.

> **Why it matters:** The LCR can be satisfied for 30 days by holding a lot of liquid assets. The NSFR cannot be gamed that way, because liquid assets still need funding, and short-term funding earns little credit. The two ratios together cover the short term and the structure of the balance sheet.

## 6.2 The formula

The NSFR has two components: available stable funding (ASF) and required stable funding (RSF) (Att C para 2). It is calculated as ASF divided by RSF (Att C para 3).

```
            Available stable funding (ASF)
NSFR  =  ---------------------------------   (must be at least 100%)
            Required stable funding (RSF)
```

- **ASF** is the amount of funding the bank can reasonably expect to keep for a year. Each dollar of capital or liabilities is multiplied by a factor from 0% to 100% that reflects how reliable it is.
- **RSF** is the amount of stable funding the bank needs, given how long and how illiquid its assets and off-balance sheet commitments are. Each dollar of assets is multiplied by a factor from 0% to 100%.

An ASF **factor** is a percentage that says how much of a funding source counts as stable. An RSF factor is a percentage that says how much of an asset must be backed by stable funding. A **weighted amount** is a balance after the factor has been applied. Note the direction: a high ASF factor is good for the bank (the funding is sticky); a high RSF factor is bad for the bank (the asset is hard to sell or will be held a long time).

> **Example (the shape of the test):** If a bank had ASF of A$100 and RSF of A$80, its NSFR would be 125%. If ASF fell to A$75 and RSF stayed at A$80, the NSFR would be 93.75%, which is a breach of the 100% minimum (APS 210 para 60).

## 6.3 Available stable funding (ASF)

### 6.3.1 Definition and method

ASF is "the portion of capital and liabilities expected to be reliably provided over a one-year time horizon". It is "measured based on the broad characteristics of the relative stability of an ADI's funding sources, including the contractual maturity of its liabilities and the differences in propensity of different types of funding providers to withdraw their funds" (Att C para 6). Two ideas are embedded here:

1. **Contractual maturity**: the date the contract says the money must be repaid. Funding that does not need to be repaid for more than a year is stable on its face.
2. **Propensity to withdraw**: how likely a type of customer is to take money out early. A salary account of a household is less likely to leave than an at-call deposit from a hedge fund.

The method has three steps (Att C para 7):

1. Assign the **carrying value** of the ADI's capital and liabilities to the relevant ASF category (Att C paras 11 to 15).
2. Multiply the amount in each category by the ASF factor to get a weighted amount.
3. Sum the weighted amounts.

Footnote 9 explains that the **carrying value** "represents the amount of a liability or equity instrument before application of any regulatory deductions, filters or other adjustments" (Att C para 7, footnote 9). Carrying value is the amount shown on the balance sheet under the accounting rules; it is not the face value on the bond certificate and not the market value. The same footnote matters for equity: capital is taken before regulatory deductions, which is why the 100% factor is applied to the total of regulatory capital "before the application of regulatory adjustments" (Att C para 11(a)).

### 6.3.2 Maturity of funding

For funding with a **withdrawal notice period** (a period the customer must wait after asking for money back) or with an **option** (a contractual right for one side to change the maturity, such as to call or redeem early), the rule is conservative: "assume the maturity date as being the earliest date at which the funds may be redeemed" (Att C para 8). So a five-year bond that the holder can put back to the bank (force the bank to repay) after eight months is treated as an eight-month liability for NSFR purposes.

For long-dated liabilities, a split is allowed: "only that portion of cash flows falling on or after the six-month and one-year time horizons may be treated as having an effective residual maturity of six months or more and one year or more, respectively" (Att C para 8). Put plainly, a liability that amortises (pays back in instalments) is cut into slices by when each slice is due.

The word **residual maturity** means the time remaining until the contractual end date, measured from the reporting date. It is different from **original maturity**, which is the term when the instrument was issued. A bond issued 5 years ago for 5 years and a year has residual maturity of 1 year even though it was originally a 5-year bond. The NSFR uses residual maturity for liabilities and assets.

> **Worked example:** A bank issued a three-year bond of A$100m. At the reporting date it has 14 months to run. The whole A$100m is a "one year or more" liability (100% ASF, Att C para 11(c)). Three months later it has 11 months to run and falls into the 6-months-to-under-1-year group (50% ASF if the holder is a financial institution, Att C para 14(f)).

> **Watch out:** Para 11(c) says cash flows due in less than one year that arise from a liability with a final maturity greater than one year do not qualify for 100%. So if a bond has a final maturity of three years but pays a large coupon in six months, the part due within a year must be bucketed separately.

### 6.3.3 Derivative liabilities

A **derivative** is a contract whose value depends on something else (an interest rate, an exchange rate, a bond price). A **derivative liability** exists when the contract is currently worth a negative amount to the bank, meaning the bank would have to pay if the contract were closed out today. The NSFR rule for amounts is:

- Calculate derivative liabilities "based on the replacement cost for derivative contracts (obtained by marking-to-market) where the contract has a negative value" (Att C para 9). **Replacement cost** is what it would cost today to replace the contract. **Marking-to-market** means revaluing at today's market prices.
- If an eligible bilateral netting contract is in place that meets the conditions in paragraphs 9 to 11 of Attachment H of APS 112 and paragraphs 8 and 9 of the annex of the Basel III leverage ratio framework (as it existed at 12 January 2014), then the replacement cost for the set of exposures covered by the contract is the net replacement cost (Att C para 9 and footnote 10). **Netting** means offsetting positive and negative values between the same two parties so that only the difference counts.
- Deduct "any collateral posted in the form of variation margin in connection with derivative contracts, regardless of the asset type, from the negative replacement cost amount" (Att C para 10). **Variation margin** is collateral that moves day to day as the contract's value changes. Footnote 11 gives the formula:

```
NSFR derivative liabilities = derivative liabilities
                              - total collateral posted as variation margin on derivative liabilities
```

Footnote 12 closes a loophole: where the variation margin posted is deducted from the replacement cost, the bank "must not include an asset on its balance sheet associated with collateral posted as variation margin" when computing RSF (Att C para 10, footnote 12). Otherwise the same dollar would be netted in the liabilities calculation and also charged in RSF.

There is a separate 20% add-on for derivative liabilities on the asset (RSF) side, discussed in 6.5.8 (Att C para 37(d) and footnote 20). And derivative liabilities are netted against derivative assets for the zero-percent ASF treatment (Att C para 15(c)).

### 6.3.4 ASF categories

The standard has five ASF factors: 100%, 95%, 90%, 50% and 0%. The tables below set out every limb.

#### ASF 100% (Att C para 11)

| Limb | What it covers | Notes |
|---|---|---|
| 11(a) | The total amount of regulatory capital, before regulatory adjustments, as defined in APS 111 | Excludes the part of Tier 2 instruments with residual maturity under one year |
| 11(b) | Any capital instrument not in 11(a) with an effective residual maturity of one year or more | Excludes instruments with explicit or embedded options that, if exercised, would reduce expected maturity to under one year |
| 11(c) | Secured and unsecured borrowings and liabilities, including term deposits, with an effective residual maturity of one year or more | Cash flows due within one year from liabilities with a final maturity beyond one year are not eligible for 100% |

**Regulatory capital** is the owners' money plus certain debt-like instruments that count as loss-absorbing under the capital standards (Common Equity Tier 1, Additional Tier 1 and Tier 2; see Chapter 3). **Tier 2** instruments are subordinated debt that counts as capital; as they approach maturity they stop being reliable, which is why the part with residual maturity under one year is excluded (Att C para 11(a)).

#### ASF 95% (Att C para 12)

| Limb | What it covers | Cross-reference |
|---|---|---|
| 12(a) | Stable demand deposits and term deposits with residual maturity under one year, from retail and SME customers | Stable: Att A para 37 (footnote 13). Retail: Att A para 34 (footnote 14). SME definition: Att A para 46 and footnote 9 |
| 12(b) | Intermediated deposits that meet Att A para 35 for treatment as stable retail deposits, where the intermediary cannot replace the ADI unless it gives at least 12 months' notice | |

In plain terms: a **stable deposit** is the portion of a retail deposit fully covered by the Financial Claims Scheme (the government deposit guarantee, covering deposits up to A$250,000 per account holder per ADI) where the depositor has other established relationships with the ADI, or the deposit is in a transactional account such as one receiving salary (Att A para 37). **Retail** means placed by a natural person (Att A para 34). **SME** is a small or medium enterprise whose funding is treated like retail where it is managed as a retail exposure and aggregate funding is under A$2 million (Att A para 46). An **intermediated deposit** is one a person places through an intermediary, such as a platform or adviser, and the ADI places the funds on their behalf (Att A para 35).

#### ASF 90% (Att C para 13)

| Limb | What it covers | Cross-reference |
|---|---|---|
| 13(a) | Less stable demand deposits and term deposits with residual maturity under one year, from retail and SME customers | Less stable: Att A para 38 (footnote 15) |
| 13(b) | Intermediated deposits, including member-directed superannuation deposits, meeting Att A para 35 for treatment as less stable retail deposits, where the intermediary cannot replace the ADI unless it gives at least 12 months' notice | |

A **less stable deposit** is the portion of a retail deposit that does not meet the stable test (Att A para 38). The LCR distinguishes between less stable deposits scoring 0 to 2 (10% run-off) and 3 or more (25% run-off) on the scorecard (Att A paras 40). The NSFR does not. All less stable retail and SME deposits get 90%.

#### ASF 50% (Att C para 14)

| Limb | What it covers | Cross-reference |
|---|---|---|
| 14(a) | Secured and unsecured funding with residual maturity under one year, from non-financial corporate customers | |
| 14(b) | Operational deposits | Att A paras 47 to 50 (footnote 16) |
| 14(c) | Superannuation fund deposits that meet the definition of operational deposits | Footnote 17 refers back to footnote 16 |
| 14(d) | Intermediated deposits, including member-directed superannuation deposits, meeting Att A para 35 where the intermediary cannot replace the ADI unless it gives at least six months' notice | |
| 14(e) | Funding with residual maturity under one year from sovereigns, public sector entities (PSEs) and multilateral development banks (MDBs) and national development banks | |
| 14(f) | Other funding, secured and unsecured, not in the categories above, with residual maturity from six months to under one year, including funding from central banks and financial institutions | |

A **non-financial corporate** is a company that is not a financial institution (for example a retailer or a mining company). A **financial institution** includes a money market corporation, finance company, friendly society and the trustee of a superannuation or pension fund, public unit trust or mutual fund, or cash management trust (APS 210 para 10(b)). A **PSE** is a public sector entity (such as a government agency or state body) and an **MDB** is a multilateral development bank (such as the World Bank). An **operational deposit** is a deposit a customer keeps with the bank to use clearing, custody or cash management services where it has a substantive dependency on the bank, and excess balances do not qualify (Att A paras 47 to 50).

Note how 14(f) works with 15(a): funding from financial institutions and central banks with a residual maturity of six months to under a year is 50%, but under six months it is zero.

#### ASF 0% (Att C para 15)

| Limb | What it covers | Cross-reference |
|---|---|---|
| 15(a) | All other liabilities and equity categories not in paras 11 to 14, including other funding with residual maturity under six months from central banks and financial institutions | Footnote 18: cooperative network exception |
| 15(b) | Other liabilities without a stated maturity, including short positions and open maturity positions | Exceptions: deferred tax liabilities and minority interests |
| 15(c) | If NSFR derivative liabilities exceed NSFR derivative assets, the excess | Footnote 19 formula |
| 15(d) | Trade date payables from the purchase of financial instruments, foreign currencies and commodities that are expected to settle within the standard settlement cycle, or have failed to settle but are still expected to | |

Points to notice:

- **Short position**: an obligation to deliver a security the bank has sold but does not own, usually created by borrowing the security and selling it. It has no stable maturity, so it gets 0%.
- **Exceptions in 15(b):** deferred tax liabilities are treated "according to the nearest possible date on which such liabilities could be realised", and minority interests (the share of a subsidiary owned by outsiders) "according to the term of the instrument, usually in perpetuity". They get 100% if the effective maturity is one year or greater, or 50% if between six months and under one year (Att C para 15(b)(i), (ii)).
- **Footnote 18 (cooperative networks):** subject to APRA's approval, deposits between ADIs in the same cooperative network may be excluded from the 0% category if they are required by law to be placed at the central organisation, or are placed in the context of common task sharing under legal, statutory or contractual arrangements where both ADIs take part in the same network's mutual protection scheme. Such deposits may receive an ASF up to the RSF factor assigned for the same deposits to the depositing bank, not to exceed 85% (Att C para 15, footnote 18).
- **Footnote 19** gives the arithmetic for 15(c): ASF = 0% x MAX((NSFR derivative liabilities - NSFR derivative assets), 0). It is zero by construction. The reason for stating it is to show that the net derivative liability amount is placed in the 0% bucket rather than ignored.
- **Para 28 link:** any balance sheet liability for variation margin received that does not meet the offset conditions, and any initial margin received, "must not offset derivative assets and must be assigned a zero per cent ASF factor" (Att C para 28).

> **In the standard:** The ASF factor list is complete: 100% (11), 95% (12), 90% (13), 50% (14), 0% (15). Para 15(a) is the "catch-all": anything not listed earlier gets zero.

### 6.3.5 The pattern behind the ASF factors

Why these sizes? Each factor is a judgement about how much of a funding source would remain after a year of stress.

| Factor | Intuition |
|---|---|
| 100% | Money the bank can keep for the full year: owners' capital and any borrowing that does not need to be repaid within a year |
| 95% | Insured, relationship-based retail money. Even in a crisis most of it stays. Five percent is allowed to leave |
| 90% | Retail and small-business money that is less sticky (high balances above A$250,000, online-only, rate-driven or no relationship). Still considered fairly reliable, but 10% could go |
| 50% | Money from customers who are more likely to leave than households but not as flighty as banks: corporates, sovereigns, operational deposits, and money maturing in six to twelve months. Half is assumed to stay |
| 0% | Funding that can leave within six months or has no maturity at all, and funding from financial institutions that may withdraw first |

Notice the ASF factors for deposits are much higher than the LCR run-off rates would suggest by simple subtraction. For stable retail deposits the LCR run-off is 5% in 30 days (Chapter 5), and the NSFR haircut is 5% over a year (95% ASF). The factors are regulatory calibrations set by the Basel Committee and adopted by APRA. They are not derived by scaling a 30-day rate up to a year, and this guide does not claim to know the precise data behind each number; the intuition column above is an interpretation, not wording from the standard.

## 6.4 Required stable funding (RSF): the method

RSF is "the minimum amount of stable funding an ADI is required to hold and is a function of the liquidity characteristics and residual maturities of the various assets held by an ADI including off-balance sheet (OBS) exposures" (Att C para 16). An **off-balance sheet (OBS) exposure** is a commitment that is not an asset or liability today but could become one, such as an undrawn credit line.

The method mirrors the ASF method (Att C para 17):

1. Assign the ADI's assets, at carrying value, and OBS exposures to the relevant RSF category (Att C paras 29 to 37).
2. Multiply each amount by the RSF factor (for OBS items, the "potential liquidity exposure").
3. Sum the weighted amounts.

Allocation follows "the asset's residual maturity or liquidity value" (Att C para 18).

Footnote 20 to para 17 adds two things. First, for NSFR purposes HQLA means all HQLA "without regard to LCR operational requirements and LCR caps on HQLA2 and HQLA2B". So the 40% and 15% caps of the LCR (Att A paras 6 to 8) do not limit what counts as HQLA1, HQLA2A or HQLA2B for RSF. HQLA is defined in Att A paras 6 to 29 and operational requirements in Att A paras 22 to 29 (Att C para 17, footnote 20). Second, assets for NSFR purposes "include 20 per cent of derivative liabilities calculated in accordance with paragraph 9" (the add-on in 6.5.8).

> **Why it matters:** An asset that qualifies as HQLA2A under the LCR but would be excluded by the 40% cap still gets the 15% factor in the NSFR, because the NSFR ignores the caps. A data model that reuses LCR "counted" amounts for the NSFR would get the wrong answer.

### 6.4.1 Trade date accounting

Para 19 handles purchases and sales that have been agreed but not yet settled. The bank "must include financial instruments, foreign currencies and commodities for which a purchase order has been executed". It "may exclude" those for which a sales order has been executed, even if such transactions are not yet on the balance sheet under a settlement-date accounting model, provided that (i) they are not reflected as derivatives or secured financing transactions on the balance sheet and (ii) the effects will be reflected in the balance sheet when settled (Att C para 19). In effect the bank counts what it has bought and is about to hold, and may remove what it has sold and is about to deliver.

### 6.4.2 Maturity of assets

The rule for assets is the opposite of the rule for liabilities. For liabilities the earliest redemption date is used (Att C para 8). For assets the bank must "assume the maturity date as being the latest possible date at which the asset may mature" and, for an asset with an option to extend, assume the option "will be exercised" (Att C para 20). Both choices are conservative: money is assumed to leave as early as possible and to come back as late as possible.

| Situation | Treatment | Reference |
|---|---|---|
| Asset with an option to extend maturity | Assume the option is exercised (latest possible maturity) | Att C para 20 |
| Asset with no defined maturity, or maturity subject to periodic review | Classify as residual maturity of one year or more and apply that RSF factor | Att C para 21 |
| Amortising loan, or loan with minimum contractual payments | The portion due within the one-year horizon may be included in the under-one-year category | Att C para 22 |

An **amortising loan** is one repaid in instalments of principal over its life, such as a principal-and-interest mortgage. Para 22 uses the word "may", so splitting is permitted, not compulsory.

> **Example:** A A$10m business loan to a non-financial corporate has 3 years left and requires A$1m of principal to be repaid within the next 12 months. The A$1m can go into the under-one-year category (50% RSF, Att C para 34(f)) and A$9m into the one-year-or-more category (85%, Att C para 36(b)). RSF = 0.50 + 7.65 = A$8.15m, against A$8.5m if the whole loan were classed as one year or more.

### 6.4.3 Encumbered assets (paras 23 to 24)

An asset is **encumbered** when it has been pledged or otherwise committed so that the bank cannot freely sell or reuse it. Footnote 21 says encumbered assets "include but are not limited to assets backing securities or covered bonds and assets pledged in securities financing transactions or collateral swaps" (Att C para 23, footnote 21). The longer an asset is locked up, the less it helps the bank, so its factor rises. The decision table applies Att C para 23 to an asset with a given remaining encumbrance period, where X is the factor the asset would receive if unencumbered.

| Remaining encumbrance period | Unencumbered factor X | RSF factor to apply | Reference |
|---|---|---|---|
| One year or more | Any | 100% | Att C para 23 (also para 37(a)) |
| Six months to under one year | X is 50% or lower | 50% | Att C para 23 |
| Six months to under one year | X is higher than 50% | X (the higher factor) | Att C para 23 |
| Under six months | Any | X (same as an equivalent unencumbered asset) | Att C para 23 |

Para 34(b) is consistent: any HQLA encumbered for between six months and less than one year gets 50% (Att C para 34(b)).

> **Example:** A bank holds A$100m of government securities (unencumbered factor 5%). It repos them (sells with an agreement to buy back) for 9 months. Encumbered for six months to under a year with X of 5% (below 50%), the factor becomes 50%, so RSF is A$50m instead of A$5m. If the repo is for 3 months, the factor stays 5% (A$5m). If it is for 18 months, it is 100% (A$100m). A mortgage with X of 65% encumbered for 9 months stays at 65%, because 65% is higher than 50%.

**Exceptional central bank operations.** Where an asset is encumbered for exceptional central bank liquidity operations, "the asset may be given a lower RSF factor if approval is sought from APRA and APRA agrees to the lower RSF factor" (Att C para 24). Footnote 22 explains that exceptional central bank liquidity operations are "non-standard, temporary operations conducted by a central bank in order to achieve its mandate in a period of market-wide financial stress and/or exceptional macroeconomic circumstances". APRA exercises such discretions in writing (APS 210 para 8).

> **Watch out:** Para 23 looks at the remaining period of the encumbrance, not the maturity of the asset. A 10-year bond pledged for 4 more months is, for this test, encumbered for under six months. It takes the factor for an unencumbered 10-year bond, not 100%.

### 6.4.4 Secured financing transactions (paras 25 to 26)

A **securities financing transaction** is a deal where securities are used as collateral to borrow or lend cash, or are lent against other securities. The main types are a **repurchase agreement (repo)**, where the bank sells securities with an agreement to buy them back; a **reverse repo**, where it buys securities with an agreement to sell them back; and a **collateral swap**, where one set of securities is swapped for another. The question for the NSFR is who keeps **beneficial ownership**, meaning who bears the risks and receives the rewards of the securities.

| Situation | Treatment | Reference |
|---|---|---|
| Securities borrowed (for example under a reverse repo or collateral swap) where the ADI does not retain beneficial ownership | Exclude from the ADI's assets amount | Att C para 25 |
| Securities lent where the ADI retains beneficial ownership | Include | Att C para 25 |
| Securities received through collateral swaps that do not appear on the ADI's balance sheet | Do not include | Att C para 25 |
| Securities encumbered in repos or other financing, where the ADI keeps beneficial ownership and they stay on its balance sheet | Allocate to the appropriate RSF category (applying the encumbrance rules in 6.4.3) | Att C para 25 |
| Netting of securities financing transactions with a single counterparty | Permitted if the netting conditions in para 38 of Attachment D of APS 110 are met | Att C para 26 |

Footnote 28 (on para 37(a)) says that for a non-maturity (open) reverse repo, 100% RSF applies unless the ADI can demonstrate to APRA's satisfaction that it would effectively have a different maturity period (Att C para 37, footnote 28).

### 6.4.5 Derivative assets (paras 27 to 28)

A **derivative asset** is a derivative contract with a positive value to the bank. It is measured at replacement cost (marked to market), using the net replacement cost where an eligible bilateral netting agreement meets the conditions in paras 9 to 11 of Attachment H of APS 112 and paras 8 and 9 of the annex of the Basel III leverage ratio framework (as at 12 January 2014) (Att C para 27 and footnote 23).

Collateral received against a derivative asset must not reduce the positive replacement cost "regardless of whether or not netting is permitted under an ADI's operational accounting or risk-based framework", except cash variation margin that meets the conditions in para 23 of Attachment D to APS 110 and is in the same currency as the currency of settlement of the contract (Att C para 28 and footnote 24). Any other liability for variation margin received, and any initial margin received, cannot offset derivative assets and gets 0% ASF (Att C para 28).

The net position then goes to one side only:

```
If NSFR derivative assets > NSFR derivative liabilities:
    RSF = 100% x (NSFR derivative assets - NSFR derivative liabilities)
          (Att C para 37(b), footnote 29: 100% x MAX(assets - liabilities, 0))

If NSFR derivative liabilities > NSFR derivative assets:
    the excess is a liability with ASF = 0% x excess = 0
          (Att C para 15(c), footnote 19)
```

Separately, 20% of gross derivative liabilities (before deducting variation margin posted) is added to RSF (Att C para 37(d)).

## 6.5 RSF categories

The standard lists eight RSF factors: 0%, 5%, 10%, 15%, 50%, 65%, 85% and 100% (Att C paras 29 to 37), plus off-balance sheet factors (paras 41 to 42). Every asset must land in exactly one category, so work from the top (0%) down. Para 30 makes this explicit: the 5% group includes unencumbered HQLA1 but excludes "assets receiving a zero per cent RSF factor as specified in paragraph 29" (Att C para 30).

### 6.5.1 RSF 0% (Att C para 29)

| Limb | Asset | Notes |
|---|---|---|
| 29(a) | Notes and coins immediately available to meet obligations | |
| 29(b) | Central bank reserves and balances | Footnote 25: APRA may impose a higher RSF factor after discussing and agreeing with the relevant central bank, taking into account whether a reserve requirement must be satisfied at all times and whether it exists over a longer horizon and so needs associated stable funding |
| 29(c) | All claims on central banks with a residual maturity of under six months | |
| 29(d) | Trade date receivables from the sale of financial instruments, foreign currencies and commodities expected to settle within the standard settlement cycle, or failed but still expected to settle | |

A claim on a central bank is money the bank holds at, or lends to, the central bank (in Australia, the Reserve Bank of Australia, RBA). Balances at the RBA are used for settling payments between banks and can be drawn on demand, which is why they carry no funding requirement.

### 6.5.2 RSF 5% (Att C para 30)

Unencumbered HQLA1 that is not already in the 0% group. Two limbs:

| Limb | Asset | Notes |
|---|---|---|
| 30(a) | Marketable securities representing claims on, or guaranteed by, sovereigns, central banks, PSEs, the BIS, the IMF, the ECB and EU or MDBs, assigned a 0% risk weight under Attachment B of APS 112 | These are the HQLA1 securities in Att A para 9(c) |
| 30(b) | Certain non-zero risk-weighted sovereign or central bank debt securities as specified in paras 9(d) and (e) of Attachment A | The HQLA1 categories for non-zero risk-weighted sovereigns |

A **risk weight** is a percentage used in the capital standards to say how risky an exposure is (0% for the safest sovereign claims). A **sovereign** is a national government. A **marketable security** is a debt instrument that can be sold in an active market.

As generally understood (see Chapter 5 for the verification note), the Australian dollar assets that qualify as HQLA1 are notes and coin, balances at the RBA, and Australian Government and semi-government (state and territory) securities. In Example Bank, the government and semi-government securities therefore fall in the 5% group (Att C para 30(a)).

> **Watch out:** "Unencumbered HQLA1" is the key phrase. A government bond repo'd for 12 months or more is 100% (Att C para 23). The same bond encumbered for six months to under 12 months is 50% (Att C paras 23 and 34(b)).

### 6.5.3 RSF 10% (Att C paras 31 and 32)

| Limb | Asset | Notes |
|---|---|---|
| 31 (must) | Unencumbered loans to financial institutions with residual maturity under six months, where the loan is secured against HQLA1 (Att A para 9) and the ADI can freely rehypothecate the collateral for the life of the loan | **Rehypothecate** means re-use the collateral received, for example by pledging it onwards |
| 32(a) (may) | CLF-eligible third-party debt securities, other jurisdictions' ALA (alternative liquid assets) and assets recognised as eligible liquid assets by a host supervisor that APRA allows in the numerator of the LCR | 10% applies only to the lower of the carrying value and the amount of the CLF that can be included in the LCR numerator |
| 32(b) (may) | Self-securitised assets eligible as CLF collateral | Maximum amount at 10% is the ADI's CLF less eligible third-party debt securities held as collateral for the CLF |

Para 31 is mandatory ("must"); para 32 says "may" and so is at the ADI's election.

The **Committed Liquidity Facility (CLF)** was an arrangement under which the RBA committed, for a fee, to repo qualifying securities from banks so that those banks could count the commitment towards the LCR (the CLF is described in Att A paras 13 to 21; see Chapter 5). As generally understood, and consistent with APRA and RBA web pages checked at the time of writing, APRA announced in September 2021 that LCR ADIs should reduce reliance on the CLF to zero by the end of 2022, and RBA material later reported that CLF allowances had been reduced to zero. That leaves para 32 largely dormant in practice, though the text remains in the July 2025 version.

### 6.5.4 RSF 15% (Att C para 33)

| Limb | Asset | Notes |
|---|---|---|
| 33(a) | Unencumbered HQLA2A assets (Att A para 10) | Certain government-related securities with a 20% risk weight, and corporate debt and covered bonds meeting the criteria in Att A para 10 |
| 33(b) | All other unencumbered loans to financial institutions with residual maturity under six months not in para 31 | Unsecured, or secured by something other than HQLA1 |

Example Bank's A$2.0bn of unsecured loans to other banks under six months falls here (Att C para 33(b)).

### 6.5.5 RSF 50% (Att C para 34)

| Limb | Asset | Notes |
|---|---|---|
| 34(a) | Unencumbered HQLA2B assets (Att A para 12) | Eligible RMBS, certain corporate debt and common equity shares |
| 34(b) | Any HQLA that is encumbered for between six months and under one year | See the encumbrance table in 6.4.3 |
| 34(c) | All loans to financial institutions and central banks with residual maturity of six months to under one year | |
| 34(d) | Operational deposits held at other ADIs that are subject to the 50% ASF factor in para 14(b) | A bank's own operational deposits placed at another bank |
| 34(e) | Australian equities, other than financial institutions or associated entities (section 50AAA of the Corporations Act 2001), that trade on the ASX and form part of the S&P/ASX200 index | |
| 34(f) | All other non-HQLA not in the above categories that have residual maturity under one year, including loans to non-financial corporates, loans to retail customers (natural persons) and SME customers, and loans to sovereigns and PSEs | |

Para 34(f) is the home of short-term lending. Example Bank's A$8.0bn of personal and business loans under one year falls here (Att C para 34(f)).

### 6.5.6 RSF 65% (Att C para 35)

| Limb | Asset | Notes |
|---|---|---|
| 35(a) | Unencumbered standard residential property loans to an individual or individuals (natural persons) with residual maturity of one year or more and a loan-to-valuation ratio (LVR) of 80% or below, as defined under APS 112 | LVR is the loan amount divided by the property value |
| 35(b) | Other unencumbered loans not in the above, excluding loans to financial institutions, with residual maturity of one year or more that are subject to or would qualify for a 35% or lower risk weight under APS 112 | |

Para 35(a) is where most mortgages sit. A mortgage that fails the test (for example, an LVR above 80%, or a loan that is not a standard residential loan) is not in 35(a). If it is performing, has a residual maturity of one year or more and is not in 35(b), it takes 85% under para 36(b).

### 6.5.7 RSF 85% (Att C para 36)

| Limb | Asset | Notes |
|---|---|---|
| 36(a) | Cash, securities or other assets, on or off balance sheet, posted as initial margin for derivative contracts, and cash or other assets provided to the default fund of a central counterparty (CCP) | Securities posted as initial margin that would otherwise receive a higher factor take the higher factor. Footnote 26: initial margin posted on behalf of a customer, where the ADI does not guarantee the third party's performance, is exempt |
| 36(b) | Other unencumbered performing loans that do not qualify under para 35 with residual maturity of one year or more, excluding loans to financial institutions | Footnote 27: performing or non-performing is determined by reference to APS 220 Credit Risk Management |
| 36(c) | Unencumbered securities with remaining maturity of one year or more, and exchange-traded equities, that are not in default and do not qualify as HQLA | |
| 36(d) | Physical traded commodities, including gold | |

**Initial margin** is collateral posted up front when a derivative is entered into, to cover possible future losses; unlike variation margin it does not move with day-to-day value. A **central counterparty (CCP)** is a clearing house that stands between the two sides of a trade. A **default fund** is a pool contributed to by members of the CCP to cover the loss if a member fails. A **performing loan** is one being repaid as agreed; a non-performing loan is in default or arrears.

### 6.5.8 RSF 100% (Att C para 37)

| Limb | Asset | Notes |
|---|---|---|
| 37(a) | All assets encumbered for one year or more | Footnote 28 on non-maturity reverse repos |
| 37(b) | NSFR derivative assets net of NSFR derivative liabilities, if assets exceed liabilities | Footnote 29 formula |
| 37(c) | All other assets not in the above categories, including non-performing loans, loans to financial institutions with residual maturity of one year or more, non-exchange-traded equities, fixed assets, items deducted from regulatory capital (as defined in APS 111), retained interest, insurance assets, subsidiary interests and defaulted securities | |
| 37(d) | 20% of derivative liabilities (negative replacement cost amounts) calculated under para 9, before deducting any variation margin posted | |

A **fixed asset** is something like a building or equipment. **Goodwill** and other items deducted from regulatory capital cannot be turned into cash to meet obligations, so they take 100%. A **retained interest** is the part of a securitisation that the originator keeps (for example a first-loss tranche).

Para 37(d) in numbers: a bank with A$10m of gross negative derivative values and A$4m of variation margin posted has NSFR derivative liabilities of A$6m (Att C para 10). The RSF add-on is 20% x A$10m = A$2m, because it is calculated before deducting variation margin posted (Att C para 37(d)). The A$4m of variation margin posted is not also charged as an asset (Att C para 10, footnote 12).

### 6.5.9 The pattern behind the RSF factors

| Factor | Intuition |
|---|---|
| 0% | Cash and central bank claims: available immediately at full value, so they do not need long-term funding |
| 5% | Government securities: highly liquid, but prices can move and they may have to be repo'd or sold, so a small amount of stable funding is demanded |
| 10%, 15% | Short and mostly secured or very liquid assets: 10% for short loans backed by re-usable HQLA1; 15% for HQLA2A and short unsecured lending to financial institutions |
| 50% | Assets that should turn into cash within a year but are not HQLA1 or HQLA2A: lower-grade securities, ordinary lending under a year, and anything locked up for 6 to 12 months |
| 65% | Long-term, lower-risk mortgages. Long, but they can be securitised or used as collateral, so the factor is not higher |
| 85% | Long loans and securities that are not liquid |
| 100% | Assets that will not turn into cash within a year, or at all, and assets already locked up |

These are interpretive comments on the design of the scale. The standard sets the numbers (Att C paras 29 to 37) and does not explain each one.

## 6.6 Interdependent assets and liabilities (paras 38 to 40)

Occasionally a bank is a pure conduit: it receives funding that it must immediately pass on, on matching terms, to a specific asset. APRA "may determine that certain asset and liability items, on the basis of contractual arrangements, are interdependent" where all three of the following hold: the liability cannot fall due while the asset remains on the balance sheet; the principal payments from the asset cannot be used other than to repay the liability; and the liability cannot be used to fund other assets (Att C para 38).

APRA will only make a determination "on a case-by-case basis, in exceptional circumstances", and the ADI must at minimum show that the criteria in para 40 are met in full (Att C para 39). If APRA so determines, it "may, at its discretion, adjust the RSF and ASF factors relating to those asset and liability items to zero per cent", subject to four criteria (Att C para 40):

| Criterion | Requirement |
|---|---|
| 40(a) | The individual interdependent asset and liability items are clearly identifiable |
| 40(b) | The maturity and principal amount of both the liability and its interdependent asset are the same |
| 40(c) | The ADI is acting solely as a pass-through unit to channel the funding received into the corresponding asset |
| 40(d) | The counterparties for each pair of interdependent liabilities and assets are not the same |

Evidence a bank would keep: the contract documents showing the matching terms, a mapping of each pair in its data warehouse, and APRA's written determination (APRA's discretions are exercised in writing, APS 210 para 8).

> **Watch out:** Interdependence is not an election. Without a written APRA determination, both the asset and the liability take their ordinary factors (Att C para 38).

## 6.7 Off-balance sheet exposures (paras 41 to 42)

Table 1 of Attachment C sets RSF factors for OBS credit and liquidity facilities (Att C para 41). A **credit facility** is a commitment to lend; a **liquidity facility** is a committed back-up facility used to refinance a customer's debt when it cannot roll it over (Att A para 51). An **irrevocable** facility cannot be cancelled by the bank; a **conditionally revocable** one can be cancelled only if specified conditions occur; an **unconditionally revocable** one can be cancelled at any time.

| OBS exposure | RSF factor | Reference |
|---|---|---|
| Irrevocable and conditionally revocable credit and liquidity facilities to any client | 5% | Att C para 41, Table 1 |
| Unconditionally revocable credit and liquidity facilities | 1% | Att C para 41, Table 1 |
| Trade finance-related obligations, guarantees and letters of credit unrelated to trade finance obligations | 100%, applied to actual net outflows in the most recent 12-month period | Att C para 42 |

Note on the 1% figure: Table 1 of Attachment C gives 1 per cent for unconditionally revocable facilities, against 5 per cent for irrevocable and conditionally revocable ones.

The 5% factor applies to the undrawn commitment (what the customer could still draw). Loans already drawn are on-balance sheet assets with their own factors.

For para 42, a bank does not charge 100% on the face amount of its guarantee book; it charges 100% on what actually left the bank in the last twelve months on such obligations. A **guarantee** is a promise to pay if a customer fails to pay a third party; a **letter of credit** is a bank's promise to pay a seller on behalf of a buyer when documents are presented; **trade finance** is the lending and guarantee business that supports the movement of goods.

> **Example:** A bank has A$20m of undrawn irrevocable facilities and A$30m of undrawn unconditionally revocable facilities. It also paid out A$1.5m net, over the last 12 months, on guarantees unrelated to trade finance. RSF = 20 x 5% + 30 x 1% + 1.5 x 100% = 1.0 + 0.3 + 1.5 = A$2.8m.

## 6.8 The Example Bank NSFR calculation

Example Bank is the fictional bank used throughout this guide (balance sheet in Chapter 3). All figures are A$ billions. The calculation follows Att C para 7 (ASF) and para 17 (RSF).

### 6.8.1 ASF

| Funding line | Carrying value | ASF category | Factor | Weighted ASF |
|---|---|---|---|---|
| Shareholders' equity (regulatory capital) | 8.0 | Att C para 11(a) | 100% | 8.00 |
| Wholesale debt, 1 year or more | 15.0 | Att C para 11(c) | 100% | 15.00 |
| Retail deposits, stable (at call) | 25.0 | Att C para 12(a) | 95% | 23.75 |
| Retail deposits, less stable (at call) | 15.0 | Att C para 13(a) | 90% | 13.50 |
| Retail term deposits (under 1 year) | 10.0 | Att C para 13(a) | 90% | 9.00 |
| SME deposits (qualifying, less stable) | 5.0 | Att C para 13(a) | 90% | 4.50 |
| Corporate operational deposits | 4.0 | Att C para 14(b) | 50% | 2.00 |
| Corporate non-operational deposits | 6.0 | Att C para 14(a) | 50% | 3.00 |
| Financial institution deposits (at call) | 4.0 | Att C para 15(a) | 0% | 0.00 |
| Wholesale debt maturing within 30 days | 1.0 | Att C para 15(a) | 0% | 0.00 |
| Wholesale debt, 30 days to under 6 months | 3.0 | Att C para 15(a) | 0% | 0.00 |
| Wholesale debt, 6 months to under 1 year | 2.0 | Att C para 14(f) | 50% | 1.00 |
| Other liabilities (no stated maturity) | 2.0 | Att C para 15(b) | 0% | 0.00 |
| **Total** | **100.0** | | | **79.75** |

Check of the sum: 8.00 + 15.00 = 23.00; + 23.75 = 46.75; + 13.50 = 60.25; + 9.00 = 69.25; + 4.50 = 73.75; + 2.00 = 75.75; + 3.00 = 78.75; + 1.00 = 79.75.

Assumptions behind this classification:

- The short wholesale debt lines are assumed to be funding from financial institutions or the market generally, not from non-financial corporates, sovereigns, PSEs or MDBs. Under para 14(a) and (e), funding from those holders with a residual maturity under one year would receive 50% rather than 0%. Under six months from financial institutions is 0% (Att C para 15(a)); six months to under one year is 50% through the "other funding" limb (Att C para 14(f)).
- Retail term deposits "over 30 days, under 1 year, no early withdrawal, less stable" take 90% under para 13(a), which covers term deposits with residual maturity under one year. The "no early withdrawal" feature matters for the LCR (0% run-off, Att A paras 41 to 42), not for the NSFR factor.
- Corporate non-operational deposits are assumed to have residual maturity under one year, so para 14(a) gives 50%.

### 6.8.2 RSF

| Asset or exposure | Carrying value | RSF category | Factor | Weighted RSF |
|---|---|---|---|---|
| Cash and balances with the RBA | 5.0 | Att C para 29(a), (b) | 0% | 0.00 |
| Government and semi-government securities | 12.0 | Att C para 30(a) | 5% | 0.60 |
| Other debt securities (non-HQLA, over 1 year) | 3.0 | Att C para 36(c) | 85% | 2.55 |
| Loans to other banks (under 6 months, unsecured) | 2.0 | Att C para 33(b) | 15% | 0.30 |
| Residential mortgages (standard, LVR 80% or below, over 1 year) | 50.0 | Att C para 35(a) | 65% | 32.50 |
| Business loans (over 1 year) | 15.0 | Att C para 36(b) | 85% | 12.75 |
| Personal and business loans (under 1 year) | 8.0 | Att C para 34(f) | 50% | 4.00 |
| Other assets (premises, goodwill, tax assets) | 5.0 | Att C para 37(c) | 100% | 5.00 |
| Undrawn facilities (10.0 + 5.0 + 1.0) | 16.0 | Att C para 41, Table 1 | 5% | 0.80 |
| **Total RSF** | | | | **58.50** |

Sum check: 0 + 0.60 + 2.55 + 0.30 = 3.45; + 32.50 = 35.95; + 12.75 = 48.70; + 4.00 = 52.70; + 5.00 = 57.70; + 0.80 = 58.50.

Simplifications to state clearly:

- Derivatives are ignored in the RSF for simplicity. A full calculation would add 20% of derivative liabilities (Att C para 37(d)) and any net derivative asset amount (Att C para 37(b)). The A$0.3bn of net derivative outflows in the 30-day data is an LCR input and is not used here.
- Business loans over one year take 85% (Att C para 36(b)) rather than 65% because they are not standard residential loans and are assumed to carry a risk weight above 35% under APS 112 (Att C para 35(b)).
- The A$16.0bn of undrawn facilities is treated as irrevocable or conditionally revocable (Att C para 41, Table 1).
- All assets are assumed unencumbered. Encumbrance would raise the factors (Att C para 23).

### 6.8.3 The ratio

```
NSFR = ASF / RSF = 79.75 / 58.50 = 1.3632 = 136.3%
```

Example Bank's NSFR is 136.3%, above the 100% minimum (APS 210 para 60). Its surplus of weighted ASF over RSF is 79.75 - 58.50 = A$21.25bn.

What drives the result? Mortgages contribute 32.50 of the 58.50 RSF (55.6%), because they are the biggest asset and carry 65%. On the funding side, retail deposits (stable, less stable and term) provide 23.75 + 13.50 + 9.00 = 46.25 of the 79.75 ASF (58.0%). That is why a retail-funded mortgage lender typically has a comfortable NSFR.

## 6.9 What-if exercise: lending out cash (NSFR part)

Example Bank lends A$3.0bn of its cash as new standard residential mortgages (LVR 80% or below, over one year).

- Cash and RBA balances fall by 3.0. At 0% (Att C para 29), RSF falls by 3.0 x 0% = 0.
- New mortgages rise by 3.0. At 65% (Att C para 35(a)), RSF rises by 3.0 x 65% = 1.95.
- New total RSF = 58.50 + 1.95 = 60.45.
- ASF is unchanged at 79.75, because no liability changed.
- New NSFR = 79.75 / 60.45 = 1.3193 = 131.9%.

The NSFR falls by about 4.4 percentage points (136.3% to 131.9%). The LCR part of the same exercise is in Chapter 5: HQLA falls from 17.0 to 14.0, so the LCR falls from 147.2% to 121.2%. The LCR drops further because the cash was part of the LCR's numerator, whereas in the NSFR the cash carried no weight in the first place.

> **Why it matters:** The same transaction hits the two ratios through different channels. Lending cash lowers the LCR because it shrinks the liquid asset buffer. It lowers the NSFR because it swaps a 0% asset for a 65% asset, which needs more stable funding.

A second exercise, using the NSFR alone: Example Bank replaces A$2.0bn of at-call financial institution deposits with A$2.0bn of retail term deposits (under one year, less stable). ASF on the old funding was 2.0 x 0% = 0 (Att C para 15(a)). ASF on the new funding is 2.0 x 90% = 1.80 (Att C para 13(a)). ASF becomes 79.75 + 1.80 = 81.55, RSF is unchanged at 58.50, and the NSFR is 81.55 / 58.50 = 139.4%. (The LCR effect, 178.0%, is in Chapter 5.)

## 6.10 LCR and NSFR compared

| Feature | LCR (Attachment A) | NSFR (Attachment C) |
|---|---|---|
| Time horizon | 30 calendar days (APS 210 para 55) | One year (Att C para 1) |
| Question asked | Do we hold enough HQLA to survive a 30-day severe stress? | Is our funding stable enough for the assets and commitments we have, over a year? |
| Numerator | Stock of HQLA after haircuts and caps | Available stable funding: weighted capital and liabilities (Att C para 3) |
| Denominator | Net cash outflows over 30 days (outflows less capped inflows) | Required stable funding: weighted assets and OBS exposures (Att C para 3) |
| Nature | Flow test: cash going out against cash coming in over a period | Stock test: the structure of the balance sheet at a point in time |
| Minimum | 100% on both AUD and all-currencies bases for a locally incorporated ADI; 40% all-currencies for a foreign ADI (APS 210 para 55) | 100% for locally incorporated LCR ADIs (APS 210 para 60) |
| Who is covered | All LCR ADIs | Locally incorporated LCR ADIs only (APS 210 para 59) |
| Treatment of caps | HQLA2 and HQLA2B caps apply (Att A paras 6 to 8) | Caps and LCR operational requirements ignored (Att C para 17, footnote 20) |
| Maturity convention | Contractual cash flows inside 30 days | Liabilities: earliest redemption (Att C para 8). Assets: latest possible maturity (Att C para 20) |
| What improves it | More HQLA; less short-term wholesale funding; more retail and operational funding; fewer undrawn commitments; inflows (within the 75% cap) | More long-term funding and capital; more stable retail funding; shorter, more liquid assets; fewer long loans and illiquid assets |

How they interact:

- **Same action, same direction.** Extending wholesale funding from 25 days to 18 months helps both: the LCR because the outflow leaves the 30-day window, and the NSFR because the ASF factor rises from 0% to 100%.
- **Trade-offs.** Buying government bonds funded by three-month wholesale debt raises HQLA (helps the LCR), but the bonds need 5% stable funding and the funding earns 0% ASF. The LCR rises and the NSFR falls.
- **Different weights for the same item.** An unencumbered government bond counts in full in the LCR (HQLA1, no haircut, Att A para 9) and carries 5% in the NSFR (Att C para 30). Cash counts in full in the LCR and carries 0% in the NSFR.
- **Mortgages.** An unencumbered mortgage is not HQLA, so it adds nothing to the LCR numerator, but it needs 65% stable funding in the NSFR (Att C para 35(a)). Mortgage growth tends to depress the NSFR with no direct effect on the LCR.

## 6.11 Common mistakes

1. **Using original maturity instead of residual maturity.** A five-year bond with ten months left is a ten-month liability (50% or 0% ASF depending on the holder), not a five-year one (Att C paras 8 and 11(c)).
2. **Reversing the maturity convention.** Liabilities use the earliest redemption date (Att C para 8) and assets the latest possible date (Att C para 20). Using one convention for both is wrong for any instrument with an option.
3. **Using LCR-counted HQLA.** The NSFR counts HQLA without the LCR operational requirements or caps (Att C para 17, footnote 20). The LCR's capped numerator is not the right input for RSF.
4. **Ignoring encumbrance.** Securities pledged for six months or more attract 50% or 100% (Att C para 23). A data feed without an encumbrance end date misstates RSF.
5. **Getting the derivative adjustments wrong.** Net only where an eligible bilateral netting contract meets the conditions (Att C paras 9 and 27); deduct variation margin posted from liabilities (Att C para 10); do not offset assets with margin received other than qualifying cash variation margin (Att C para 28); add 20% of gross derivative liabilities (Att C para 37(d)); and put initial margin posted at 85% (Att C para 36(a)).
6. **Double counting variation margin.** The asset for variation margin posted must not be included in RSF if it has been deducted from the replacement cost (Att C para 10, footnote 12).
7. **Treating every corporate deposit alike.** Operational deposits (Att C para 14(b)) and non-operational corporate funding under one year (Att C para 14(a)) both get 50%, but corporate funding with a residual maturity of one year or more is 100% (Att C para 11(c)).
8. **Giving every retail term deposit 90% or 95%.** Those factors apply to term deposits with residual maturity under one year. A retail term deposit with a year or more to run is 100% (Att C para 11(c)).
9. **Counting all mortgages at 65%.** Only standard residential loans to natural persons, with residual maturity of one year or more and LVR of 80% or below, qualify (Att C para 35(a)). Others fall to 85% if performing (Att C para 36(b)), or 100% if non-performing (Att C para 37(c)).
10. **Missing the off-balance sheet exposures.** Undrawn commitments attract 5% (Att C para 41); trade finance, guarantees and letters of credit attract 100% of net outflows over 12 months (Att C para 42).
11. **Mixing valuation bases.** Both ASF and RSF are based on carrying value (Att C paras 7 and 17), not market or face value.
12. **Assuming the interdependent treatment applies automatically.** It needs an APRA determination (Att C paras 38 to 40).
13. **Applying the NSFR to every ADI.** It is for locally incorporated LCR ADIs only (APS 210 para 59).

## Key points

- The NSFR tests whether a bank's funding is stable enough, over a one-year horizon, to support its assets and commitments. NSFR = ASF / RSF (Att C paras 1 to 3).
- The minimum is 100% at all times for locally incorporated LCR ADIs, with a buffer above it in line with the bank's liquidity risk tolerance (APS 210 paras 59 to 60; Att C para 4).
- ASF applies factors of 100%, 95%, 90%, 50% and 0% to the carrying values of capital and liabilities (Att C paras 7, 11 to 15). Longer, more stable and more retail-like funding scores higher.
- RSF applies factors of 0%, 5%, 10%, 15%, 50%, 65%, 85% and 100% to assets, and 5% (plus 100% of net outflows for trade finance items) to off-balance sheet exposures (Att C paras 17, 29 to 37, 41 to 42).
- Liabilities use the earliest redemption date; assets use the latest possible maturity (Att C paras 8 and 20).
- Encumbered assets move up the RSF scale: 100% if encumbered for one year or more; at least 50% for six months to under one year (Att C para 23).
- Derivatives are measured at net replacement cost; variation margin posted is deducted from liabilities, and 20% of derivative liabilities is added to RSF (Att C paras 9 to 10, 27 to 28, 37(d)).
- Example Bank has ASF of A$79.75bn, RSF of A$58.50bn and an NSFR of 136.3%.
- Lending A$3.0bn of cash as mortgages lowers Example Bank's NSFR from 136.3% to 131.9%, because a 0% asset becomes a 65% asset.
- The NSFR is a stock test over one year; the LCR is a flow test over 30 days. Some actions help both, others trade one against the other.

## Check your understanding

1. **Question:** Why does the NSFR use the earliest redemption date for liabilities but the latest possible date for assets?
   **Answer:** Both choices are conservative. Assuming funding can leave as early as possible gives less credit for stable funding, and assuming assets are repaid as late as possible requires more stable funding for them (Att C paras 8 and 20).

2. **Question:** A bank has A$40m of stable retail deposits, A$10m of less stable retail deposits and A$20m of operational deposits, all at call. Its A$30m of equity counts as regulatory capital. What is the ASF?
   **Answer:** Stable retail 40 x 95% = 38.0 (Att C para 12(a)); less stable 10 x 90% = 9.0 (para 13(a)); operational 20 x 50% = 10.0 (para 14(b)); equity 30 x 100% = 30.0 (para 11(a)). ASF = 38.0 + 9.0 + 10.0 + 30.0 = A$87.0m.

3. **Question:** A bank holds A$200m of unencumbered government securities. It then repos all of them for 9 months. What is the RSF before and after?
   **Answer:** Before: 200 x 5% = A$10m (Att C para 30). After: encumbered for six months to under one year, with an unencumbered factor of 5% (50% or lower), so the factor is 50% (Att C paras 23 and 34(b)); RSF = 200 x 50% = A$100m.

4. **Question:** Why does a bond with 14 months to maturity stop earning a 100% ASF factor after three months?
   **Answer:** Its residual maturity has fallen below one year, so it moves out of para 11(c) into the 50% or 0% categories depending on who holds it (Att C paras 11(c), 14 and 15).

5. **Question:** In Example Bank, A$1.0bn of the wholesale debt of 1 year or more falls to 11 months to maturity, and is held by financial institutions. What is the new NSFR?
   **Answer:** ASF falls by 1.0 x 100% = 1.00 and rises by 1.0 x 50% = 0.50 (para 14(f)), so ASF = 79.75 - 1.00 + 0.50 = 79.25. NSFR = 79.25 / 58.50 = 135.5%.

6. **Question:** Why can a bank's LCR rise while its NSFR falls?
   **Answer:** Buying government bonds with short-term wholesale funding raises HQLA (the LCR numerator), but the funding earns 0% ASF and the bonds need 5% RSF, so the NSFR falls. The ratios measure different horizons and use different weights.

7. **Question:** In Example Bank, A$5.0bn of the A$50.0bn mortgage book turns out to have an LVR above 80%. What happens to the NSFR?
   **Answer:** Those mortgages move from 65% (para 35(a)) to 85% (para 36(b), assuming they are performing). RSF rises by 5.0 x (85% - 65%) = A$1.0bn to 59.50, and NSFR = 79.75 / 59.50 = 134.0%.

8. **Question:** Why does a bank get credit for the full balance-sheet amount of its capital under para 11(a), even though some items are deducted from regulatory capital for capital adequacy?
   **Answer:** Para 11(a) takes regulatory capital "before the application of regulatory adjustments", and footnote 9 defines carrying value as the amount before regulatory deductions, filters or other adjustments. The deducted items themselves are charged 100% on the asset side (Att C para 37(c)), so the effect is neutral for them.

## NSFR quick reference

### ASF factors

| Factor | Liability or capital | Reference |
|---|---|---|
| 100% | Regulatory capital before adjustments (excluding Tier 2 under one year) | Att C para 11(a) |
| 100% | Other capital instruments with effective residual maturity of one year or more (excluding those with options reducing maturity below one year) | Att C para 11(b) |
| 100% | Secured and unsecured borrowings and liabilities, including term deposits, with effective residual maturity of one year or more (not cash flows due within one year) | Att C para 11(c) |
| 95% | Stable retail and SME demand and term deposits (residual maturity under one year) | Att C para 12(a) |
| 95% | Intermediated deposits meeting Att A para 35 as stable, with at least 12 months' notice to replace the ADI | Att C para 12(b) |
| 90% | Less stable retail and SME demand and term deposits (residual maturity under one year) | Att C para 13(a) |
| 90% | Intermediated deposits (including member-directed superannuation) meeting Att A para 35 as less stable, with at least 12 months' notice | Att C para 13(b) |
| 50% | Funding under one year from non-financial corporates | Att C para 14(a) |
| 50% | Operational deposits | Att C para 14(b) |
| 50% | Superannuation fund deposits that meet the definition of operational deposits | Att C para 14(c) |
| 50% | Intermediated deposits meeting Att A para 35 with at least six months' notice | Att C para 14(d) |
| 50% | Funding under one year from sovereigns, PSEs, MDBs and national development banks | Att C para 14(e) |
| 50% | Other funding with residual maturity from six months to under one year, including from central banks and financial institutions | Att C para 14(f) |
| 0% | All other liabilities and equity, including funding under six months from central banks and financial institutions | Att C para 15(a) |
| 0% | Liabilities without a stated maturity, short positions and open maturity positions (deferred tax liabilities and minority interests are treated by term: 100% if one year or more, 50% if six months to under one year) | Att C para 15(b) |
| 0% | Excess of NSFR derivative liabilities over NSFR derivative assets | Att C para 15(c) |
| 0% | Trade date payables expected to settle in the standard cycle, or failed but still expected to settle | Att C para 15(d) |
| 0% | Variation margin received not meeting the offset conditions, and initial margin received | Att C para 28 |
| 0% (APRA discretion) | Interdependent liabilities (and matching assets) | Att C paras 38 to 40 |

### RSF factors

| Factor | Asset or exposure | Reference |
|---|---|---|
| 0% | Notes and coins immediately available | Att C para 29(a) |
| 0% | Central bank reserves and balances | Att C para 29(b) |
| 0% | Claims on central banks with residual maturity under six months | Att C para 29(c) |
| 0% | Trade date receivables expected to settle in the standard cycle, or failed but still expected to settle | Att C para 29(d) |
| 5% | Unencumbered marketable securities that are 0% risk-weighted claims on sovereigns, central banks, PSEs, BIS, IMF, ECB, EU or MDBs | Att C para 30(a) |
| 5% | Certain non-zero risk-weighted sovereign or central bank debt securities (Att A para 9(d), (e)) | Att C para 30(b) |
| 5% | Undrawn irrevocable and conditionally revocable credit and liquidity facilities | Att C para 41, Table 1 |
| 1% | Undrawn unconditionally revocable credit and liquidity facilities | Att C para 41, Table 1 |
| 10% | Unencumbered loans to financial institutions under six months secured by HQLA1, with free rehypothecation | Att C para 31 |
| 10% (may) | CLF-eligible third-party debt securities, other jurisdictions' ALA, host-supervisor eligible assets (limited to the CLF amount allowed in the LCR) | Att C para 32(a) |
| 10% (may) | Self-securitised assets eligible as CLF collateral (limited) | Att C para 32(b) |
| 15% | Unencumbered HQLA2A | Att C para 33(a) |
| 15% | Other unencumbered loans to financial institutions under six months | Att C para 33(b) |
| 50% | Unencumbered HQLA2B | Att C para 34(a) |
| 50% | HQLA encumbered for six months to under one year | Att C para 34(b) |
| 50% | Loans to financial institutions and central banks, six months to under one year | Att C para 34(c) |
| 50% | Operational deposits held at other ADIs (50% ASF under para 14(b)) | Att C para 34(d) |
| 50% | ASX200 Australian equities, other than financial institutions and associated entities | Att C para 34(e) |
| 50% | Other non-HQLA under one year, including loans to non-financial corporates, retail, SME, sovereigns and PSEs | Att C para 34(f) |
| 65% | Unencumbered standard residential loans to natural persons, one year or more, LVR 80% or below | Att C para 35(a) |
| 65% | Other unencumbered loans (not to financial institutions), one year or more, with a risk weight of 35% or lower | Att C para 35(b) |
| 85% | Initial margin posted and CCP default fund contributions (higher factor if securities would otherwise get it) | Att C para 36(a) |
| 85% | Other unencumbered performing loans, one year or more, not in para 35 (excluding loans to financial institutions) | Att C para 36(b) |
| 85% | Unencumbered securities of one year or more remaining maturity and exchange-traded equities, not in default and not HQLA | Att C para 36(c) |
| 85% | Physical traded commodities, including gold | Att C para 36(d) |
| 100% | Assets encumbered for one year or more | Att C para 37(a) |
| 100% | Net derivative assets (if more than derivative liabilities) | Att C para 37(b) |
| 100% | All other assets: non-performing loans, loans to financial institutions of one year or more, non-exchange-traded equities, fixed assets, items deducted from regulatory capital, retained interest, insurance assets, subsidiary interests, defaulted securities | Att C para 37(c) |
| 100% | 20% of gross derivative liabilities (before deducting variation margin posted) | Att C para 37(d) |
| 100% | Trade finance obligations, guarantees and letters of credit unrelated to trade finance (applied to actual net outflows in the last 12 months) | Att C para 42 |
| 50% / 100% / as unencumbered | Encumbered assets, by remaining encumbrance period | Att C para 23 |
| 0% (APRA discretion) | Interdependent assets (and matching liabilities) | Att C paras 38 to 40 |

---

# Chapter 7: The Minimum Liquidity Holdings regime

## 7.1 What the MLH regime is and why it exists

Chapters 5 and 6 describe the two ratio tests for larger or more complex banks. This chapter describes the simpler regime for the rest. The **minimum liquidity holdings (MLH)** requirement says that an ADI must hold a fixed proportion of its liabilities in a list of specified, easily sold liquid assets. An **ADI** is an authorised deposit-taking institution: a bank, building society or credit union licensed under the Banking Act 1959. A **liability** is an amount the bank owes, such as customer deposits or bonds it has issued.

The idea is the same as the LCR in spirit (hold enough easily sold assets to meet obligations in a squeeze) but the mechanics are far simpler. There is no 30-day stress scenario, no run-off rate for each type of deposit, no inflow cap, and no required-funding calculation. There is one test: liquid assets divided by liabilities must be at least 9%.

The key principles in APS 210 apply to every ADI whatever its classification. An ADI "must at all times maintain sufficient liquidity to meet its obligations as they fall due and hold a minimum level of liquid assets to survive a severe liquidity stress" (APS 210 para 12). The MLH requirement is the quantitative floor for the ADIs that are classified as MLH ADIs. Chapter 8 covers the governance requirements that apply to them as well.

> **Why it matters for a data professional:** The MLH calculation is a sum over a short list of asset types divided by a sum over liabilities. The difficulty is not the arithmetic; it is deciding which assets are eligible (unencumbered, repo-eligible with the RBA, not subordinated, convertible within two business days) and valuing them at market value on the reporting date.

## 7.2 Who is an MLH ADI, and who decides

APS 210 classifies ADIs into two groups.

| Question | Rule | Reference |
|---|---|---|
| Who classifies a locally incorporated ADI? | APRA determines whether it is a Liquidity Coverage Ratio ADI (LCR ADI) or a Minimum Liquidity Holdings ADI (MLH ADI) | APS 210 para 52 |
| What is the default for a foreign ADI? | A foreign ADI is an LCR ADI, unless APRA determines that it is an MLH ADI | APS 210 para 53 |
| What does APRA consider for a foreign ADI? | The ADI's "size and complexity with respect to liquidity risk" | APS 210 para 53 |
| When must the requirements be met? | "On a continuous basis, absent a situation of financial stress" | APS 210 para 54 |
| What does an MLH ADI have to hold? | "A minimum holding of nine per cent of its liabilities in specified liquid assets, in accordance with Attachment B" | APS 210 para 57 |
| Can APRA require more? | Yes: a higher minimum if APRA has concerns about the ADI's liquidity risk profile or the quality of its liquidity risk management | APS 210 para 58 |

A **foreign ADI** is a branch in Australia of a bank incorporated overseas. A **locally incorporated** ADI is a company incorporated in Australia. The standard does not set out numerical tests (such as a size threshold) for which locally incorporated ADIs are MLH ADIs. It simply says that "APRA will determine" the classification (APS 210 para 52), and APRA exercises that power in writing (APS 210 para 8). As generally understood, MLH classification is used for smaller ADIs with simpler balance sheets; the standard itself does not say so, and APRA's guidance (APG 210) is where a reader would look for the factors APRA considers.

Several consequences follow from classification:

- An MLH ADI is **not** subject to the LCR (APS 210 para 55 applies to an LCR ADI).
- An MLH ADI is **not** subject to the NSFR, which applies only to a locally incorporated ADI classified as an LCR ADI (APS 210 para 59).
- The stress-testing requirement in para 62 is expressed to apply to an LCR ADI, so on its wording it does not apply to an MLH ADI (APS 210 para 62). The general requirement for a robust framework, a liquidity risk tolerance, a funding strategy and a contingency funding plan (APS 210 paras 11 to 51) applies to all ADIs; see Chapter 8.
- The securitisation carve-out allows an originating ADI that meets the operational requirements for capital relief under APS 120 to exclude the assets and liabilities of the relevant special purpose vehicles from its MLH calculation (APS 210 para 5).
- The 9% is a floor. In addition, APRA "may require an MLH ADI to maintain higher minimum liquidity holdings" (APS 210 para 58).
- The notification duty in the key principles applies: an ADI must inform APRA "as soon as possible of any concerns it has about its current or future liquidity position" (APS 210 para 14).

> **In the standard:** The classification is made by APRA and not chosen by the ADI. A bank's liquidity team should hold APRA's written classification (see APS 210 para 8) and re-check it whenever APRA's letter is updated.

## 7.3 The formula

```
                    Eligible liquid assets (market value, unencumbered)
MLH ratio  =  ------------------------------------------------------------   (must be at least 9%)
               Liabilities (on-balance sheet) + irrevocable commitments
```

The numerator is defined in Att B para 2 and the denominator in Att B para 1. The 9% comes from APS 210 para 57.

Note that this is a ratio of assets to liabilities, not to total assets. The size of the equity cushion does not enter into the denominator.

## 7.4 The denominator: liabilities (Att B para 1)

"For the purpose of this Attachment, liabilities are defined as total on-balance sheet liabilities and irrevocable commitments, except where approved for a prudential purpose by APRA" (Att B para 1).

| Component | What it means | Notes |
|---|---|---|
| Total on-balance sheet liabilities | Everything the ADI owes that appears on its balance sheet: deposits, borrowings, debt it has issued, derivative liabilities, provisions and other liabilities | Equity is not a liability, so it is not in the denominator. The paragraph says "total", so it does not distinguish short from long, retail from wholesale |
| Irrevocable commitments | Undrawn commitments the ADI cannot cancel, such as a committed (irrevocable) credit facility it has promised to provide | They are not on the balance sheet, but they could become cash outflows if a customer draws. Revocable commitments are not mentioned in para 1 |
| Exception | APRA may approve a different treatment "for a prudential purpose" | The approval is exercised in writing (APS 210 para 8) |

An **irrevocable commitment** is a promise to lend or provide funds that the bank cannot cancel at will. Compare **revocable** commitments, which the bank can cancel (conditions vary; see Chapter 4). Att B para 1 includes only irrevocable commitments.

> **Watch out:** The wording is "total on-balance sheet liabilities", not "deposits". A data model that uses only customer deposits as the denominator understates liabilities and overstates the ratio. Conversely, including equity or revocable commitments would overstate the denominator.

## 7.5 The numerator: eligible liquid assets (Att B paras 2 to 4)

### 7.5.1 General conditions

Att B para 2 sets two general conditions:

1. Liquid assets "are included at market value". **Market value** is the price the asset could be sold for in the market on the valuation date, as opposed to its face value (the amount printed on a bond, repaid at maturity) or its carrying value (the accounting amount, which may be cost-based). If a government bond with a face value of A$100m trades at A$97m, A$97m counts.
2. The assets "must be free from encumbrances except where approved for a prudential purpose by APRA". An asset is **encumbered** when it has been pledged, lent or otherwise committed so that the bank cannot freely sell it (for example, lodged as collateral in a repurchase agreement).

### 7.5.2 The list of eligible assets

Att B para 2 lists the eligible assets:

| Limb | Eligible liquid asset | Plain-English explanation |
|---|---|---|
| (a) | Notes and coin and settlement funds | Physical cash, and balances held for settling payments (as generally understood, balances in the bank's Exchange Settlement Account at the Reserve Bank of Australia (RBA), through which interbank payments settle) |
| (b) | Commonwealth Government and semi-government securities | Bonds and bills issued by the Australian Government and by state and territory governments (or their borrowing agencies) |
| (c) | Debt securities guaranteed by the Australian Government, or foreign sovereign governments | Debt that is issued by someone else but backed by a government guarantee |
| (d) | Debt securities issued by supranationals and foreign governments | Bonds issued by international bodies (for example development banks) and by overseas governments |
| (e) | Bank bills, certificates of deposit (CDs) and debt securities issued by ADIs | Short-term bank paper: a **bank bill** is a short-term IOU accepted by a bank; a **certificate of deposit** is a tradeable receipt for a term deposit; plus other debt securities that ADIs have issued |
| (f) | Deposits (at call and any other deposits readily convertible into cash within two business days) held with other ADIs, net of placements by other ADIs | Money the ADI has placed with other banks that it can get back quickly, reduced by the amount other ADIs have placed with it |
| (g) | Any other securities approved by APRA | A catch-all, exercised in writing by APRA |

Points to notice:

- **Limb (e) includes paper issued by ADIs.** Under the LCR, securities issued by financial institutions are excluded from HQLA (Att A para 9(c)(iv)), which is a major difference between the two regimes; see 7.9.
- **Limb (f) is net.** If an MLH ADI has A$50m placed with other ADIs at call, and other ADIs have A$20m placed with it, only A$30m counts. If the other ADIs' placements exceed its own, the net amount is negative, and the standard does not say how to treat a negative figure. The text says "net of placements by other ADIs" and a reader should read APG 210 or ask APRA rather than assume it floors at zero.
- **Limb (b) includes semi-government securities**, as the LCR also does for Australian dollar HQLA1 (as generally understood). The MLH list also includes foreign government debt (limbs (c) and (d)) without the risk-weight and market-depth tests applied for HQLA1 in the LCR (Att A para 9(c)).

### 7.5.3 Repo eligibility and subordination (Att B para 3)

"All debt securities must be eligible for repurchase agreement with the RBA and must not be subordinated" (Att B para 3).

- A **repurchase agreement (repo)** with the RBA is a transaction where a bank sells securities to the RBA and agrees to buy them back, in effect borrowing against them. A security is "eligible for repo with the RBA" if the RBA accepts it as collateral in its market operations. This requirement ties the MLH list to the RBA's own list of eligible securities, which the RBA publishes and may change. (Chapter 2 describes the RBA's role.) The idea is that a bank can always raise cash against these securities from the central bank if the market will not buy them.
- **Subordinated** debt ranks behind other creditors if the issuer fails, so it is riskier and harder to sell. It is excluded, whatever its issuer. This matters especially for limb (e): a subordinated bond issued by an ADI does not count even though it is "debt securities issued by ADIs".
- The paragraph says "all debt securities", so it applies to limbs (b) to (e) and any debt securities approved under limb (g). It does not apply to notes and coin, settlement funds or deposits, which are not debt securities.

### 7.5.4 Two-day liquidation (Att B para 4)

"An MLH ADI must ensure it has the operational capacity to liquidate any securities held as liquid assets within two business days" (Att B para 4).

**Operational capacity** means the practical ability to turn the securities into cash: the legal right to sell, the custody and settlement arrangements, the people and systems to execute trades, and, if the plan is to repo to the RBA, the documentation and access to do so. A **business day** is a day on which the relevant markets and payment systems are open. The limb (f) deposits already carry a two-business-day test in their wording ("readily convertible into cash within two business days"), and para 4 extends the same time frame to the securities.

Evidence a bank would keep: a periodic test of selling or repo'ing a sample of each security type; custody and settlement agreements; delegations showing who can trade; and records of the RBA repo eligibility of each holding.

## 7.6 The trigger ratio (Att B para 5)

"In order to ensure that the MLH requirement is not breached, absent a situation of financial stress, an ADI must set a trigger ratio above its MLH requirement and must ensure that it manages its liquidity in accordance with its trigger ratio" (Att B para 5).

A **trigger ratio** is an internal early-warning level set above the regulatory minimum. When the ADI's actual ratio falls to the trigger, management must act (for instance by raising funding or buying more liquid assets) before the 9% minimum is reached. The standard does not set the number. The ADI chooses it, and must "manage its liquidity in accordance with" it, so in practice it becomes a limit with escalation procedures (compare the requirement for limits and escalation in APS 210 para 37, Chapter 8).

> **Example:** An ADI sets a trigger of 11%. Its MLH ratio drifts down to 10.8%, which is above the 9% minimum but below its trigger. The Board's liquidity policy requires management to report the breach of the trigger and put a plan in place. The 9% requirement has not been breached, but the ADI has used up its early warning.

The phrase "absent a situation of financial stress" is important. The buffer is for normal conditions; in a real stress the ADI may use it. For the LCR, the standard says explicitly that an ADI may use its HQLA in stress (Att A para 5, Chapter 5); for the MLH, para 5 of Att B and para 54 of the main body use the same "absent a situation of financial stress" language, and APS 210 para 14 requires immediate notification to APRA of a severe stress.

## 7.7 Notification (Att B para 6)

"An ADI must inform APRA immediately when it becomes aware that its liquid assets may fall below its MLH requirement and advise APRA of the remedial action taken or planned to restore its liquidity position above its MLH requirement" (Att B para 6).

Three things stand out:

1. **The trigger is a possibility, not an actual breach.** The duty arises when the ADI "becomes aware that its liquid assets *may* fall below" the requirement. A forecast shortfall is enough.
2. **The duty is immediate.** There is no grace period.
3. **The report must include the fix.** The ADI must say what remedial action has been taken or is planned.

This sits on top of the general duty to tell APRA "as soon as possible" of any concerns about the current or future liquidity position (APS 210 para 14).

> **Watch out for dashboards:** If you build an MLH monitor, the useful alert is not "ratio < 9%". It is a projected path that crosses the trigger ratio (Att B para 5) and, separately, one that might cross 9% (Att B para 6). The first starts internal escalation; the second starts a call to APRA.

## 7.8 Worked example: a small mutual (what-if exercise 5)

This is not Example Bank. It is a small hypothetical mutual ADI with simple figures, to show the arithmetic.

| Item | A$m |
|---|---|
| On-balance sheet liabilities plus irrevocable commitments (Att B para 1) | 1,000 |
| Minimum MLH assets = 9% x 1,000 (APS 210 para 57) | 90 |
| Eligible liquid assets held (market value, unencumbered) | 130 |

```
MLH ratio = 130 / 1,000 = 13.0%
Surplus over the minimum = 130 - 90 = A$40m (4.0 percentage points)
```

The ADI sets its own trigger ratio above 9% (Att B para 5). For illustration only, suppose it chooses 11%, which is A$110m. (The 11% is an invented number to show the mechanism; the standard does not specify one.) The headroom between the holding and the trigger is 130 - 110 = A$20m.

Now consider a stress: liabilities grow to A$1,100m as customers deposit more, while the eligible holding stays at A$130m.

```
MLH ratio = 130 / 1,100 = 11.8%
Trigger of 11% = A$121m; minimum of 9% = A$99m
```

Still above the trigger, so no action. Suppose instead that A$25m of the holding turns out to be a bond that is not eligible for repo with the RBA, and the ADI had wrongly included it. The correct eligible holding is 130 - 25 = A$105m.

```
MLH ratio = 105 / 1,000 = 10.5%  (below the 11% trigger, above the 9% minimum)
```

The ADI has breached its trigger and must act (Att B para 5). It is still above 9%, so no breach of the minimum, but if it is aware that the holding may fall below A$90m it must tell APRA immediately (Att B para 6).

## 7.9 How MLH differs from the LCR

| Feature | MLH (Att B) | LCR (Att A) |
|---|---|---|
| Who | MLH ADIs (APS 210 paras 52 to 54, 57) | LCR ADIs (APS 210 paras 52 to 56) |
| Test | Liquid assets / liabilities, at least 9% (APS 210 para 57) | HQLA / net cash outflows over 30 days, at least 100% (locally incorporated) (APS 210 para 55) |
| Stress scenario | None built in | 30-day severe stress with run-off and inflow rates (Att A) |
| Denominator | Total liabilities plus irrevocable commitments (Att B para 1) | Stressed net outflows (Att A para 30) |
| Asset valuation | Market value (Att B para 2) | Market value less haircuts for HQLA2 (Att A paras 9, 10, 12) |
| Asset list | Short list: cash, government and semi-government, guaranteed paper, supranational and foreign government paper, bank bills, CDs and ADI debt, interbank deposits (Att B para 2) | HQLA1, HQLA2A, HQLA2B with detailed criteria and caps (Att A paras 6 to 12) |
| Paper issued by financial institutions | Eligible if issued by an ADI (Att B para 2(e)) | Excluded from HQLA1 and HQLA2A government-type and corporate categories (Att A paras 9 and 10) |
| Funding stability test | None (NSFR does not apply, APS 210 para 59) | Separate NSFR for locally incorporated LCR ADIs (APS 210 para 59) |
| Operational test | Liquidate in two business days (Att B para 4) | Operational requirements (Att A paras 22 to 25) |
| Early warning | Trigger ratio above 9%, set by the ADI (Att B para 5) | Buffer above 100% in line with liquidity risk tolerance (Att A para 5; Att C para 4 for NSFR) |
| Notification | Immediately if liquid assets may fall below MLH (Att B para 6) | Notification if the ADI uses its buffer in stress (Att A para 5) |
| Minimum higher by APRA? | Yes, para 58 | Yes, para 56 (LCR) and para 61 (NSFR) |

How to think about the difference: the LCR is a model of what could happen to the bank over 30 days, with a different weight for each liability. MLH is a rule of thumb that assumes a fixed 9% of all obligations might need to be met from quickly saleable assets, whatever mix of deposits and loans the bank has. It is easier to compute, and less sensitive to the composition of funding. A bank with highly volatile wholesale funding and a bank with sticky household deposits have the same 9% requirement if their liabilities are equal.

## 7.10 What changed in the July 2025 version

The July 2025 version of APS 210 commenced on 1 July 2025 (APS 210 para 6). APRA's published information about the reform that led to it (see Appendix B) indicates that the main change for MLH ADIs was a requirement to value their liquid assets at market value and keep those values up to date. In the text of Attachment B, para 2 says liquid assets "are included at market value". APRA's practice guide APG 210 is reported to expect MLH ADIs to revalue liquid assets at least quarterly and to be able to revalue more often. Confirm the exact words and the date of the guide on apra.gov.au before relying on them. APRA also deferred a proposal to phase out bank debt securities as MLH liquid assets, and in the meantime expects MLH ADIs to diversify their liquid asset portfolios. A line-by-line comparison of Attachment B in the previous version with the July 2025 version has not been made here.

## Key points

- An MLH ADI must hold at least 9% of its liabilities in specified liquid assets (APS 210 para 57); APRA may require more (APS 210 para 58).
- APRA decides whether a locally incorporated ADI is an LCR ADI or an MLH ADI; a foreign ADI is an LCR ADI unless APRA determines otherwise (APS 210 paras 52 to 53).
- Liabilities mean total on-balance sheet liabilities plus irrevocable commitments (Att B para 1).
- Eligible assets are valued at market value and must be unencumbered unless APRA approves otherwise (Att B para 2).
- The eligible list covers cash and settlement funds, Australian Government and semi-government securities, guaranteed and supranational/foreign government debt, bank bills, CDs and ADI-issued debt, and interbank deposits (net) readily convertible within two business days (Att B para 2(a) to (g)).
- Debt securities must be repo-eligible with the RBA and not subordinated (Att B para 3).
- The ADI must be able to liquidate its securities within two business days (Att B para 4).
- The ADI must set a trigger ratio above 9% and manage to it (Att B para 5), and tell APRA immediately if liquid assets may fall below the requirement (Att B para 6).
- MLH ADIs are not subject to the LCR or the NSFR (APS 210 paras 55, 59).

## Check your understanding

1. **Question:** A small ADI has liabilities of A$800m, irrevocable commitments of A$60m, and equity of A$90m. What is its minimum MLH holding?
   **Answer:** Liabilities for MLH are on-balance sheet liabilities plus irrevocable commitments = 800 + 60 = A$860m (Att B para 1). Equity is not counted. Minimum = 9% x 860 = A$77.4m (APS 210 para 57).

2. **Question:** The same ADI holds A$50m of government securities at market value (A$5m of which are pledged to secure a repo), A$20m of cash, and A$10m of its own subordinated debt held as an investment in a related ADI's issue (a debt security issued by an ADI, but subordinated). What is its eligible holding and ratio?
   **Answer:** Encumbered securities are excluded unless APRA approves (Att B para 2): 50 - 5 = A$45m. Cash A$20m is eligible (para 2(a)). The subordinated debt is excluded (Att B para 3). Eligible = 45 + 20 = A$65m. Ratio = 65 / 860 = 7.6%, which is below the 9% minimum of A$77.4m. Shortfall = 77.4 - 65 = A$12.4m, and the ADI must tell APRA immediately about the actual or likely shortfall and its remedial action (Att B para 6).

3. **Question:** Why does para 5 of Attachment B require a trigger ratio when there is already a 9% minimum?
   **Answer:** So that the ADI acts before it breaches the minimum in normal conditions. The trigger ratio sits above the minimum and the ADI must manage its liquidity to it (Att B para 5).

4. **Question:** Does an interbank deposit that can be withdrawn on five business days' notice count as an MLH liquid asset?
   **Answer:** No. Limb (f) covers deposits at call or otherwise readily convertible into cash within two business days (Att B para 2(f)).

5. **Question:** A bank bill issued by an ADI is eligible under limb (e), but a bond issued by the same ADI is not eligible under the LCR as HQLA1. Why is the MLH treatment broader?
   **Answer:** The MLH list expressly includes bank bills, CDs and debt securities issued by ADIs, provided they are repo-eligible with the RBA and not subordinated (Att B paras 2(e), 3). The LCR HQLA1 and HQLA2A government-type categories exclude obligations of financial institutions (Att A paras 9(c)(iv), 10(a)(iv)). The two regimes use different lists for different purposes.

6. **Question:** An ADI forecasts that, after a large loan settlement next week, its eligible liquid assets will be A$85m against a minimum of A$90m. Must it tell APRA now or wait until it happens?
   **Answer:** Now. Att B para 6 requires immediate notice when the ADI "becomes aware that its liquid assets may fall below" the requirement, with the remedial action taken or planned.

7. **Question:** Using the A$1,000m mutual in 7.8, how far can eligible assets fall before the 9% minimum is breached, if liabilities stay unchanged?
   **Answer:** Minimum is A$90m. The holding of A$130m can fall by A$40m (to A$90m) before the minimum is breached; it would reach an 11% trigger (A$110m) after a fall of A$20m.

## MLH quick reference

| Item | Rule | Reference |
|---|---|---|
| Minimum | 9% of liabilities in specified liquid assets | APS 210 para 57 |
| Higher minimum | APRA may require | APS 210 para 58 |
| Classification | APRA determines (locally incorporated); foreign ADI is an LCR ADI unless APRA determines otherwise | APS 210 paras 52 to 53 |
| Continuous compliance | Absent financial stress | APS 210 para 54 |
| Liabilities | On-balance sheet liabilities plus irrevocable commitments | Att B para 1 |
| Valuation, encumbrance | Market value; unencumbered unless APRA approves | Att B para 2 |
| Eligible assets | Notes, coin, settlement funds; Commonwealth and semi-government securities; guaranteed debt; supranational and foreign government debt; bank bills, CDs and ADI debt; at-call or two-day deposits with ADIs net of placements by ADIs; other APRA-approved securities | Att B para 2(a) to (g) |
| Debt security conditions | RBA repo-eligible; not subordinated | Att B para 3 |
| Operational | Liquidate within two business days | Att B para 4 |
| Trigger | Set above MLH requirement and manage to it | Att B para 5 |
| Notification | Immediately when liquid assets may fall below; give remedial action | Att B para 6 |

---

# Chapter 8: The rest of APS 210: governance and risk management

## 8.1 Why this part of the standard matters

Chapters 5, 6 and 7 cover the numbers: the Liquidity Coverage Ratio (LCR), the Net Stable Funding Ratio (NSFR) and the Minimum Liquidity Holdings (MLH) requirement. This chapter covers the part of Prudential Standard APS 210 Liquidity that is written in words rather than percentages: who is responsible, what policies must exist, what must be reviewed and how often, and what must be told to the regulator. APS 210 is the prudential standard that the Australian Prudential Regulation Authority (APRA) made under section 11AF of the Banking Act 1959 (APS 210 para 1). A **prudential standard** is a legally binding rule for regulated institutions. An **authorised deposit-taking institution (ADI)** is a bank, building society or credit union licensed to take deposits.

A bank can pass every ratio on the reporting date and still fail an APRA review if it cannot show that it manages liquidity well. Paras 56 and 58 say so directly: APRA may require higher minimums "if APRA has concerns about the ADI's liquidity risk profile or the quality of its liquidity risk management" (APS 210 paras 56 and 58; also para 61 for the NSFR). The quality of governance is therefore a driver of the numbers, not a separate topic.

For each group of paragraphs this chapter gives three things: what the rule says, what it typically looks like inside a real bank (as generally understood, not as prescribed by the standard), and what evidence a bank would keep so that it can show APRA that it complies. The standard does not prescribe the "evidence" or the "in practice" parts; those are reasoned from the wording of the rule and are labelled as such.

> **Why it matters for a data professional:** A liquidity dashboard is a piece of the framework in this chapter. Para 40 requires "a reliable management information system that provides the Board, senior management and other appropriate personnel with timely and forward-looking information" (APS 210 para 40). The data lineage, controls and report schedules you build are evidence of compliance.

## 8.2 Application and interpretation (paras 1 to 10)

The opening paragraphs say who the standard covers and how to read it. They are short but they matter for how the later paragraphs apply.

| Para | What it says | What it means |
|---|---|---|
| 1 | Made under section 11AF of the Banking Act 1959 | Source of legal force (APS 210 para 1) |
| 2 | Applies to all ADIs | Banks, credit unions and building societies alike (APS 210 para 2) |
| 3 | A reference to an ADI is to an ADI on a **Level 1** basis (the ADI alone) and to a group of which it is a member on a **Level 2** basis (the consolidated group) | The rules apply twice: to the legal entity and to the group (APS 210 para 3) |
| 4 | If the ADI is the holding company of a group, it must ensure Level 2 requirements are met; if it is a subsidiary of an authorised non-operating holding company (authorised NOHC), the NOHC must ensure they are met | Responsibility for Level 2 sits with the top entity (APS 210 para 4) |
| 5 | An originating ADI in a securitisation that meets the operational requirements for capital relief under APS 120 may exclude the special purpose vehicles' assets and liabilities from MLH and NSFR; for the LCR it must include the SPVs' cash flows | Securitisation carve-out (APS 210 para 5) |
| 6 | Commences on 1 July 2025 | (APS 210 para 6) |
| 7 | Terms defined in CPS 001 Defined terms appear in bold on first use | (APS 210 para 7) |
| 8 | Where APRA exercises a power or discretion, it does so in writing | Applies to every "APRA may" in the standard (APS 210 para 8) |
| 9 | References to Acts, regulations and prudential standards mean those instruments as in force from time to time | (APS 210 para 9) |
| 10 | Definitions: an **associated entity** has the meaning in section 50AAA of the Corporations Act 2001; a **financial institution** includes a money market corporation, finance company, friendly society and the trustee of a superannuation or pension fund, public unit trust or mutual fund, or cash management trust | (APS 210 para 10) |

Practical consequences:

- **Level 1 and Level 2.** The liquidity framework in this chapter must "clearly set out the organisational structure as it relates to liquidity for the ADI on both a Level 1 and Level 2 basis" (APS 210 para 25) and stress tests must analyse both (APS 210 para 64). A dashboard that shows only the group total fails the Level 1 requirement and vice versa.
- **APRA acts in writing.** Every exemption, approval, higher requirement or adjustment (APS 210 paras 56, 58, 61, 69, 71) should be on file as a written communication (APS 210 para 8).
- **The word "financial institution"** has a defined breadth (APS 210 para 10(b)). The trustee of a superannuation fund is included, which matters for the classification of deposits in Chapters 5 and 6.

## 8.3 Key principles (paras 11 to 14)

The key principles are four short duties that frame everything else.

| Para | Principle | In plain words |
|---|---|---|
| 11 | "An ADI is responsible for the sound management of its liquidity risk and must have a robust framework to manage its liquidity risk accordingly." | The bank owns the problem; it cannot outsource it to the regulator. A framework (policies, limits, reporting, roles) must exist |
| 12 | "An ADI must at all times maintain sufficient liquidity to meet its obligations as they fall due and hold a minimum level of liquid assets to survive a severe liquidity stress." | Two tests: ability to pay obligations on the day they fall due, and a stock of liquid assets for a severe stress. The first is a general duty, the second is quantified by the LCR or MLH |
| 13 | "An ADI must ensure that its activities are funded with stable sources of funding on an ongoing basis." | The basis of the NSFR (Chapter 6) |
| 14 | An ADI "must inform APRA as soon as possible of any concerns it has about its current or future liquidity position, and its plans to address those concerns. In particular, if an ADI experiences a severe liquidity stress, it must notify APRA immediately and advise the action that is being taken." | Two speeds of notice: "as soon as possible" for concerns, "immediately" for a severe stress |

(APS 210 paras 11 to 14.)

**In a real bank.** Para 14 is a duty that depends on judgement ("any concerns"). Banks usually write down in the contingency funding plan which early warning indicators (para 39) or limit breaches trigger a call to APRA, so that the decision to notify is not left to one person on the night. The usual owner is the Treasurer or the Chief Risk Officer, and the notification is logged.

**Evidence.** A notification protocol; a log of contacts with APRA with times; the minutes of the meeting that decided whether a concern met the threshold; and an exercise record showing the protocol was tested.

> **Watch out:** "As soon as possible" is not "at the next quarterly meeting". The test is the earliest practicable time after the concern arises. "Immediately" is stricter still and applies to a severe liquidity stress (APS 210 para 14). The same word "immediately" appears in the MLH notification (Att B para 6) and the ELA notification (APS 210 para 70).

## 8.4 Board and senior management responsibilities (paras 15 to 20)

### 8.4.1 The Board (paras 15 to 18)

The **Board of directors** (the Board) is the governing body elected by shareholders (or, for a mutual, members) to oversee the institution.

| Para | Requirement | Reference |
|---|---|---|
| 15 | The Board "is ultimately responsible for the sound and prudent management of the liquidity risk of the ADI". The ADI must maintain a liquidity risk management framework "commensurate with the level and extent of liquidity risk to which the ADI is exposed from its activities". For a foreign ADI, the Board's responsibilities are fulfilled by the "senior officer outside Australia" | APS 210 para 15 |
| 16 | The framework must include at a minimum five items: (a) a Board-approved statement of liquidity risk tolerance; (b) the Board-approved liquidity management strategy and policy; (c) operating standards (policies, procedures, controls) for identifying, measuring, monitoring and controlling liquidity risk in line with the tolerance; (d) a Board-approved funding strategy; (e) a contingency funding plan | APS 210 para 16 |
| 17 | The Board must ensure that (a) senior management and other relevant personnel have the necessary experience to manage liquidity risk, and (b) the framework and practices are documented and reviewed at least annually | APS 210 para 17 |
| 18 | The Board must review regular reports on the liquidity position and, where necessary, information on new or emerging liquidity risks | APS 210 para 18 |

A **foreign ADI** is the Australian branch of an overseas bank; it has no Australian Board of its own, so para 15 puts the responsibility on the senior officer outside Australia (APS 210 para 15).

Note the difference between "approved by the Board" (the Board must sign off) and items (c) and (e) of para 16, which do not carry that wording. The tolerance, the strategy and policy, and the funding strategy are all Board-approved; the operating standards and the contingency funding plan are not described that way in para 16, although para 51 separately requires the Board to review and approve the contingency funding plan at least annually (APS 210 para 51).

**In a real bank.** Boards usually delegate detailed review to a Board Risk Committee, which reports to the full Board. A standing agenda item shows the LCR, NSFR, buffer above 100%, limit utilisation and early warning indicators. The annual cycle is a good way to line up the timed obligations: tolerance (para 22), framework review (para 17(b)), funding strategy (paras 45 and 46) and contingency funding plan (para 51) are often presented together.

**Evidence.** Board and committee papers and minutes with the approval recorded; the version-controlled framework document with review dates; a skills and experience matrix for liquidity staff (para 17(a)); the report pack that the Board receives (para 18).

### 8.4.2 Senior management (paras 19 to 20)

**Senior management** are the executives who run the bank day to day, such as the Chief Executive, Chief Financial Officer, Treasurer and Chief Risk Officer. Para 19 sets nine minimum duties.

| Para 19 | Duty | What it looks like |
|---|---|---|
| (a) | Develop the liquidity management strategy, policies and processes in accordance with the Board-approved tolerance | A policy suite that cites the tolerance |
| (b) | Ensure the ADI maintains sufficient liquidity at all times | Daily monitoring and a buffer above the minimum |
| (c) | Determine the structure, responsibilities and controls for managing liquidity risk and overseeing liquidity positions of all legal entities, branches and subsidiaries in the jurisdictions in which the ADI is active, and set these out in policy | A governance chart covering each entity and country |
| (d) | Ensure adequate internal controls over the integrity of liquidity risk management processes | Reconciliations, access controls, data quality checks, internal audit review |
| (e) | Ensure that stress tests, contingency funding plans and holdings of liquid assets are effective and appropriate | Management review of stress test design and results |
| (f) | Establish reporting criteria specifying scope, manner and frequency of reporting for various recipients (Board, senior management, asset/liability committee) and the parties responsible for preparing reports | A reporting calendar and report catalogue |
| (g) | Establish procedures and approvals for exceptions to policies and limits, including escalation procedures and follow-up for breaches | An exceptions register |
| (h) | Closely monitor current trends and potential market developments that may present significant, unprecedented and complex challenges, so that the strategy can be changed in time | Market watch notes and horizon-scanning |
| (i) | Continuously review information on liquidity developments and report to the Board on a regular basis | Regular Board reporting |

(APS 210 para 19.) The **asset/liability committee (ALCO)** mentioned in (f) is the management committee that oversees the balance sheet's funding, liquidity and interest rate position. The standard uses the term "asset/liability committee" without defining it.

Para 20 adds a knowledge requirement: "Senior management and the Board must be able to demonstrate a thorough understanding of the links between funding liquidity risk ... and market liquidity risk ... as well as how other risks, including credit, market, operational and reputation risks, affect the ADI's overall liquidity risk management strategy" (APS 210 para 20). The standard defines the two terms in the same paragraph:

- **Funding liquidity risk** is "the risk that an ADI may not be able to meet its financial obligations as they fall due".
- **Market liquidity risk** is "the risk that liquidity in financial markets, such as the market for debt securities, may reduce significantly".

(APS 210 para 20.) The links are the point: when market liquidity falls, assets cannot be sold at fair prices, which makes it harder to meet obligations; and a bank that must sell assets to meet obligations pushes prices down further.

**Evidence.** Board and senior management training records; a briefing paper on the links; stress test scenarios that combine market and funding stresses (compare para 26).

## 8.5 The liquidity risk tolerance (paras 21 to 24)

A **liquidity risk tolerance** (sometimes called a risk appetite statement for liquidity) "defines the level of liquidity risk that the ADI is willing to assume" (APS 210 para 21).

| Para | Requirement |
|---|---|
| 21 | The tolerance must be documented and "appropriate for the ADI's operations and strategy and its role in the financial system" |
| 22 | It must be reviewed, "at least annually", to reflect the ADI's financial condition and funding capacity |
| 23 | In setting it, the Board and senior management must ensure it lets the ADI manage its position "in such a way that it is able to withstand a prolonged period of stress" |
| 24 | It must be articulated so as to state clearly "the trade-off between risks and profits" |

(APS 210 paras 21 to 24.)

The trade-off in para 24 is a real economic one. Liquid assets such as government securities earn lower interest than loans, and long-term wholesale funding costs more than short-term funding. A cautious tolerance therefore lowers profit. The tolerance must say how much profit the bank is willing to give up for safety.

**In a real bank.** The tolerance is usually a one-to-two-page statement with quantitative metrics, for example a minimum LCR buffer above 100%, a minimum survival horizon in stress, limits on reliance on short-term wholesale funding, and a funding concentration limit. The specific numbers are chosen by each bank; the standard does not give any. The buffer above the regulatory minimum that Att A and Att C refer to ("in line with its liquidity risk tolerance", Att C para 4) is set here.

**Evidence.** The signed tolerance statement; the Board minute approving it; the annual review paper showing financial condition and funding capacity; a mapping from tolerance metrics to limits (para 37) and to early warning indicators (para 39).

## 8.6 The liquidity risk management framework (paras 25 to 35)

### 8.6.1 Structure, stress events and integration (paras 25 to 27)

| Para | Requirement | Comment |
|---|---|---|
| 25 | The framework must clearly set out the organisational structure for liquidity at Level 1 and Level 2 and define responsibilities and roles of management | An organisation chart and role descriptions |
| 26 | The framework must ensure that the ADI maintains sufficient liquidity, "including a cushion of unencumbered liquid assets, to withstand a range of stress events, including those involving the loss or impairment of both unsecured and secured funding sources". The stress source "could be specific to the ADI or market-wide or a combination of the two" | The three stress types: name-specific (idiosyncratic), market-wide and combined |
| 27 | The framework must be "well integrated into the ADI's overall risk management process" | Liquidity risk is not a separate silo; it connects to credit, market, operational and reputation risk (para 20) |

(APS 210 paras 25 to 27.) Note "loss or impairment of both unsecured and secured funding": **unsecured funding** is borrowed without specific collateral (most deposits and bonds); **secured funding** is borrowed against collateral (such as repos). A framework that assumes secured funding is always available fails para 26, because in a market-wide stress lenders raise the haircuts they apply to collateral or stop lending.

### 8.6.2 Independent oversight (para 28)

"An ADI's liquidity risk management oversight function must be operationally independent and staffed with personnel who have the skills and authority to challenge the ADI's treasury and other liquidity risk management businesses" (APS 210 para 28).

This is the "second line of defence" idea. The first line is the business that takes the risk (Treasury, which raises funding and manages liquid assets). The second line is an independent risk function that measures the risks, sets and monitors limits, and challenges the first line. "Operationally independent" means the oversight team does not report to the person whose decisions it is checking and is not paid on the same profit measures; "authority to challenge" means it can escalate and be heard.

**In a real bank.** The liquidity risk oversight team usually sits within the Risk division under the Chief Risk Officer. It owns an independent calculation or validation of the LCR and NSFR, reviews Treasury's limit breaches and exceptions, challenges stress test assumptions and presents to the Board Risk Committee. A data professional building the liquidity dashboard should expect two audiences: Treasury, who run the position, and the independent oversight team, who will want to reconcile numbers without relying on Treasury's own spreadsheets.

**Evidence.** The reporting line chart; terms of reference; documented challenges and their outcomes; independent validation reports; the profile of staff skills.

### 8.6.3 The liquidity management strategy (paras 29 to 32)

| Para | Requirement | Reference |
|---|---|---|
| 29 | The strategy "must include specific policies on liquidity management", such as (a) the composition and maturity of assets and liabilities; (b) the diversity and stability of funding sources; (c) the approach to managing liquidity in different currencies, across borders, and across business lines and legal entities; (d) the approach to intraday liquidity management | APS 210 para 29 |
| 30 | Must take account of liquidity needs under normal conditions and in stress, and "must include quantitative and qualitative targets" | APS 210 para 30 |
| 31 | Must be appropriate for the nature, scale and complexity of the ADI, considering its legal structure, key business lines, breadth and diversity of markets, products and jurisdictions and home and host regulatory requirements | APS 210 para 31 |
| 32 | The strategy, key policies and risk management structure "must be communicated throughout the organisation by senior management" | APS 210 para 32 |

(APS 210 paras 29 to 32.) **Home and host regulatory requirements** are the rules of the country where a bank is headquartered (home) and where it operates (host).

**In a real bank.** The strategy is typically a Board-approved document, supported by detailed policies on liquid asset portfolio composition, funding mix, currency management and intraday. "Quantitative and qualitative targets" (para 30) are usually things like target funding mix by source, minimum buffer, and qualitative statements such as maintaining a presence in key markets.

**Evidence.** The strategy document and version history; a table linking each para 29 topic to a policy; the communication record (intranet publication, training attendance) for para 32.

### 8.6.4 Escalation, awareness and review (paras 33 to 35)

| Para | Requirement | Reference |
|---|---|---|
| 33 | The ADI must have "adequate policies, procedures and controls" to ensure the Board and senior management are "informed immediately of new and emerging liquidity concerns". These include increasing funding costs or concentrations, increases in any funding requirements, the lack of availability of alternative sources of liquidity, material and/or persistent breaches of limits, a significant decline in the cushion of unencumbered liquid assets, or changes in external market conditions that could signal future difficulties | APS 210 para 33 |
| 34 | Senior management must be satisfied that all business units conducting activities that affect liquidity are fully aware of the strategy and operate in accordance with approved policies, procedures, limits and controls | APS 210 para 34 |
| 35 | The framework must be subject to effective review on an ongoing basis, in addition to a comprehensive review as part of the review of the risk management framework under CPS 220 Risk Management | APS 210 para 35 |

(APS 210 paras 33 to 35.)

Para 33 lists seven categories of triggering event for immediate internal escalation. These are the natural starting points for the early warning indicators of para 39. Para 34 reaches into business units that affect liquidity without being Treasury: for example, a lending business that agrees large undrawn commitments, or a payments business that influences intraday needs. Para 35 links this standard to **CPS 220 Risk Management**, the cross-industry prudential standard on the overall risk management framework (as generally understood; its full title and content are not reproduced in APS 210).

**Evidence.** The escalation matrix; incident logs; attestation by business unit heads (para 34); internal audit reports on the framework (para 35); the CPS 220 comprehensive review file.

## 8.7 Managing liquidity risk day to day (paras 36 to 43)

This group of paragraphs sets eight operating requirements. Chapter 9 describes how Treasury runs them day to day; this section covers what each rule requires.

### 8.7.1 Cash flow projection (para 36)

"An ADI must have a sound process for identifying, measuring, monitoring and controlling liquidity risk. This process must include a robust framework for comprehensively projecting cash flows arising from assets, liabilities and off-balance sheet items over an appropriate set of time horizons" (APS 210 para 36).

A **cash flow projection** lists the cash expected to come in and go out in future time buckets (overnight, a week, a month, three months, a year and beyond). Three phrases carry the weight: "comprehensively" (all assets, liabilities and off-balance sheet items, so undrawn commitments and derivatives are in), "over an appropriate set of time horizons" (a range, not just 30 days), and "robust" (documented assumptions and controls).

**In a real bank.** The projection is a maturity ladder (also called a liquidity gap report) with both contractual cash flows (what the contract says) and behavioural cash flows (what customers are expected to do, such as the share of at-call deposits that stay). The assumptions, especially for behavioural flows, are reviewed and approved by a committee.

**Evidence.** Assumption register with approval dates; back-testing of projected against actual flows; data lineage from source systems to the ladder; reconciliations of the ladder to the general ledger.

### 8.7.2 Limits (para 37)

"An ADI must set limits to control its liquidity risk exposure and vulnerabilities. Limits and corresponding escalation procedures must be reviewed regularly. Limits must be relevant to the business in terms of its location, complexity of activity, nature of products, currencies and markets served. Where a liquidity risk limit is breached, an ADI must implement a plan of action to review the exposure and reduce it to a level that is within the limit" (APS 210 para 37).

A **limit** is a numerical boundary on a risk measure, with an agreed escalation path when it is approached or breached. Typical limits include a minimum survival horizon, a cap on the share of funding maturing in a bucket, a cap on reliance on any one counterparty or market, and floors on liquid asset holdings. The standard does not prescribe any limit value or measure, only that limits exist, are relevant, are "reviewed regularly" and that a breach triggers "a plan of action". "Regularly" has no stated frequency.

**Evidence.** A limit framework table (measure, value, owner, escalation path); daily limit utilisation reports; the breach log with plans of action and close-out dates (para 37); the minutes of reviews.

### 8.7.3 Collateral (para 38)

"An ADI must actively manage its collateral positions, differentiating between encumbered and unencumbered assets. An ADI must monitor the legal entity and physical location where collateral is held and how it may be mobilised in a timely manner" (APS 210 para 38).

**Collateral** is an asset pledged to secure an obligation. An asset is **encumbered** when it is pledged or otherwise unavailable, and **unencumbered** when it is free to be sold or pledged. **Mobilised** means made available to use, for example delivered to the RBA or another lender within the time needed. The paragraph asks three questions of every asset: is it free, where is it (which legal entity and which custodian or location) and how fast could it be used?

Why location matters: a government bond held by a foreign subsidiary may be legally free but practically stuck, because it takes days to move or because local rules restrict transfer. For an LCR it must also pass the operational requirements (Att A paras 22 to 25; Chapter 5); for the NSFR, encumbrance duration drives the RSF factor (Att C para 23; Chapter 6).

**Evidence.** A daily unencumbered asset report by legal entity and custodian; documentation of the mobilisation process and lead times (for example settlement time to the RBA); collateral agreements and margin call logs.

### 8.7.4 Early warning indicators (para 39)

"An ADI must design a set of early warning indicators to aid its daily liquidity risk management processes in identifying the emergence of increased risk or vulnerabilities in its liquidity risk position or potential funding needs. Such early warning indicators must be structured so as to assist in the identification and escalation of any negative trends in the ADI's liquidity position and lead to an assessment and potential response by management to mitigate the ADI's exposure to these trends" (APS 210 para 39).

An **early warning indicator (EWI)** is a measure that tends to move before a problem becomes serious. The standard sets no list. Para 33 supplies a ready list of themes: funding costs, funding concentrations, funding requirements, availability of alternative liquidity, limit breaches, the decline in the unencumbered liquid asset cushion and external market conditions. Example EWIs a bank might use are the spread it pays on new wholesale funding relative to a benchmark, the share of deposits lost in a week, a credit rating outlook change, a fall in deposit balances of its largest depositors, and a rise in collateral calls. These examples are illustrations, not prescriptions in the standard.

The standard stresses "daily" processes, escalation and a response by management. An EWI with no named owner and no response is not compliant.

**Evidence.** The EWI catalogue with thresholds (amber and red), owners and responses; daily dashboards; a log of EWI breaches, assessments and actions.

### 8.7.5 Management information (para 40)

"An ADI must have a reliable management information system that provides the Board, senior management and other appropriate personnel with timely and forward-looking information on the liquidity position of the ADI" (APS 210 para 40).

A **management information system** is the set of data, calculations and reports that supply decision-makers. The three tests are **reliable** (accurate, controlled and reconciled), **timely** (available soon enough to act on) and **forward-looking** (projections as well as the current position). Para 19(f) says management must set reporting criteria for scope, manner, frequency and responsible parties (APS 210 para 19(f)).

**In a real bank.** This is the layer where a liquidity dashboard sits: a daily LCR, NSFR and maturity ladder, with drill-downs. Reliability needs data quality checks, ownership of each source, and reconciliations to the ledger.

**Evidence.** Data lineage documents; data quality exception reports; reconciliation sign-offs; the report catalogue showing recipient, frequency, timing and owner; evidence of the delivery time.

### 8.7.6 Intraday liquidity (para 41)

"An ADI must actively manage its intraday liquidity positions and risks in order to meet payment and settlement obligations on a timely basis under both normal and stressed conditions, thus contributing to the orderly functioning of payment and settlement systems" (APS 210 para 41).

**Intraday liquidity** is the money a bank needs during the business day to make payments before it receives incoming payments. Large payments settle in real time in the RBA's payment system, and a bank that cannot fund an early payment may delay others in the system. The paragraph covers "normal and stressed" conditions and notes the contribution to the "orderly functioning" of the payment system, a systemic reason for the rule. The strategy must also contain an intraday approach (APS 210 para 29(d)), and the contingency funding plan must address time horizons "including intraday" (APS 210 para 49).

**Evidence.** Intraday usage reports (peak use, time of peak); stress scenarios for intraday (for example, a delayed receipt from a large counterparty); procedures for monitoring payment flows.

### 8.7.7 Costs and benefits allocation (para 42)

"An ADI must develop and implement a costs and benefits allocation process for funding and liquidity that appropriately apportions the costs of prudent liquidity management to the sources of liquidity risk and provides appropriate incentives to manage liquidity risk" (APS 210 para 42).

This is usually called **funds transfer pricing (FTP)** in banking practice: a charge made by Treasury to business units for the liquidity they use, and a credit paid to units that bring in stable funding. The standard does not use the term FTP; the description is "a costs and benefits allocation process". Without it, a lending business that writes long loans funded by short deposits would look more profitable than it is, because the cost of liquidity would sit in a central pool. With it, the business that creates the liquidity risk bears the cost.

**Evidence.** The FTP methodology and approval; the pricing curve and its inputs; a monthly allocation report; evidence that product pricing uses the charges.

### 8.7.8 Currencies (para 43)

An ADI that is active in multiple currencies must (a) "maintain liquid assets consistent with the distribution of its liquidity needs by currency"; (b) "assess its aggregate foreign currency liquidity needs and determine an acceptable level of currency mismatches"; and (c) "undertake a separate analysis of its strategy for each currency in which it has material activities, considering potential constraints in times of stress" (APS 210 para 43).

A **currency mismatch** exists when the bank has liabilities in one currency and assets in another. The risk is that, in a stress, the market for converting currencies (the foreign exchange swap market) may shut or become costly. The reason for separate currency analysis is the LCR's own requirement: the Australian dollar LCR and the all currencies LCR must each be at least 100% for a locally incorporated ADI (APS 210 para 55(a)).

**Evidence.** Currency-by-currency ladder and LCR; a policy statement defining "material" currencies and the acceptable mismatch; limits on mismatch; stress tests for FX market closure.

## 8.8 Funding strategy (paras 44 to 46)

| Para | Requirement | Reference |
|---|---|---|
| 44(a) | "Develop and document a three-year funding strategy, which must be provided to APRA on request" | APS 210 para 44(a) |
| 44(b) | "Maintain an ongoing presence in its chosen funding markets and strong relationships with funds providers" | APS 210 para 44(b) |
| 44(c) | "Regularly gauge its capacity to raise funds quickly", identify the main factors that affect this and monitor them "to ensure that estimates of fund-raising capacity remain valid" | APS 210 para 44(c) |
| 45 | The funding strategy must be reviewed and approved by the Board, at least annually, and supported by robust assumptions in line with the liquidity management strategy and business objectives | APS 210 para 45 |
| 46 | It must be reviewed and updated, at least annually, to account for at a minimum changed funding conditions and/or a change in strategy. The ADI "must advise APRA of any material changes" | APS 210 para 46 |

The **funding strategy** is the plan for how the bank will raise the money it needs: how much from retail deposits, how much from wholesale markets, in what maturities and currencies, and from what investors. A three-year horizon forces it to look ahead at maturities (the bonds that will have to be refinanced). Para 44(b) protects against the risk that a bank which stays out of a market for years finds it closed when it needs it: wholesale investors have long memories. Para 44(c) asks for an honest estimate of how much the bank could raise, how fast, and what could change that.

Two obligations to APRA exist: the strategy must be provided "on request" (para 44(a)) and "material changes" must be advised (para 46). The standard does not define "material". The bank should set a policy for what is material (for example, a shift in target retail share or a market exit) and record decisions about whether a change was notified.

**In a real bank.** The funding plan is produced by Treasury with Finance and Business units, uses the balance sheet forecast, and is approved by the Board with the budget. It includes issuance targets by quarter, and regular tests of market capacity (such as sounding investor demand).

**Evidence.** The three-year plan; Board approval minutes with dates; the annual update; a register of material changes with the decision whether APRA was notified; investor meeting records; funding capacity assessments.

## 8.9 The contingency funding plan (paras 47 to 51)

A **contingency funding plan (CFP)** is the plan for what the bank will do if it faces a funding shortfall: who decides, which sources of cash it will tap first, how fast, and what is said to customers and regulators.

| Para | Requirement | Reference |
|---|---|---|
| 47 | A formal plan that "clearly sets out the strategies for addressing liquidity shortfalls in stressed situations", outlines policies for "a range of stress environments", establishes "clear lines of responsibility" and includes "clear invocation and escalation procedures" | APS 210 para 47 |
| 48 | Commensurate with the ADI's complexity, risk profile, scope and role. Must articulate (i) available contingency funding sources and the amounts estimated from each, (ii) escalation and prioritisation procedures detailing when and how each action can and must be activated and (iii) the lead time needed to tap each source. Must be flexible so the ADI can respond quickly in a variety of situations | APS 210 para 48 |
| 49 | Closely integrated with the ongoing analysis of liquidity risk and the assumptions and results of stress tests; must address "a range of different time horizons, including intraday" | APS 210 para 49 |
| 50 | For an ADI with retail deposits, the plan must address a retail deposit run and include measures "to repay retail depositors as soon as practicable". It "must not rely upon closing distribution channels to retail depositors". It must seek to ensure that in the event of loss of market confidence, retail depositors wishing to retrieve their deposits may do so "as quickly and as conveniently as is practicable in the circumstances, and within the contractual terms and conditions applicable to the relevant deposit products" | APS 210 para 50 |
| 51 | Must be reviewed and tested, at least annually, to ensure effectiveness and operational feasibility. The Board must review and approve it, at least annually, or more often as circumstances require | APS 210 para 51 |

**Key concepts.**

- **Invocation** means formally activating the plan (a decision made by a named person or committee). **Escalation** means moving the matter up the management chain.
- **Contingency funding sources** include selling or repo'ing liquid assets, drawing on committed lines, raising secured funding against loan portfolios (for example by securitising them, as generally understood), and, in the last resort, the Reserve Bank of Australia's facilities (see 8.12).
- **Lead time** is the time between deciding to use a source and receiving the cash. It matters because a source of A$5bn that takes ten days to deliver is useless against a three-day outflow.
- **Retail run (para 50).** The standard prohibits relying on "closing distribution channels" (shutting branches, switching off online banking or limiting ATMs) as a defence. Closing channels would stop depositors withdrawing, but it destroys confidence and conflicts with the obligation to repay. The contractual terms still apply: a term deposit may not be repayable early, so the plan works "within the contractual terms and conditions". The plan needs measures such as capacity in payment channels, call-centre and branch staffing and sufficient cash and payment system liquidity to meet withdrawals.

**In a real bank.** The CFP is a document with an action menu: an indicator dashboard that leads to a "stage" (for example, watch, alert, crisis), a table of actions per stage with the owner and lead time, a communications plan, and a contact list for APRA and the RBA. The plan is tested through a simulation or "fire drill" with the executive and sometimes the Board.

**Evidence.** The CFP document with version history; a table of contingency sources with amounts and lead times (para 48); the test or simulation report with lessons learned (para 51); Board approval minutes (para 51); the retail run section (para 50) and its operational runbooks for branches, online channels and payment capacity; the link to stress test results (para 49).

> **Watch out:** Para 51 requires two different annual actions: a review *and test* of the plan, and a Board review and approval. A document approved by the Board but never exercised does not meet the first.

## 8.10 Classification, the quantitative requirements and the stress testing duty (paras 52 to 66)

Paras 52 to 61 are covered in other chapters: classification into LCR ADIs and MLH ADIs (paras 52 to 54; Chapter 7), the LCR minimum and APRA's power to set a higher minimum (paras 55 to 56; Chapter 5), the MLH minimum (paras 57 to 58; Chapter 7) and the NSFR minimum (paras 59 to 61; Chapter 6). One sentence on each: an LCR ADI must hold HQLA to cover 30 days of severe stress with an LCR of at least 100% (AUD and all currencies, locally incorporated) or 40% (all currencies, foreign) (APS 210 para 55); an MLH ADI must hold 9% of liabilities in specified liquid assets (APS 210 para 57); a locally incorporated LCR ADI must keep an NSFR of at least 100% at all times (APS 210 paras 59 and 60).

### 8.10.1 Stress testing (paras 62 to 66)

A **stress test** is an exercise that projects the bank's liquidity position under an adverse scenario to see whether it would survive.

| Para | Requirement | Reference |
|---|---|---|
| 62 | "In addition to" the LCR requirements, an LCR ADI must conduct stress tests "on a regular basis" for a variety of short-term and protracted institution-specific and market-wide scenarios, "individually and in combination", to identify sources of potential liquidity strain and to ensure current exposures remain in line with the liquidity risk tolerance | APS 210 para 62 |
| 63 | Outcomes must be used to adjust the liquidity management strategy, policies and positions and to develop effective contingency plans | APS 210 para 63 |
| 64 | Stress tests must analyse the impact on Level 1 and Level 2 liquidity positions and on individual business lines | APS 210 para 64 |
| 65 | An LCR ADI's scenarios and assumptions must be well documented and reviewed together with the results. Results, vulnerabilities and resulting actions "must be reported to, and discussed with, the Board and APRA". Results must be integrated into strategic planning and day-to-day risk management and "explicitly considered in the setting of internal limits" | APS 210 para 65 |
| 66 | An LCR ADI must decide how to incorporate stress test results in assessing and planning for potential funding shortfalls in its contingency funding plan | APS 210 para 66 |

Points to note:

- **Who it applies to.** Paras 62, 65 and 66 refer expressly to an LCR ADI. Paras 63 and 64 do not repeat the words but follow para 62's stress tests. An MLH ADI should read the general framework paragraphs (such as para 26, which requires the framework to withstand stress events) and not assume that stress testing is optional.
- **Not just the LCR scenario.** The LCR is one fixed scenario. Para 62 requires a variety: short-term and protracted, bank-specific and market-wide, and combinations. This is the "survival horizon" analysis: how many days or weeks the bank survives under each scenario.
- **Reporting to APRA.** Para 65 requires results and vulnerabilities to be reported "to, and discussed with, the Board and APRA". The standard does not say how often. Banks typically provide results through their regular APRA engagement.
- **Feedback loop.** Results feed strategy (para 63), limits (para 65) and the CFP (paras 49 and 66). A stress test that has no effect on any of these fails the standard in substance.

**In a real bank.** Stress testing is often a monthly or quarterly exercise run by the independent oversight team, using scenarios such as a downgrade, a loss of wholesale market access for three months, a retail run, and a combined scenario. Each shows a cash-flow projection and whether the buffer lasts. The number of days survived is the survival horizon, often with an internal minimum set by the tolerance.

**Evidence.** The scenario library and assumptions; results packs; Board and committee minutes recording discussion; communications to APRA; action tracker showing changes to limits and the CFP.

> **Example (survival horizon, simplified):** Example Bank has HQLA of A$17.0bn and 30-day net cash outflows of A$11.55bn under the LCR stress (Chapter 5). If those outflows ran evenly, the daily net outflow is 11.55 / 30 = A$0.385bn. The liquid assets would last 17.0 / 0.385 = 44.2 days. This is an illustration of the idea only: real survival horizon analysis uses day-by-day projections, not an even rate, and the LCR scenario is not designed to extend beyond 30 days.

## 8.11 Local operational capacity for foreign ADIs (paras 67 to 69)

A foreign ADI relies, in part, on its overseas head office. The **local operational capacity (LOC)** requirement tests whether the Australian branch could still run if it lost that help.

| Para | Requirement | Reference |
|---|---|---|
| 67 | A foreign ADI must assess its LOC "to liquidate assets and make or receive payments without assistance from staff located outside Australia", at least annually, and provide the results to APRA on request | APS 210 para 67 |
| 68 | The assessment must consider, at a minimum, "a scenario involving a combination of time zones, different public holidays and an offshore operational risk event" under which the foreign ADI would operate, including making and receiving payments, "for a minimum of three business days without assistance from staff located outside Australia". The foreign ADI may assume that related-party operations within Australia continue to function normally | APS 210 para 68 |
| 69 | APRA may impose additional requirements on a foreign ADI if the assessment highlights issues about its ability to liquidate assets and make or receive payments without offshore staff | APS 210 para 69 |

An example scenario: an outage hits the head office's data centre on the day before a long weekend in the home country that is a working day in Australia. The Australian branch must still process payments and sell securities for three business days with its local staff.

**Evidence.** The annual LOC assessment and approval; runbooks for payment processing and securities sales by local staff; system access lists and testing of local logins; staffing and roster plans; and the record of providing the results to APRA on request.

## 8.12 Exceptional Liquidity Assistance (para 70)

"An ADI under severe liquidity stress may request Exceptional Liquidity Assistance (ELA) from the Reserve Bank of Australia (RBA). Prior to approaching the RBA, the ADI must notify APRA immediately of the ADI's liquidity concerns and its intention to request ELA. An ADI must provide any information requested by APRA or the RBA in relation to the ADI's ELA request. An ADI must have the operational capability to provide information along with its application for ELA or within other timeframes specified by APRA" (APS 210 para 70).

**Exceptional Liquidity Assistance (ELA)** is the central bank's lender-of-last-resort support to a solvent bank that is short of liquidity. The paragraph sets out four duties: (1) the ADI **may** request it; (2) it **must** notify APRA immediately before approaching the RBA; (3) it must supply any information that APRA or the RBA asks for; and (4) it must have the operational capability to provide that information with the application or within other timeframes that APRA specifies. The standard does not say what the RBA will do with a request; the terms and conditions of ELA are decided by the RBA (as generally understood, and described in Chapter 2).

The last duty is a data requirement. A bank that could not produce a list of its unencumbered assets by legal entity, with their values and the loan collateral eligible for pledge, in a matter of hours would have trouble meeting para 70. This is the kind of requirement that a liquidity data platform should be designed to support.

**Evidence.** An ELA readiness playbook; a standing data pack (asset listings, loan-level data, cash-flow forecasts, balance sheet) that can be generated at short notice; named contacts; periodic test runs of the data pack (the pack is the evidence that "operational capability" exists).

## 8.13 Adjustments and previous exercise of discretion (paras 71 to 72)

| Para | Requirement | Reference |
|---|---|---|
| 71 | "APRA may adjust or exclude a specific requirement in this Prudential Standard in relation to an ADI or authorised NOHC." Footnote 1: refer to subsection 11AF(2) of the Banking Act | APS 210 para 71 |
| 72 | An ADI "must contact APRA if it seeks to place reliance, for the purposes of complying with this Prudential Standard, on a previous exemption or other exercise of discretion by APRA under a previous version of this Prudential Standard" | APS 210 para 72 |

Para 71 means the standard is not rigid. APRA can adjust (change) or exclude (remove) a requirement for a given ADI or authorised NOHC, and does so in writing (APS 210 para 8). Para 72 deals with the new July 2025 version (APS 210 para 6). A bank that holds a previous approval, for example an approval to treat a class of asset in a particular way, cannot assume that it carries over to the new version. It must contact APRA if it wants to rely on it.

**In a real bank.** Compliance maintains a register of every APRA approval, adjustment and exemption with its date, scope and conditions. When a standard is replaced, each entry is reviewed and, where the bank wants to continue, APRA is contacted.

**Evidence.** The register; the written APRA letters; and the correspondence from the contact required by para 72.

> **Watch out:** In a data model, flag any calculation that depends on an APRA approval (for example the Att B approvals "for a prudential purpose", or the Att C para 24 lower factor for exceptional central bank operations, or the Att C para 38 interdependence determination). Each should carry a reference to the written approval and an end date if it has one.

## 8.14 Every timed obligation in APS 210 (main body)

The table lists each time-related requirement in the main body of APS 210 (paras 1 to 72), plus the notification and timing rules in the attachments that affect the same duties.

| Para | Obligation | Timing |
|---|---|---|
| 6 | Standard commences | 1 July 2025 |
| 12 | Maintain sufficient liquidity to meet obligations as they fall due | At all times |
| 14 | Inform APRA of any concerns about current or future liquidity and plans to address them | As soon as possible |
| 14 | Notify APRA of a severe liquidity stress and the action being taken | Immediately |
| 17(b) | Document and review the liquidity risk management framework and practices | At least annually |
| 18 | Board reviews reports on the liquidity position (and, where necessary, on new or emerging risks) | Regularly |
| 19(b) | Senior management ensures sufficient liquidity | At all times |
| 19(i) | Senior management continuously reviews liquidity developments and reports to the Board | Continuously; report on a regular basis |
| 22 | Review the liquidity risk tolerance | At least annually |
| 33 | Inform Board and senior management of new and emerging liquidity concerns | Immediately |
| 35 | Review the liquidity risk management framework | On an ongoing basis, plus a comprehensive review within the CPS 220 review |
| 36 | Project cash flows | Over an appropriate set of time horizons |
| 37 | Review limits and escalation procedures | Regularly |
| 39 | Early warning indicators support | Daily liquidity risk management |
| 40 | Management information to the Board and senior management | Timely and forward-looking |
| 41 | Meet payment and settlement obligations | On a timely basis, normal and stressed conditions |
| 44(a) | Three-year funding strategy | Provided to APRA on request |
| 44(c) | Gauge capacity to raise funds quickly | Regularly |
| 45 | Board review and approval of the funding strategy | At least annually |
| 46 | Review and update the funding strategy | At least annually |
| 46 | Advise APRA of material changes to the funding strategy | (No period stated; on a material change) |
| 49 | Contingency funding plan addresses different time horizons | Including intraday |
| 50 | Repay retail depositors | As soon as practicable |
| 51 | Review and test the contingency funding plan | At least annually |
| 51 | Board review and approval of the contingency funding plan | At least annually, or more often as circumstances require |
| 54 | Meet minimum quantitative requirements for the ADI's classification | Continuously, absent a situation of financial stress |
| 60 | NSFR of at least 100% (locally incorporated LCR ADI) | At all times |
| 62 | Stress tests (LCR ADI) | On a regular basis |
| 67 | Local operational capacity assessment (foreign ADI) | At least annually; results to APRA on request |
| 68 | Operate without offshore staff in the LOC scenario | A minimum of three business days |
| 70 | Notify APRA before approaching the RBA for ELA | Immediately, before approaching the RBA |
| 70 | Provide information for an ELA request | With the application or within other timeframes specified by APRA |
| 72 | Contact APRA before relying on a previous exemption or discretion | Before relying on it |
| Att A para 5 | Notify APRA when using the LCR buffer in stress (see Chapter 5) | As set out in Att A para 5 |
| Att B para 6 | Inform APRA when liquid assets may fall below the MLH requirement | Immediately |
| Att C para 4 | Maintain a buffer above the required NSFR | At all times |

The most important pattern: **annually** for the framework (para 17(b)), tolerance (para 22), funding strategy (paras 45 and 46), contingency funding plan (para 51) and foreign ADI LOC assessment (para 67); **immediately** for severe stress, ELA, and board escalation of emerging concerns (paras 14, 33, 70); **continuously** for the ratios (paras 54, 60).

## 8.15 Governance as a data requirement: what to build

The standard does not mention dashboards, but several paragraphs create data needs that any liquidity platform should meet.

| Paragraph | Data need |
|---|---|
| 36 | Cash flow projections by bucket, including off-balance sheet items |
| 37 | Limits with daily utilisation and a breach log with action plans |
| 38 | Encumbered and unencumbered assets by legal entity and location, with time to mobilise |
| 39 | EWI values, thresholds and escalation status each day |
| 40 | Reliable, timely, forward-looking reports with lineage and reconciliation |
| 41 | Intraday balance and payment flows |
| 42 | Liquidity cost allocations by business unit |
| 43 | Position by currency |
| 44 to 46 | Funding plan against actual issuance, and the capacity estimates |
| 47 to 51 | CFP action menu, source amounts and lead times; test records |
| 62 to 66 | Scenario definitions, results and actions taken |
| 70 | A standing ELA data pack |

## Key points

- The key principles require a robust framework, sufficient liquidity at all times, stable funding and prompt notification to APRA (APS 210 paras 11 to 14).
- The Board is ultimately responsible for liquidity risk and must approve the tolerance, strategy and funding strategy; senior management implements them (APS 210 paras 15 to 19).
- The liquidity risk tolerance must be documented, reviewed at least annually and state the trade-off between risk and profit (APS 210 paras 21 to 24).
- The oversight function must be operationally independent and able to challenge Treasury (APS 210 para 28).
- Operating requirements cover cash flow projection, limits, collateral, early warning indicators, management information, intraday liquidity, cost allocation and currencies (APS 210 paras 36 to 43).
- The three-year funding strategy is reviewed, updated and Board-approved at least annually, and material changes must be advised to APRA (APS 210 paras 44 to 46).
- The contingency funding plan must cover a retail run without closing distribution channels, and be reviewed, tested and Board-approved at least annually (APS 210 paras 47 to 51).
- LCR ADIs must run varied stress tests and report the results to the Board and APRA, and use them in limits and the contingency plan (APS 210 paras 62 to 66).
- Foreign ADIs must assess local operational capacity annually for a scenario of at least three business days (APS 210 paras 67 to 69).
- An ADI must notify APRA immediately before requesting ELA from the RBA and be able to supply information quickly (APS 210 para 70); APRA can adjust requirements and previous discretions need to be re-confirmed (APS 210 paras 71 to 72).

## Check your understanding

1. **Question:** Which obligations in APS 210 must be performed "at least annually"? List them with paragraph numbers.
   **Answer:** Documenting and reviewing the framework and practices (para 17(b)); reviewing the liquidity risk tolerance (para 22); Board approval of the funding strategy (para 45); review and update of the funding strategy (para 46); review and test of the contingency funding plan and Board review and approval of it (para 51); and the local operational capacity assessment by a foreign ADI (para 67).

2. **Question:** Why can a Board approve the contingency funding plan every year and still breach para 51?
   **Answer:** Para 51 requires the plan to be both reviewed and *tested* at least annually to show effectiveness and operational feasibility, as well as Board review and approval. Approval without testing does not meet the first limb.

3. **Question:** Example Bank's tolerance requires an LCR buffer of at least 120%. Its net cash outflows are A$11.55bn and HQLA is A$17.0bn. How much HQLA could it use or lend out before it hits its tolerance?
   **Answer:** HQLA needed for 120% = 1.20 x 11.55 = A$13.86bn. Surplus above tolerance = 17.0 - 13.86 = A$3.14bn. (The regulatory minimum of 100% would be A$11.55bn, a surplus of A$5.45bn.) The tolerance is set by the ADI under paras 21 to 24, and Att A and Att C refer to a buffer in line with it (Att C para 4).

4. **Question:** A bank closes its online banking for four hours during a rumour-driven run to "give itself time". Which paragraph does this probably breach, and why?
   **Answer:** Para 50: a retail run contingency plan "must not rely upon closing distribution channels to retail depositors" and must seek to let depositors retrieve their deposits "as quickly and as conveniently as is practicable", within contractual terms.

5. **Question:** Using the survival horizon illustration, Example Bank's HQLA falls to A$14.0bn after lending out A$3.0bn of cash. If net outflows are still A$11.55bn over 30 days at an even rate, how many days does the HQLA last?
   **Answer:** Daily outflow = 11.55 / 30 = A$0.385bn. 14.0 / 0.385 = 36.4 days. (Illustration only; the LCR stress is a 30-day scenario.)

6. **Question:** A foreign ADI's head office suffers a systems outage on a day that is a public holiday there and a working day in Australia. What must the Australian branch have shown it can do?
   **Answer:** Under paras 67 and 68 it must have assessed, at least annually, that it can liquidate assets and make and receive payments without assistance from staff outside Australia for a minimum of three business days, considering a combination of time zones, public holidays and an offshore operational risk event.

7. **Question:** Before approaching the RBA for ELA, what must an ADI do, and what data capability must it have?
   **Answer:** It must notify APRA immediately of its liquidity concerns and its intention to request ELA, and it must have the operational capability to provide information requested by APRA or the RBA along with its application or within other timeframes specified by APRA (para 70).

8. **Question:** Suppose APRA granted a bank a written approval under a previous version of APS 210 to treat a particular asset in a certain way. The July 2025 version commenced. What must the bank do before relying on the approval?
   **Answer:** Contact APRA (para 72). The standard does not say the approval carries over automatically.

---

# Chapter 9: How Treasury manages liquidity day to day

This chapter turns the rules of APS 210 into the daily routine of a bank. It describes who does what, which reports they use, and how common events move the two ratios. The governance rules themselves are covered paragraph by paragraph in Chapter 8; the ratios are built line by line in Chapters 5 and 6.

## Who does what

A **bank function called Treasury** (not to be confused with the government department of the same name, Chapter 2) manages the bank's own cash, funding and liquid assets. It is the part of the bank that raises money, invests surplus cash, holds the liquid asset portfolio and keeps the bank able to pay. Treasury is a "first line" function: it takes the liquidity decisions.

| Role | What it does | APS 210 link |
|---|---|---|
| **Board** | Ultimately responsible for the sound and prudent management of liquidity risk; approves the liquidity risk tolerance, the liquidity management strategy and policy, and the funding strategy; reviews regular liquidity reports; ensures the framework is documented and reviewed at least annually | Paras 15 to 18 |
| **Senior management** | Develops strategy, policies and processes within the Board's tolerance; ensures sufficient liquidity at all times; sets the reporting criteria for the Board, senior management and the asset/liability committee; sets procedures for exceptions and limit breaches | Para 19 |
| **ALCO** (asset and liability committee) | A senior management committee, usually chaired by the Chief Financial Officer or Treasurer, that reviews the liquidity position, funding plan, limits, stress test results and pricing. APS 210 names the "asset/liability committee" as a recipient of reports (para 19(f)); the standard does not prescribe its membership. | Para 19(f) |
| **Treasury** | Executes: manages the liquid asset portfolio, issues wholesale debt, manages daily cash and intraday positions, runs the contingency funding plan in a crisis | Paras 36 to 51 |
| **Liquidity risk oversight (second line)** | An independent function that measures, monitors and challenges. It must be "operationally independent and staffed with personnel who have the skills and authority to challenge the ADI's treasury and other liquidity risk management businesses" | Para 28 |
| **Business units** (retail, business banking, institutional) | Create liquidity risk by gathering deposits, writing loans, and granting commitments; must be "fully aware of" the strategy and operate within limits | Para 34 |

The split matters in data work. Treasury produces the numbers it uses to run the bank; the independent oversight function validates them and reports separately. A dashboard for Treasury is typically a first-line tool; the second line will want its own independently sourced figures.

> **In the standard:** "An ADI's liquidity risk management oversight function must be operationally independent and staffed with personnel who have the skills and authority to challenge the ADI's treasury and other liquidity risk management businesses." (APS 210 para 28)

## The liquid asset portfolio

### What it is and why it exists

The **liquid asset portfolio** (also called the liquidity buffer or HQLA portfolio) is the stock of unencumbered high-quality liquid assets that the bank holds to survive stress. In Example Bank it is A$17.0bn: A$5.0bn of cash and RBA balances plus A$12.0bn of government and semi-government securities. APS 210 requires a "cushion of unencumbered liquid assets" (APS 210 para 26), and the objective of the LCR is that the bank hold enough HQLA to meet needs for 30 calendar days of severe stress (Att A para 1).

### How it is run

Treasury decides how to hold the portfolio, within the Board's tolerance:

- **Composition.** Mix of cash at the RBA, government securities and semi-government securities. As generally understood (APG 210 guidance, which is not part of the standard), the Australian dollar HQLA available are notes and coin, balances at the RBA, and Australian Government and state and territory government securities.
- **Maturity.** Short-dated securities fall in price less when interest rates move, but pay less; long-dated securities pay more but are more volatile.
- **Diversification** across issuers within the permitted set.
- **Operational readiness.** The assets must be able to be sold or repoed quickly. The LCR operational requirements are set out in Att A paras 22 to 25 (Chapter 5). They include the principle that the assets be under the control of Treasury and not pledged elsewhere.
- **Encumbrance monitoring.** Any asset pledged or committed drops out of the buffer (see collateral management, below).
- **Currency.** The portfolio should match the currencies in which cash needs arise (APS 210 para 43(a)).

### Why it costs money

Liquid assets earn lower returns than loans. Suppose, for illustration only, that government securities yield 4.0% and the average loan yields 6.0%. Every A$1.0bn held in the buffer instead of lent forgoes about 2.0% a year, or A$20m. This forgone margin is the **cost of carry** of liquidity, and it is the reason bank managers do not hold unlimited liquid assets. The cost is also why APS 210 para 24 requires the liquidity risk tolerance to be "articulated in such a way that clearly states the trade-off between risks and profits".

The rates in this paragraph are invented for illustration and are not Example Bank figures.

### The buffer above 100%

Att A para 4 says: "An ADI must include an appropriate buffer of HQLA over the LCR requirement in line with its liquidity risk tolerance." The minimum is 100% (APS 210 para 55). A bank that runs exactly at 100% will breach with the first unexpected movement, so banks set an internal floor and a target above the minimum.

For Example Bank: HQLA of A$17.0bn against net cash outflows of A$11.55bn gives an LCR of 147.2% and a surplus over 100% of A$5.45bn (17.0 - 11.55). Treasury will ask: how much of that surplus is deliberate and how much is an accident of the day? A large unplanned surplus costs money; a small one risks a breach after routine movements.

> **Watch out:** Att A para 5 says that in stress the LCR may fall below the minimum as the bank uses its buffer, but the bank must "inform APRA immediately in the event of an actual breach of its LCR requirement or if it becomes aware of circumstances that may result in a breach". The buffer exists to be used, but its use is a notifiable event.

## Contractual versus behavioural cash flows

A **cash flow** is a movement of money in or out of the bank. A **cash inflow** brings money in (for example, a customer repays a loan); a **cash outflow** sends money out (for example, a deposit is withdrawn).

- **Contractual maturity** is the date an obligation is due under the contract. An at-call deposit has no fixed date, so its contractual maturity is "on demand".
- **Behavioural maturity** is the date the bank expects cash to move in practice, based on customer behaviour. Most at-call retail deposits stay for years, so their behavioural maturity is far longer than their contractual maturity. Mortgages often repay early, so their behavioural maturity is shorter than the contractual term.

Contractual cash flows tell you the worst case if every right were exercised; behavioural cash flows tell you what is expected. APS 210 requires the bank to project cash flows "arising from assets, liabilities and off-balance sheet items over an appropriate set of time horizons" (APS 210 para 36). The LCR and NSFR use fixed regulatory assumptions (run-off rates, factors) in place of the bank's own behavioural models, so they sit between pure contractual and bank-estimated behavioural views.

Treasury models behaviour using history: how much of a current account balance has stayed through past stress? How often are fixed-rate mortgages repaid early? The models need testing and governance because the assumptions drive decisions.

## The maturity ladder

The **maturity ladder** (also called the liquidity gap report or the maturity mismatch report) sorts cash inflows and outflows into time buckets, and shows the gap in each. A **maturity mismatch** is a difference between the timing of what comes in and what goes out.

### Columns and how to read them

| Bucket | Typical examples |
|---|---|
| Overnight | Cash at the RBA; payments due today |
| 2 to 7 days | |
| 8 to 30 days | |
| 31 to 90 days | |
| 91 days to 6 months | |
| 6 months to 1 year | |
| 1 to 5 years | |
| Over 5 years | |

For each bucket:

```
Net gap            = Inflows in bucket - Outflows in bucket
Cumulative gap     = Running total of net gaps from the first bucket
```

A negative net gap means more cash leaves than arrives in the bucket, so the bank must fund the shortfall by selling assets, borrowing or drawing on liquid assets. A **cumulative gap** is the running total, and shows the funding need that has built up by the end of each bucket.

### Example Bank, qualitatively

Using only the contractual terms in the shared example:

- Within 30 days, liabilities that could contractually be called include at least A$40.0bn of at-call retail deposits, A$4.0bn of at-call financial institution deposits and A$1.0bn of maturing wholesale debt: at least A$45.0bn. The shared example does not give the exact terms of the SME and corporate deposits, so they are left out of this simple sketch.
- Within 30 days, contractual inflows are A$5.0bn of cash plus A$2.8bn of loan repayments (A$1.0bn + A$0.8bn + A$1.0bn). The A$12.0bn of securities can be sold, but the ladder shows them at contractual maturity unless Treasury overlays a "liquidity value" view.
- On a purely contractual basis, the early buckets show a large negative cumulative gap, and the long buckets are positive (the A$50.0bn mortgage book repays slowly).

That is the shape of maturity transformation (Chapter 1). A negative early gap is normal for a bank. The question is not whether it is negative, but whether the bank has enough sellable or repo-able liquid assets to cover the gap under stress. That is why the contractual ladder is read alongside behavioural and stress views, and why regulators supplement it with the LCR.

> **Why it matters:** The ladder is a diagnostic. The LCR is a rule. A bank can pass the LCR and still have a worrying ladder (for example a cliff of wholesale maturities in month four) that the LCR's 30-day window cannot see. Treasury uses both.

## Funding concentration

**Concentration** means that a large share of something comes from a single source. **Funding concentration** is the dependence on one counterparty, product, market, currency or maturity for funding. Concentration is a risk because if that source withdraws, the bank has no easy substitute. APS 210 para 29(b) requires liquidity policies on "the diversity and stability of funding sources", and para 33 lists "increasing funding costs or concentrations" among the matters that must be escalated.

Treasury analyses concentration along several dimensions:

| Dimension | Question | Example from Example Bank |
|---|---|---|
| **Counterparty** | How much comes from the largest individual funders? | Largest ten depositors and wholesale investors |
| **Product** | How much comes from each product type? | Deposits A$69.0bn (75.0% of liabilities), wholesale debt A$21.0bn (22.8%) |
| **Market** | Domestic or offshore? Which investor base? | Share of wholesale debt raised offshore |
| **Currency** | In which currencies is funding raised? | AUD vs foreign currency share |
| **Maturity** | When does the wholesale debt mature? | A$1.0bn within 30 days; A$15.0bn at one year or more |

### The 1% threshold

A common test of significance is whether a single counterparty or product represents more than **1% of the balance sheet** (often stated as 1% of total liabilities). This is a threshold from the Basel Committee's liquidity monitoring tools, as generally understood, rather than a rule in APS 210. For Example Bank, 1% of the A$100.0bn balance sheet is A$1.0bn, so any single funder providing A$1.0bn or more would be a "significant counterparty" for monitoring. The threshold is a way of deciding what to report on, not a limit on how much funding may come from them.

## Survival horizon and stress testing in practice

A **survival horizon** is the number of days a bank can keep paying its obligations under a stress scenario before running out of liquidity. The LCR fixes the horizon at 30 days. APS 210 paras 62 to 66 require an LCR ADI to go further and run its own stress tests.

| Requirement | What it says | Para |
|---|---|---|
| Regular tests, many scenarios | "on a regular basis for a variety of short-term and protracted institution-specific and market-wide stress scenarios (individually and in combination)" | 62 |
| Use of results | Adjust strategy, policies and positions, and develop contingency plans | 63 |
| Reach | Level 1 and Level 2 positions, and individual business lines | 64 |
| Governance | Scenarios and assumptions documented and reviewed with the results; results and vulnerabilities and actions reported to the Board and APRA; integrated into strategic planning and day-to-day risk management; explicitly considered in setting internal limits | 65 |
| Link to the plan | Decide how to include results in the contingency funding plan | 66 |

### In practice

Treasury and the risk function run a library of scenarios, for example:

1. **Idiosyncratic**, severe: a rating downgrade with a 10-day wholesale shutdown and retail outflows.
2. **Market-wide**: offshore funding markets closed for three months; government bond prices fall.
3. **Combined** and protracted: both, over 90 days.
4. **Reverse stress test**: start from the point of failure and work backwards to the events that would cause it (a general technique).

For each scenario they project daily cash flows, the use of the buffer, and the day on which the buffer runs out. The survival horizon is that day. If it is shorter than the Board's tolerance, management must act: raise term funding, hold more HQLA or cut a limit. The results feed limit setting (APS 210 para 65).

> **Example:** Example Bank's 30-day net outflow is A$11.55bn against A$17.0bn of HQLA. If the 30-day outflow pattern continued at the same daily pace beyond day 30 and no new funding were raised, a rough survival horizon would be 30 x 17.0 / 11.55 = 44 days. This is a crude illustration; real survival horizons use scenario-specific daily projections, not a straight line.

## Limits and early warning indicators

### Limits

APS 210 para 37 requires the ADI to set limits "to control its liquidity risk exposure and vulnerabilities", reviewed regularly with escalation procedures, relevant to location, complexity, products, currencies and markets. Where a limit is breached, the ADI "must implement a plan of action to review the exposure and reduce it to a level that is within the limit". Senior management must set procedures for exceptions and breaches (para 19(g)).

Typical limit types:

| Limit | What it controls |
|---|---|
| Minimum LCR or NSFR (internal floor above the regulatory minimum) | Overall buffer |
| Maximum wholesale funding maturing in a given period | Rollover risk |
| Maximum share of funding from a single counterparty or product | Concentration |
| Minimum liquid asset holdings in each currency | Currency risk |
| Maximum loan-to-deposit ratio | Reliance on wholesale funding |
| Survival horizon floor under stress | Resilience |
| Intraday usage limits | Payment risk |

Limits usually come in layers: a Board-level limit, a lower management trigger that gives early warning and a breach procedure.

### Early warning indicators

APS 210 para 39 requires a set of **early warning indicators (EWIs)** "to aid its daily liquidity risk management processes in identifying the emergence of increased risk or vulnerabilities", structured so that negative trends are identified, escalated and assessed. Para 33 says the Board and senior management must be informed immediately of matters such as increasing funding costs or concentrations, increases in funding requirements, lack of availability of alternative sources, material or persistent limit breaches, a significant decline in unencumbered liquid assets, or changes in external market conditions.

The following are typical examples. They are illustrations of common practice, not a list from the standard.

| Indicator | Why it warns | Direction of concern |
|---|---|---|
| Rising cost of the bank's new wholesale debt relative to peers (spread to benchmark) | Investors demand more compensation for risk | Up |
| Shortening tenor of new wholesale issuance or investors refusing long terms | Market confidence falling | Down |
| Falling share of deposits that are stable or insured | More money could leave quickly | Down |
| Rising withdrawals or large transfers out of the largest depositors | Possible start of a run | Up |
| Concentration of funding in few counterparties | Single-name withdrawal risk | Up |
| Increase in the bank's credit default swap price or fall in its share price (market signals) | Market doubts the bank | Up / Down |
| Credit rating outlook change or downgrade | Triggers collateral calls and investor limits | Negative |
| Rising draw-downs on committed credit lines | Customers hoarding liquidity | Up |
| Increase in collateral demands from counterparties | Counterparties asking for more security | Up |
| Growing share of liquid assets that are encumbered | Buffer shrinking | Up |
| Drop in HQLA surplus over internal floor | Buffer shrinking | Down |
| Deterioration in asset quality (rising non-performing loans) | Funders may lose confidence | Up |
| Heavy social media or press attention | Confidence risk, fast runs | Up |
| Intraday peak usage rising | Payment pressure | Up |
| Stress in the RBA's or other markets, such as widening interbank spreads | Market-wide strain | Up |

Each EWI usually has a green, amber or red status with a defined escalation. The test is whether trends are caught early and escalated, not whether the list is long.

## Funds transfer pricing

**Funds transfer pricing (FTP)** is the internal process by which Treasury charges business units for the funding and liquidity they use, and credits them for the funding they provide. APS 210 para 42 requires the ADI to "develop and implement a costs and benefits allocation process for funding and liquidity that appropriately apportions the costs of prudent liquidity management to the sources of liquidity risk and provides appropriate incentives to manage liquidity risk."

How it works, with simple illustrative figures (not Example Bank figures):

- A business unit writes a 10-year fixed rate A$100m business loan. It is charged for long-term funding at, say, 5.0% (market rate plus a liquidity premium for stable funding).
- Another unit gathers A$100m of stable retail deposits. It is credited at, say, 4.0%, because the deposits are cheap and stable and the LCR gives them a low run-off rate.
- A unit that writes a large undrawn facility is charged for the liquid assets that must be held against it (for Example Bank, 5% of retail and SME facilities and 10% of corporate credit facilities run off in the LCR, so liquid assets must be held against those amounts).

Without FTP, the unit that writes long loans funded by cheap at-call deposits looks very profitable, while the true cost of liquidity is hidden in Treasury. With FTP, the cost follows the risk, so an operational deposit with high stability is valued, and a loan that needs stable funding is priced accordingly.

> **Why it matters:** FTP is how the LCR and NSFR become pricing signals. A product that consumes a lot of HQLA or required stable funding becomes more expensive to the business that sells it.

## Intraday liquidity

**Intraday liquidity** is the funds a bank can access during the business day to make payments and settle obligations in real time. APS 210 para 41 requires the ADI to "actively manage its intraday liquidity positions and risks in order to meet payment and settlement obligations on a timely basis under both normal and stressed conditions, thus contributing to the orderly functioning of payment and settlement systems."

**Settlement** is the final transfer of money or securities that completes a payment or trade. Large payments between banks are settled across their **Exchange Settlement Accounts** at the RBA (Chapter 2). Within a day, a bank may send a large payment before receiving incoming ones, causing its settlement account to run low. The intraday risk is that it cannot make a payment on time, or that others delay payments to it.

Treasury tracks:

| Measure | Meaning |
|---|---|
| **Opening balance** at the RBA | Cash available at the start of the day |
| **Peak (maximum) intraday usage** | The largest net amount of intraday liquidity used, measured from the lowest point of the day |
| **Timing of payments** | When the bank sends large payments, relative to when it receives them |
| **Available intraday sources** | Own balance plus borrowing against collateral |

As generally understood, the RBA provides intraday funding to ESA holders against eligible securities under repo, and intraday settlement happens in real time. The details should be checked on the RBA's website. Intraday management links to the contingency funding plan, which must address "a range of different time horizons, including intraday" (APS 210 para 49), and to the liquidity strategy, which must include the intraday approach (para 29(d)).

## Collateral management and encumbrance

APS 210 para 38 states that an ADI "must actively manage its collateral positions, differentiating between encumbered and unencumbered assets", and "must monitor the legal entity and physical location where collateral is held and how it may be mobilised in a timely manner."

An **encumbered asset** is one that has been pledged or committed so it is not free to be sold. **Collateral management** is the discipline of knowing, at all times, where every eligible asset is, what it is pledged against, and how fast it can be delivered where needed.

Treasury collateral teams track:

1. **Inventory** of eligible assets by type, legal entity and custodian.
2. **Encumbrance**: which assets are pledged (to repo counterparties, central counterparties, the RBA, derivative counterparties, covered bond pools).
3. **Mobilisation time**: how long to move an asset to where it is needed, including cut-off times and time zone issues.
4. **Margin calls**: demands from derivative counterparties for more collateral when values move. An **initial margin** is collateral posted at the outset to cover potential future losses; a **variation margin** is collateral posted or received as the value of the position changes day to day (Chapter 4).
5. **Downgrade triggers**: clauses requiring extra collateral if the bank's credit rating falls. Example Bank has A$0.2bn of collateral to be posted on a three-notch downgrade, which the LCR counts at 100%.

> **Example:** Suppose A$2.0bn of Example Bank's government bonds is posted to a derivative counterparty. Reported HQLA falls from A$17.0bn to A$15.0bn: the bonds remain on the balance sheet but are encumbered and do not count. If Treasury did not track this, the dashboard would overstate the buffer.

## Currency mismatches

APS 210 para 43 says an ADI active in multiple currencies must:

- (a) hold liquid assets consistent with the distribution of liquidity needs by currency;
- (b) assess aggregate foreign currency liquidity needs and set an acceptable level of **currency mismatches**; and
- (c) analyse its strategy for each material currency, "considering potential constraints in times of stress".

A **currency mismatch** is a difference between the currency of assets and liabilities, for example funding in US dollars used to lend in Australian dollars. A bank can usually convert currencies using foreign exchange (FX) swaps, but in stress this market may be closed or costly. That is why a locally incorporated ADI must meet an LCR of 100% on both an AUD basis and all currencies basis (APS 210 para 55(a)): AUD obligations have to be covered by AUD assets. Treasury reports the LCR in each material currency.

## Funding plan and wholesale issuance

APS 210 paras 44 to 46 require:

| Requirement | Para |
|---|---|
| Develop and document a **three-year funding strategy**, provided to APRA on request | 44(a) |
| Maintain an ongoing presence in chosen funding markets and strong relationships with funds providers | 44(b) |
| Regularly gauge the capacity to raise funds quickly, identify and monitor the main factors | 44(c) |
| Board reviews and approves the strategy at least annually, supported by robust assumptions | 45 |
| Review and update the strategy at least annually; advise APRA of any material changes | 46 |

A **funding strategy** is the bank's plan for where its funding will come from over time and in what mix. In practice it includes:

- Forecast balance sheet growth: lending growth minus deposit growth is the gap to be filled.
- A **wholesale issuance** programme: what bonds and notes to issue, in what currency, in which markets, at what tenors, and when. Spreading maturities avoids a "wall" of debt falling due at one time.
- Targets for stable ratios: LCR, NSFR, loan-to-deposit ratio.
- A plan for maturing debt: for Example Bank, A$1.0bn matures within 30 days, A$3.0bn between 30 days and six months, A$2.0bn between six months and one year, and A$15.0bn is one year or more. The plan must show how each will be refinanced.
- Contingency for markets being shut.

**Rollover (refinancing) risk** is the risk that maturing debt cannot be replaced. The reason for "ongoing presence" (APS 210 para 44(b)) is that an issuer who is absent from the market for years finds it harder to return in a crisis. Treasury maintains relationships with investors and regularly tests its capacity to raise funds quickly.

## The contingency funding plan in action

The **contingency funding plan (CFP)** is the playbook for liquidity shortfalls in stress. APS 210 paras 47 to 51 set the rules.

| Requirement | Para |
|---|---|
| Formal plan setting out strategies for addressing shortfalls; policies for a range of stress environments; clear lines of responsibility; clear invocation and escalation procedures | 47 |
| Commensurate with complexity and risk profile; states available contingency funding sources and the amounts that can be derived; escalation and prioritisation procedures; lead time to tap each source; flexible | 48 |
| Integrated with ongoing liquidity analysis and stress test assumptions and results; addresses different time horizons including intraday | 49 |
| For an ADI with retail deposits: must address a retail deposit run, include measures to repay retail depositors as soon as practicable, and must not rely on closing distribution channels | 50 |
| Reviewed and tested at least annually; Board reviews and approves at least annually or more often | 51 |

### What a CFP contains

| Component | Content |
|---|---|
| **Triggers** | EWI levels or events that invoke the plan |
| **Governance** | Crisis committee, decision rights, who may do what, and when the Board is called |
| **Actions menu** | Sell or repo liquid assets; draw on committed lines; stop new lending; raise deposit rates; issue secured debt; use the RBA's standing facilities; as a last step, ELA (Chapter 2) |
| **Amounts and lead times** | How much each source yields and how many hours or days it takes |
| **Communications** | Messages to customers, staff, investors, rating agencies, APRA and the RBA |
| **Operations** | Payments capacity, call centre and digital channel scaling, cash in branches and ATMs |

### The retail run requirement

Para 50 is distinctive. The plan "must not rely upon closing distribution channels to retail depositors" (APS 210 para 50). A bank cannot plan to close branches, switch off online banking or limit ATM access to slow a run. It must plan to pay, and it must seek to ensure "retail depositors wishing to retrieve their deposits may do so as quickly and as conveniently as is practicable in the circumstances, and within the contractual terms and conditions applicable to the relevant deposit products". Practical consequences: sufficient cash in the system, scalable digital and payment capacity, and the ability to settle large outward transfers fast. Chapter 1 explains why the speed of modern runs makes this requirement demanding.

> **Watch out:** Para 51 requires the plan to be tested, not just written. Testing includes simulation exercises with real contacts and real data. A plan that has never been run is an assumption.

## What moves the LCR and the NSFR

The table below shows how common events move Example Bank's two ratios, one event at a time, starting from LCR = 17.0 / 11.55 = 147.2% and NSFR = 79.75 / 58.50 = 136.3%. Each row changes only the item described. Unless stated, the other numbers stay as in the shared example. The treatments follow the Example Bank rates used throughout this guide; the underlying paragraphs are in Chapters 5 and 6. Where a rate is assumed for illustration, the row says so.

| # | Event | LCR effect | NSFR effect | Why |
|---|---|---|---|---|
| 1 | A large corporate non-operational deposit of A$1.0bn arrives and is held as cash | Up: HQLA 18.0; outflows +0.40 (1.0 x 40%) to 13.85; net 11.95; LCR = 18.0 / 11.95 = 150.6% | Up: ASF +0.50 (50%); RSF unchanged (cash 0%); NSFR = 80.25 / 58.50 = 137.2% | Cash adds one-for-one to HQLA, while only 40% of the deposit is assumed to leave |
| 2 | A financial institution places A$1.0bn at call and the cash is held | Down: HQLA 18.0; outflows +1.00; net 12.55; LCR = 18.0 / 12.55 = 143.4% | Unchanged: ASF 0% for financial institution deposits; NSFR 136.3% | 100% of the deposit is assumed to leave in 30 days, so it brings in A$1.0bn of cash but A$1.0bn of outflow |
| 3 | A bond of A$3.0bn that matures in month 2 moves inside 30 days (the 30-day-to-6-month wholesale debt) | Down: outflows +3.00; net 14.55; LCR = 17.0 / 14.55 = 116.8% | Unchanged: ASF 0% for debt under 6 months both before and after | Debt maturing within 30 days is assumed to be not rolled over (100%); NSFR does not distinguish within 6 months |
| 4 | Treasury does a 7-day repo of A$2.0bn government bonds for cash, with the cash held | Broadly unchanged: cash +2.0 counts, bonds -2.0 encumbered so do not count; HQLA stays 17.0; secured funding backed by HQLA1 has a 0% run-off (Att A Table 3) | Unchanged for a short repo: cash is 0% RSF, bonds encumbered for under six months keep their 5% factor (Att C para 23), and short funding from a financial institution earns 0% ASF (Att C para 15(a)) | Swaps one HQLA asset for another; the bank is no safer or riskier on the ratio |
| 5 | Mortgage growth: A$3.0bn of cash is lent as new standard mortgages (what-if 2) | Down: HQLA 14.0; LCR = 14.0 / 11.55 = 121.2% | Down: RSF +1.95 (3.0 x 65%) to 60.45; NSFR = 79.75 / 60.45 = 131.9% | Cash is turned into an asset that requires stable funding and no longer counts as HQLA |
| 6 | Replace A$2.0bn of at-call financial institution deposits with A$2.0bn of retail term deposits over 30 days (what-if 1) | Up: outflows fall by 2.00 to 11.45; net 9.55; LCR = 17.0 / 9.55 = 178.0% | Up: ASF +1.80 (2.0 x 90%) to 81.55; NSFR = 81.55 / 58.50 = 139.4% | Longer-dated, retail funding runs off much less and counts as more stable |
| 7 | A retail term deposit of A$1.0bn enters its final 30 days (it is no longer excluded under Att A para 41, so it takes the less stable retail rate of 10%) | Down slightly: outflows +0.10; net 11.65; LCR = 17.0 / 11.65 = 145.9% | Unchanged: 90% ASF for retail term deposits under one year | Money due back within 30 days may leave, but the bank can see it coming |
| 8 | Customers draw A$1.0bn on committed corporate credit facilities, funded from cash | Down: HQLA 16.0; outflows -0.10 (10% of 1.0 no longer undrawn) to 13.35; net 11.45; LCR = 16.0 / 11.45 = 139.7% | Down: RSF +0.80 (loan 85% less undrawn 5%, i.e. 1.0 x 85% - 1.0 x 5%) to 59.30; NSFR = 79.75 / 59.30 = 134.5% | Cash becomes a long-term loan; the potential outflow reduces but the cash is gone |
| 9 | Treasury buys A$2.0bn of government bonds with A$2.0bn of new 2-year wholesale debt | Up: HQLA 19.0; LCR = 19.0 / 11.55 = 164.5% | Up: ASF +2.00 (100%); RSF +0.10 (5%); NSFR = 81.75 / 58.60 = 139.5% | Raises the buffer using stable funding; costs money (carry) |
| 10 | Bank raises A$2.0bn of 5-year debt and uses it to repay A$2.0bn of debt that was due in 30 days to 6 months | Unchanged: the maturing debt was outside the 30-day window | Up: ASF +2.00 (new 100%; old 0%); NSFR = 81.75 / 58.50 = 139.7% | Lengthening funding improves the NSFR even when the LCR sees no change |
| 11 | Retail customers withdraw A$1.0bn of stable deposits (cash paid out) | Down: HQLA 16.0; outflows -0.05 (5% of 1.0); net 11.50; LCR = 16.0 / 11.50 = 139.1% | Down: ASF -0.95 (95%); NSFR = 78.80 / 58.50 = 134.7% | Cash and a stable funding source both leave |
| 12 | Collateral estimated to be posted on a downgrade rises by A$0.5bn | Down: outflows +0.50; net 12.05; LCR = 17.0 / 12.05 = 141.1% | Unchanged in this simplified view (derivatives ignored) | Downgrade triggers are counted at 100% |
| 13 | Bank lends A$1.0bn cash to another bank for 20 days (new inflow within 30 days) | Up: HQLA 16.0; inflows +1.00 (100%) to 2.90 (cap 10.09, not binding); net 10.55; LCR = 16.0 / 10.55 = 151.7% | Down slightly: RSF +0.15 (15%); NSFR = 79.75 / 58.65 = 136.0% | Quirk: when the LCR is above 100%, swapping HQLA for an equal inflow raises the ratio |
| 14 | Shareholders contribute A$1.0bn of new equity, held as cash | Up: HQLA 18.0; LCR = 18.0 / 11.55 = 155.8% | Up: ASF +1.00 (100%); NSFR = 80.75 / 58.50 = 138.0% | Equity is the most stable funding and has no run-off |
| 15 | Market value of government securities falls 10% (A$12.0bn becomes A$10.8bn) | Down: HQLA 15.8 (HQLA1 counted at market value, Att A para 9); LCR = 15.8 / 11.55 = 136.8% | Slightly up: RSF 5% x 10.8 = 0.54, so RSF 58.44; NSFR = 79.75 / 58.44 = 136.5% | Ignores the loss to equity; only the asset value change is shown |

> **Watch out:** Row 13 shows a known feature of the LCR: pulling cash out of the buffer and lending it for under 30 days can raise the ratio, because the inflow reduces net outflows by the same A$1.0bn that HQLA falls by. When the ratio is above 100%, taking the same amount from top and bottom raises the ratio. That is arithmetic, not a sign of safety: the bank has less usable cash today.

### Reading the table

- **Cash into HQLA** helps the LCR and is neutral or positive for the NSFR (cash has a 0% RSF in Example Bank).
- **Turning cash into loans** hurts both ratios (what-if 2).
- **Longer, more stable funding** helps the NSFR a lot and the LCR where it removes 30-day outflows (what-if 1).
- **Funding from financial institutions at call** is the worst for the LCR (100%) and gives 0% ASF.

## How to read a daily liquidity report or dashboard

A daily liquidity dashboard is a one-page view of the position that Treasury, ALCO and the oversight function use. APS 210 para 40 requires "a reliable management information system that provides the Board, senior management and other appropriate personnel with timely and forward-looking information on the liquidity position". The lines below are typical; Example Bank's values are shown where the shared example provides them.

| # | Line | What it shows | Example Bank |
|---|---|---|---|
| 1 | **HQLA stock** | Unencumbered liquid assets counted, by HQLA1, HQLA2A, HQLA2B, after haircuts and caps | A$17.0bn, all HQLA1 |
| 2 | **Total net cash outflows (30 days)** | Weighted outflows minus capped inflows | A$11.55bn |
| 3 | **LCR (all currencies)** | Line 1 / line 2 | 147.2% |
| 4 | **LCR (AUD)** | Same ratio using Australian dollar items only | Not given in the shared example |
| 5 | **Surplus over 100% and over the internal floor** | HQLA minus net outflows; HQLA minus floor x net outflows | A$5.45bn over 100% |
| 6 | **NSFR** | ASF / RSF | 79.75 / 58.50 = 136.3% |
| 7 | **Weighted outflows by category** | Which funding types drive outflow | Largest: financial institutions A$4.00bn, corporate non-operational A$2.40bn |
| 8 | **Inflow cap utilisation** | Inflows as a share of 75% of outflows (Att A para 30) | 1.90 against a cap of 10.09 |
| 9 | **Encumbrance** | Share of HQLA and total assets pledged | Not given in the shared example |
| 10 | **Maturity ladder** | Net and cumulative gaps by bucket | Negative early, positive long (qualitative) |
| 11 | **Funding concentration** | Top counterparties and products above 1% of balance sheet | Threshold A$1.0bn |
| 12 | **Wholesale maturity profile** | Debt maturing in the next 30, 90, 180 days | A$1.0bn within 30 days |
| 13 | **Intraday liquidity** | Opening balance, peak usage, sources | Not given in the shared example |
| 14 | **EWI status** | Red/amber/green on each indicator | Not given |
| 15 | **Limit utilisation** | Each limit, usage, headroom and breaches (APS 210 para 37) | Not given |
| 16 | **Stress results** | Survival horizon under each scenario | Not given |
| 17 | **Contingency funding capacity** | Amount and lead time of each contingency source | Not given |

### Reading it

1. **Start with the ratios.** Are the LCR and NSFR above their minimum, above the internal floor, and above the day's level before?
2. **Look at the movement.** What changed from yesterday: HQLA, outflows, or both? Use the table above to explain the move.
3. **Check composition.** Is HQLA mostly HQLA1 (flexible) or relying on capped classes? Is it unencumbered?
4. **Check what drives outflows.** Large lines (financial institutions, corporate non-operational) deserve attention.
5. **Check the horizon beyond 30 days.** The ladder and wholesale maturity profile show what the 30-day LCR does not.
6. **Check early warning indicators and limits.** Any amber or red items need an owner and an action.
7. **Check data quality.** Does the total reconcile to the general ledger? Are late feeds flagged? Any manual adjustments?

> **Why it matters for your dashboard:** Each number on the page must trace to source rows (counterparty, product, residual maturity, encumbrance flag, currency). The same attributes decide the run-off rate, the ASF/RSF factor and the concentration group. If a field is wrong during a migration, the LCR moves.

## What can go wrong

- **Optimising the ratio rather than the risk.** Row 13 shows the ratio can be raised by actions that do not make the bank safer.
- **Stale or end-of-day-only data.** Fast runs mean daily may be too slow (Chapter 1).
- **Assuming behavioural stability that fails in stress.** Behavioural models built on calm history can fail.
- **Hidden encumbrance.** Counting pledged assets as buffer.
- **A plan that is untested.** APS 210 para 51 requires testing.
- **Weak independence.** If the oversight function cannot challenge Treasury, para 28 is not met.
- **Currency blind spots.** A strong all-currencies LCR can hide a weak AUD LCR (APS 210 para 55(a)).

## Key points

- Treasury executes liquidity management; the Board approves tolerance and strategy; ALCO reviews the position; an operationally independent oversight function challenges Treasury (APS 210 paras 15 to 19, 28).
- The liquid asset portfolio costs money because liquid assets earn less than loans; banks hold a buffer above 100% in line with their risk tolerance (Att A para 4), and Example Bank's LCR of 147.2% has a surplus of A$5.45bn.
- Contractual cash flows show legal due dates; behavioural cash flows show expected conduct; the maturity ladder's net and cumulative gaps show where funding must be found.
- Funding concentration is monitored by counterparty, product, market, currency and maturity; 1% of the balance sheet is a common significance threshold (a Basel monitoring convention, not an APS 210 rule).
- Stress tests (APS 210 paras 62 to 66) must cover institution-specific and market-wide scenarios, singly and combined, and feed limits and the contingency funding plan.
- Limits (para 37) and early warning indicators (para 39) turn policy into daily monitoring and escalation.
- Funds transfer pricing (para 42) charges business units for the liquidity they use; intraday liquidity (para 41), collateral (para 38) and currency mismatches (para 43) each need active management.
- The three-year funding strategy is reviewed and approved at least annually (paras 44 to 46); the contingency funding plan must be tested at least annually and cannot rely on closing retail distribution channels (paras 50 and 51).
- Common events move the LCR and NSFR in different directions: turning cash into loans hurts both; longer stable funding helps the NSFR; at-call financial institution funding hurts the LCR most.

## Check your understanding

**1. Why can't the independent liquidity oversight function report to the Treasurer?**

**Answer:** APS 210 para 28 requires it to be "operationally independent" with the authority to challenge Treasury. If it reported to the Treasurer it could not challenge Treasury's decisions freely.

**2. Example Bank holds HQLA of A$17.0bn and net cash outflows of A$11.55bn. Management sets an internal floor of 130%. How much HQLA surplus does it have over the floor?**

**Answer:** Required HQLA at 130% = 1.30 x 11.55 = A$15.015bn. Surplus = 17.0 - 15.015 = A$1.985bn, about A$2.0bn. (Compare A$5.45bn over the 100% minimum.)

**3. Explain the difference between a net gap and a cumulative gap in a maturity ladder. In a bucket with inflows of A$3bn and outflows of A$5bn, preceded by a cumulative gap of -A$4bn, what are the net and cumulative gaps?**

**Answer:** The net gap is inflows minus outflows within the bucket; the cumulative gap is the running total of net gaps. Net gap = 3 - 5 = -A$2bn. Cumulative gap = -4 + (-2) = -A$6bn.

**4. Example Bank replaces A$2.0bn of at-call financial institution deposits with A$2.0bn of retail term deposits over 30 days. Recompute the LCR and NSFR.**

**Answer:** Outflows fall by 2.0 x 100% = 2.00, so total outflows are 13.45 - 2.00 = 11.45; net outflows are 11.45 - 1.90 = 9.55; LCR = 17.0 / 9.55 = 178.0%. ASF rises by 2.0 x 90% = 1.80 (financial institution deposits had 0%) to 81.55; NSFR = 81.55 / 58.50 = 139.4%.

**5. Example Bank lends A$3.0bn of its cash as new standard mortgages. Recompute both ratios and say why the LCR falls.**

**Answer:** HQLA = 17.0 - 3.0 = 14.0; LCR = 14.0 / 11.55 = 121.2%. RSF rises by 3.0 x 65% = 1.95 to 60.45; NSFR = 79.75 / 60.45 = 131.9%. The LCR falls because mortgages are not HQLA and the cash has left the buffer; the NSFR falls because the new mortgages need stable funding while the cash needed none.

**6. A bank's retail run contingency plan proposes limiting online transfers and closing branches in a run. Does it satisfy APS 210?**

**Answer:** No. APS 210 para 50 requires that the retail run contingency plan "must not rely upon closing distribution channels to retail depositors" and must aim to let depositors retrieve funds as quickly and conveniently as practicable, within the product terms.

**7. Why is a 1% of balance sheet threshold used for funding concentration, and what is it for Example Bank?**

**Answer:** It is a common convention (from Basel's monitoring tools; not in APS 210) for deciding which counterparties and products are significant enough to monitor, since the loss of one would matter. 1% of A$100.0bn is A$1.0bn.

**8. Which of the following improves the NSFR but leaves the LCR unchanged: (a) holding more cash; (b) replacing A$2.0bn of debt due in 30 days to 6 months with 5-year debt. Show the NSFR.**

**Answer:** (b). The old debt was outside the 30-day window, so the LCR is unchanged. ASF rises by 2.0 x 100% = 2.00 (old debt 0%) to 81.75; NSFR = 81.75 / 58.50 = 139.7%. Holding more cash (a) would raise the LCR if it came from new funding that was not itself assumed to leave.

---

# Chapter 10: Glossary, acronyms and common confusions

This chapter is a reference. Use the glossary to look up a word, the acronym table to expand a short form, and the common confusions section when two terms sound alike. Paragraph references take the form `(APS 210 para N)` for the main body and `(Att A para N)`, `(Att B para N)` and `(Att C para N)` for the attachments. Money is in A$. "Example Bank" is the fictional bank used throughout the guide. Terms in bold are entries; a few entries say "as generally understood" where the point comes from outside APS 210 and is hedged.

## Glossary

**Accrual** (also known as accrued interest, accrual accounting): recording income or expense when it is earned or incurred, not when cash moves. A loan earns interest every day even if the borrower pays monthly, so the bank books an accrued interest receivable in between. Accruals matter for liquidity because accrued interest is not cash.

**Additional Tier 1** (also known as AT1): a layer of regulatory capital that sits below common equity in quality. It is usually a hybrid security that can absorb losses or convert to equity in stress. It is capital, not liquidity. In the NSFR, regulatory capital counts at a 100% ASF factor before regulatory adjustments (Att C para 11(a)).

**ADI** (authorised deposit-taking institution; also known as a deposit-taker): a body authorised under the Banking Act 1959 to take deposits from the public in Australia. Banks, credit unions and building societies are all ADIs. APS 210 applies to all ADIs (APS 210 para 2).

**ALCO** (asset and liability committee; also known as the Asset Liability Committee): the management committee that oversees the balance sheet, funding and liquidity positions and receives liquidity reports. APS 210 refers to the asset/liability committee as a recipient of reports (APS 210 para 19(f)).

**All-currencies LCR** (also known as total-currency LCR): the LCR calculated with every currency pooled together. A locally incorporated LCR ADI must keep both its all-currencies LCR and its AUD LCR at 100% or more; a foreign ADI must keep its all-currencies LCR at 40% or more (APS 210 para 55).

**Amortised cost**: an accounting measurement where a financial asset or liability is carried at its original amount, plus accrued interest, minus repayments, adjusted for fees and for expected credit loss. It ignores day-to-day market price changes. Most bank loans and many deposits are held this way. Compare **fair value**.

**Amortising loan** (also known as a principal-and-interest loan): a loan repaid in regular instalments that include both interest and some principal, so the balance falls over time. For the NSFR, the part of an amortising loan that falls due within one year may be included in the less-than-one-year residual maturity category (Att C para 22).

**APG 210** (Prudential Practice Guide APG 210 Liquidity): APRA's non-binding guidance that explains how APRA expects ADIs to apply APS 210. A practice guide is guidance, not a rule. See **prudential standard**.

**APRA** (Australian Prudential Regulation Authority): the Australian government agency that supervises ADIs, insurers and superannuation funds and makes the prudential standards. It sets the liquidity rules in APS 210, decides whether an ADI is an LCR ADI or MLH ADI (APS 210 paras 52 to 53), and may require higher minimums (APS 210 paras 56, 58, 61).

**APS 210** (Prudential Standard APS 210 Liquidity): APRA's binding liquidity standard for ADIs, made under section 11AF of the Banking Act 1959 (APS 210 para 1). This guide uses the July 2025 version, which commences on 1 July 2025 (APS 210 para 6). It has a main body and three attachments: A (LCR), B (MLH) and C (NSFR).

**ASF** (available stable funding): the part of a bank's capital and liabilities expected to be reliably available over a one-year horizon (Att C para 6). It is the numerator of the NSFR. Each funding category has an ASF factor: 100%, 95%, 90%, 50% or 0% (Att C paras 11 to 15). Example Bank's total ASF is 79.75.

**ASIC** (Australian Securities and Investments Commission): the Australian corporate, markets and consumer-finance conduct regulator. It is separate from APRA, which looks after the safety and soundness of the institution.

**Asset**: something a bank owns or is owed that is expected to bring economic benefit: cash, securities, loans. On a bank's balance sheet a customer's loan is an asset and a customer's deposit is a liability. Example Bank's assets total A$100.0bn.

**Asset-backed commercial paper** (also known as ABCP): short-term debt issued by a vehicle (often a conduit) and backed by a pool of assets such as receivables. In APS 210, maturing ABCP issued by the ADI itself runs off at 100% in the LCR (Att A Table 3).

**Asset-backed security** (also known as ABS): a bond whose payments come from a pool of assets such as car loans or credit cards. The ADI's own maturing asset-backed securities run off at 100% in the LCR (Att A Table 3).

**Associated entity**: a company related to another within the meaning of section 50AAA of the Corporations Act 2001 (APS 210 para 10(a)). It matters because HQLA cannot generally be issued by a financial institution or its associated entities (for example Att A para 9(c)(iv)).

**At-call deposit** (also known as a demand deposit, on-demand deposit): a deposit the customer can withdraw at any time without notice. It is the most run-prone form of funding, so it is treated as maturing within the 30-day LCR window. Retail at-call deposits run off at 5%, 10% or 25% depending on stability (Att A Table 3).

**Australian Government Securities** (also known as AGS, Commonwealth Government Securities, Treasury bonds and Treasury notes): debt issued by the Australian Government. Under Attachment B they are eligible liquid assets as "Commonwealth Government and semi-government securities" (Att B para 2(b)). As generally understood, Australian Government securities are HQLA1 for AUD purposes; confirm against APG 210.

**Authorised NOHC** (authorised non-operating holding company): a holding company, approved by APRA, that sits above an ADI and does not itself carry on banking. If an ADI is a subsidiary of an authorised NOHC, the NOHC must ensure Level 2 requirements are met (APS 210 para 4(b)).

**Balance sheet** (also known as statement of financial position): a statement of what an entity owns (assets), owes (liabilities) and what is left for owners (equity) at one date. Assets equal liabilities plus equity. Example Bank's balance sheet totals A$100.0bn on each side.

**Bank bill** (also known as a bank-accepted bill): a short-term debt instrument that a bank has accepted or endorsed, so the bank is liable to pay it. Bank bills are an eligible liquid asset for MLH (Att B para 2(e)). They are not HQLA in the LCR. Example Bank's loans to other banks are a different thing: they are unsecured placements.

**Bank for International Settlements** (also known as BIS): an international organisation owned by central banks that hosts the Basel Committee. Marketable securities of the BIS can be HQLA1 if they meet the conditions (Att A para 9(c)).

**Banking Act 1959**: the Commonwealth Act that governs banking and ADIs in Australia. APS 210 is made under section 11AF of it (APS 210 para 1), and subsection 11AF(2) lets APRA adjust or exclude requirements (APS 210 para 71, footnote 1).

**Bank run** (also known as a run on the bank): many depositors or funders try to withdraw money at once because they fear the bank will not be able to pay. Because banks lend long and borrow short, even a sound bank cannot pay everyone immediately. APS 210 requires a plan that can handle a retail deposit run (APS 210 para 50).

**Basel Committee** (also known as the Basel Committee on Banking Supervision, BCBS): the international committee of banking supervisors that writes global standards on bank capital and liquidity. It is hosted by the Bank for International Settlements in Basel, Switzerland. APS 210 refers to its global framework for liquidity risk (Att A para 26(b)). APRA adapts, not copies, its standards.

**Basel III**: the set of reforms the Basel Committee developed after the 2007 to 2009 financial crisis, which introduced the LCR and the NSFR as global liquidity standards alongside tougher capital rules. APS 210 is how Australia applies the liquidity part.

**Basis point** (also known as bp, bps): one hundredth of one percentage point, 0.01%. A move from 4.00% to 4.25% is 25 basis points.

**BBSW** (bank bill swap rate): the Australian benchmark short-term interest rate, derived from trading in bank bills and NCDs. It is administered by the Australian Securities Exchange, as generally understood. Many loans and wholesale securities are priced as BBSW plus a margin. Verify current administration details on asx.com.au.

**Behavioural maturity**: the time a cash flow is expected to occur based on how customers actually behave, not the contract. A savings account is contractually at call but behaviourally may stay for years. The LCR uses prescribed run-off rates, which are a regulatory view of behaviour in stress. Compare **contractual maturity**.

**Board**: the ADI's board of directors, ultimately responsible for sound and prudent management of liquidity risk (APS 210 para 15). For a foreign ADI, the senior officer outside Australia fulfils the Board's responsibilities.

**Bond** (also known as a debt security, note): a tradable loan. The issuer receives money now, pays periodic interest (the coupon), and repays the face value on a set date. Banks both issue bonds (as wholesale funding) and hold them (as liquid assets).

**Buffer** (also known as liquidity buffer, cushion): liquid assets held above the regulatory minimum. APS 210 requires an appropriate buffer of HQLA over the LCR requirement in line with the ADI's liquidity risk tolerance (Att A para 4), and a buffer over the NSFR (Att C para 4). Example Bank's HQLA surplus above 100% is 5.45.

**Building society** (also known as a mutual): a member-owned ADI, historically focused on home lending. It is an ADI and therefore subject to APS 210, often as an MLH ADI.

**Buyback**: a bank buying back its own debt before maturity, usually to support the market for it. The LCR assumes outflows for buybacks of domestic Australian debt securities of 10% for short-term and 5% for long-term securities, unless otherwise agreed with APRA (Att A Table 3).

**Carrying value** (also known as book value): the amount at which an item is recorded on the balance sheet. The NSFR applies factors to carrying value, before regulatory deductions, filters or adjustments (Att C para 7(a), footnote 9; Att C para 17(a)). It can differ from market value and face value.

**Cash flow**: money moving into or out of the bank. Liquidity management is projecting cash flows from assets, liabilities and off-balance sheet items over suitable time horizons (APS 210 para 36).

**Cash inflow**: expected money coming in over the stress period, such as loan repayments. In the LCR only contractual inflows from fully performing exposures count (Att A para 54), and total inflows are capped at 75% of outflows (Att A para 30).

**Cash outflow**: expected money going out, such as deposit withdrawals, debt repayments and facility drawdowns. The LCR multiplies balances by run-off rates in Att A Table 3. Example Bank's total outflows are 13.45.

**Cash rate** (also known as the cash rate target, official cash rate): the interest rate on unsecured overnight loans between banks in the money market, which the RBA Board targets as its main monetary policy setting. Verify the current level on rba.gov.au.

**Central bank**: a country's monetary authority, banker to banks and often the lender of last resort. The Reserve Bank of Australia is Australia's. Central bank balances that can be drawn in stress are HQLA1 (Att A para 9(b)).

**Central counterparty** (also known as CCP, clearing house): an entity that stands between the two sides of a trade so that each deals with the CCP, not with each other. CCPs collect initial and variation margin. Under the NSFR, assets posted as initial margin or contributed to a CCP default fund get an 85% RSF factor (Att C para 36(a)).

**Certificate of deposit** (also known as CD, NCD, negotiable certificate of deposit): a tradable receipt for a term deposit, issued by a bank. Certificates of deposit are an eligible liquid asset for MLH (Att B para 2(e)). Unsecured debt issuance running off within 30 days has a 100% run-off rate in the LCR (Att A Table 3).

**CET1** (Common Equity Tier 1): the highest-quality bank capital, mainly ordinary shares and retained earnings. It absorbs losses first. CET1 is part of regulatory capital and receives a 100% ASF factor within regulatory capital (Att C para 11(a)).

**CLF** (Committed Liquidity Facility): an arrangement under which a locally incorporated LCR ADI could pay the RBA a fee for a committed amount of cash against qualifying collateral, counted towards the LCR for Australian dollar needs (Att A paras 13 to 14). Qualifying collateral is assets eligible for repurchase with the RBA under normal market conditions and any other assets nominated by the RBA (Att A para 13). The standard still describes it (Att A paras 13 to 21). APRA announced that ADIs should reduce reliance on the CLF to zero by the end of 2022, and the RBA has reported that CLF allowances were reduced to zero over 2022 (apra.gov.au, rba.gov.au). APRA has said the facility remains available if it needs to be reactivated.

**Collateral**: assets pledged or transferred to secure an obligation. If the borrower defaults, the lender keeps or sells the collateral. Collateral is central to repos, derivatives and secured funding. See **encumbered asset**.

**Collateral swap**: a transaction in which two parties exchange one security for another, often a lower-quality one for a higher-quality one, for a period, usually for a fee. APS 210 requires collateral swaps maturing within 30 days to be included when the HQLA caps are tested (Att A para 7) and lets APRA require a net cash-flow adjustment (Att A para 33).

**Commercial paper** (also known as CP): short-term, unsecured debt issued by companies or banks to raise cash, usually for under a year. Corporate commercial paper can be HQLA2A or HQLA2B if it meets the criteria (Att A paras 10(b), 12(b)).

**Committed facility**: a credit or liquidity facility under which the provider is legally obliged to lend on request up to the limit. The undrawn part is an off-balance sheet exposure and receives LCR drawdown rates: 5% retail and SME, 10% non-financial corporate credit facilities, 30% corporate liquidity facilities, 40% for banks and other ADIs, and 40% credit and 100% liquidity facilities for other financial institutions (Att A Table 3). Other legal entity customers are 100%.

**Common equity**: ordinary shares and retained earnings, the top quality of capital. Exchange-traded common equity shares that meet strict criteria can be HQLA2B with a 50% haircut (Att A para 12(c)). Do not confuse the bank's own equity capital with equity shares it holds as an asset.

**Concentration** (also known as concentration risk): too much funding or exposure depending on one counterparty, product, market, currency or maturity date. APS 210 expects diversity and stability of funding sources (APS 210 para 29(b)) and warns about rising funding concentrations (APS 210 para 33).

**Conduit**: a vehicle that funds assets by issuing short-term paper. Loss of funding on conduits runs off at 100% (Att A Table 3).

**Contingency funding plan** (also known as CFP): a formal plan setting out how the ADI would deal with liquidity shortfalls in stress, with clear invocation and escalation procedures (APS 210 para 47). It must address a retail deposit run and must not rely on closing distribution channels (APS 210 para 50). It must be reviewed and tested at least annually (APS 210 para 51).

**Contingent liability**: a possible obligation that will become real only if an uncertain event happens, such as a guarantee being called. It is usually shown in notes, not on the balance sheet, but it can drain cash in stress.

**Contractual maturity**: the date a contract says the money is due. The LCR counts contractual receivables and funding callable within 30 days (Att A paras 45, 60). Compare **behavioural maturity** and **residual maturity**.

**Cooperative network**: a group of ADIs, such as credit unions, with a central organisation. Deposits placed at the central institution are assumed to stay there for LCR inflows (Att A para 64), and certain intra-network deposits can get a special ASF treatment with APRA approval (Att C footnote 18).

**Council of Financial Regulators** (also known as CFR): the coordinating body of Australia's main financial regulators: the RBA (chair), APRA, ASIC and the Treasury. It is a forum, not a regulator in its own right.

**Counterparty**: the other party to a contract or transaction, such as the depositor, the lender, the borrower or the derivative dealer. APS 210 sets different rates by counterparty type, for example financial institutions versus non-financial corporates.

**Coupon**: the periodic interest payment on a bond, quoted as a percentage of face value. A A$100m bond with a 4% annual coupon pays A$4m a year.

**Covered bond**: a bond issued by a bank and secured on a ring-fenced pool of assets (usually mortgages), with the bank also still liable. Eligible covered bonds not issued by the ADI itself can be HQLA2A if rated at least AA- and meeting other tests (Att A para 10(b)). Maturing covered bonds issued by the ADI run off at 100% (Att A Table 3).

**Credit facility**: a committed arrangement to lend for general funding, including working capital. A general working capital revolving facility must be classed as a credit facility, not a liquidity facility (Att A para 51). Compare **liquidity facility**.

**Credit rating** (also known as rating): an independent opinion of a borrower's or bond's likelihood of repaying, shown as letters such as AAA, AA or BBB. APS 210 uses ratings of a recognised external credit assessment institution (ECAI) for HQLA tests, for example AA- or better for HQLA2A corporate debt (Att A para 10(b)(iii)).

**Credit risk**: the risk a borrower or counterparty fails to repay. It is different from liquidity risk, though a rise in credit risk can trigger a liquidity problem. APS 210 expects boards to understand how credit risk affects liquidity (APS 210 para 20).

**Credit union** (also known as a mutual ADI): a member-owned ADI offering deposits and loans. It is an ADI and subject to APS 210.

**Cross-currency swap**: a derivative in which two parties exchange principal and interest in different currencies. Banks use it to turn foreign currency borrowing into Australian dollars. It creates collateral and refinancing needs.

**Cumulative gap**: the running total of net cash flows (inflows minus outflows) across a maturity ladder's time buckets, from the first bucket onwards. A large negative cumulative gap in the early buckets shows reliance on refinancing. See **maturity ladder**.

**Currency mismatch**: holding assets in one currency and liabilities in another, so that a need in one currency cannot be met easily by liquid assets in another. APS 210 requires an ADI active in several currencies to maintain liquid assets consistent with its needs by currency and to set an acceptable level of mismatches (APS 210 para 43).

**Dealer** (also known as market maker): a firm that quotes buy and sell prices in a security and holds inventory. Issuers with an affiliated dealer or market maker carry an LCR rate set by the ADI unless APRA determines the rate (Att A Table 3).

**Default**: failure to pay what is due when it is due. LCR inflows count only from fully performing exposures with no reason to expect default within 30 days (Att A para 54). Defaulted securities get a 100% RSF factor (Att C para 37(c)).

**Deposit**: money a customer places with a bank, which the bank must repay. It is the customer's asset and the bank's liability. Example Bank's customer deposits are A$65.0bn.

**Deposit insurance** (also known as deposit guarantee): a government scheme that repays depositors up to a limit if an ADI fails. In Australia this is the **Financial Claims Scheme**. Run-off rates are lower for balances fully covered by deposit insurance, for example 5% for insured operational deposits against 25% for those not fully covered (Att A Table 3).

**Derivative**: a contract whose value depends on something else, such as an interest rate, currency or share price. Examples are swaps, forwards and options. Derivatives create liquidity needs through margin calls and downgrade triggers. In the LCR, derivative cash flows are netted by counterparty only where a valid master netting agreement exists (Att A Table 3, footnote 5).

**Dividend**: a payment of profit to shareholders. It is a cash outflow, but not a contractual liability until declared.

**Downgrade trigger** (also known as rating trigger): a contract clause that requires the bank to post more collateral or repay early if its credit rating falls. The LCR includes 100% of collateral that would need to be posted on a 3-notch downgrade of the ADI (Att A Table 3). Example Bank: A$0.2bn at 100% = 0.20.

**Duration**: a measure, in years, of how sensitive a bond's price is to changes in yield. A bond with duration 4 loses roughly 4% of its price if yields rise by one percentage point (approximation).

**Early warning indicator** (also known as EWI): a monitored measure that signals rising liquidity risk before a breach, such as widening funding spreads or falling deposits. APS 210 requires a set of them to aid daily liquidity risk management and to support escalation of negative trends (APS 210 para 39).

**ECAI** (external credit assessment institution; also known as rating agency): a recognised body that assigns credit ratings. APS 210 refers to ratings from a recognised ECAI to test HQLA2A and HQLA2B eligibility (Att A paras 10(b)(iii), 12). Where an asset has multiple assessments, the method in APS 112 decides which applies (Att A footnote 2).

**Encumbered asset**: an asset pledged or otherwise committed so that it is not free to be sold or repoed. Encumbered assets do not count as HQLA (APS 210 para 55; Att A para 22(b)). Under the NSFR, an asset encumbered for one year or more gets 100% RSF (Att C para 23). See **unencumbered**.

**Equity** (also known as shareholders' equity, net assets): what is left after liabilities are subtracted from assets; the owners' stake. Regulatory capital receives a 100% ASF factor (Att C para 11(a)). Example Bank's equity is A$8.0bn, 8.0% of total assets.

**Exceptional Liquidity Assistance** (also known as ELA): emergency liquidity the RBA may provide to an ADI under severe liquidity stress. The ADI must first notify APRA immediately and must be able to supply the information requested (APS 210 para 70). It is a last resort, not a planning assumption.

**Exchange Settlement Account** (also known as ESA): an account held at the RBA by banks and other approved institutions, used to settle payments between them. As generally understood, ESA balances are the main "balances at the RBA" in Example Bank's A$5.0bn of cash and RBA balances. Verify at rba.gov.au.

**Expected credit loss** (also known as ECL): an accounting estimate of the credit losses a bank expects on its loans and other assets, recognised as a provision. Under Australian accounting standards (AASB 9, as generally understood) it is forward-looking. It reduces the carrying value of loans but is not a cash flow.

**Face value** (also known as par value, nominal value, principal): the amount a bond or note promises to repay at maturity. It differs from market value, which changes daily, and from carrying value.

**Fair value**: the price that would be received to sell an asset or paid to transfer a liability in an orderly transaction between market participants at the measurement date. Securities held at fair value change in carrying value with market prices.

**Financial Claims Scheme** (also known as FCS): the Australian Government scheme that protects deposits with an ADI that fails, up to A$250,000 per account holder per ADI (as generally understood; verify on fcs.gov.au or apra.gov.au). APS 210 uses the scheme to define stable deposits (Att A para 37), and the scorecard uses AUD 250,000 as the equivalent guarantee limit (Att A para 40).

**Financial institution**: for APS 210, includes a money market corporation, finance company, friendly society and the trustee of a superannuation or pension fund, public unit trust or mutual fund, or cash management trust (APS 210 para 10(b)). Funding from financial institutions is treated harshly: 100% run-off for most non-operational deposits (Att A Table 3).

**Fixed-term deposit** (also known as term deposit, TD): a deposit held for an agreed period at an agreed rate. In the LCR, term deposits with a residual maturity or notice period over 30 days are excluded from outflows if the depositor has no legal right to withdraw or faces a significant penalty materially greater than the loss of interest (Att A para 41). If the ADI lets depositors out anyway, the whole category is treated as demand deposits (Att A para 42), except for hardship cases under a defined policy (Att A para 43).

**Foreign ADI** (also known as a foreign bank branch): the Australian branch of an overseas bank authorised as an ADI. It is an LCR ADI unless APRA decides it is an MLH ADI (APS 210 para 53), and its minimum LCR is 40% on an all-currencies basis (APS 210 para 55(b)). It is a branch, not a separately capitalised subsidiary.

**Foreign exchange swap** (also known as FX swap): two linked trades that exchange one currency for another now and reverse the exchange on a later date. Cash flows from FX derivatives that fully exchange principal on a simultaneous basis can be reflected net (Att A Table 3, footnote 5).

**Forward**: a contract to buy or sell an asset or currency at a fixed price on a future date.

**Funding**: the sources a bank uses to pay for its assets: deposits, wholesale debt and equity. APS 210 requires activities to be funded with stable sources on an ongoing basis (APS 210 para 13).

**Funding concentration** (also known as concentration of funding): the share of funding that comes from one counterparty, product, market, currency or maturity. High concentration means one problem can cut off a large part of funding.

**Funding liquidity risk**: the risk that an ADI may not be able to meet its financial obligations as they fall due (APS 210 para 20). Compare **market liquidity risk**.

**Funding strategy**: the documented plan for how the ADI will fund itself. A three-year funding strategy must be developed and provided to APRA on request (APS 210 para 44(a)), and reviewed and approved by the Board at least annually (APS 210 paras 45 to 46).

**Funds transfer pricing** (also known as FTP): an internal charging system in which Treasury charges business units for the funding and liquidity they use and credits them for what they provide. It supports the requirement to allocate liquidity costs and benefits (APS 210 para 42).

**General collateral** (also known as GC): securities of a broad class, such as government bonds, that are accepted in a repo without being a specific named security. Repo against general collateral is the usual form of secured funding.

**Goodwill**: an intangible asset that arises when one company buys another for more than the fair value of its net identifiable assets. It cannot be sold for cash, so it gives no liquidity. Items deducted from regulatory capital get a 100% RSF factor (Att C para 37(c)).

**Guarantee**: a promise by the bank to pay if a customer fails to meet an obligation. It is an off-balance sheet contingent liability. In the LCR, guarantees and letters of credit other than trade finance run off at 50% of the average of actual monthly net outflows in a recent 12-month period (Att A Table 3).

**Haircut**: a percentage deducted from the market value of an asset to reflect the risk its price falls. In the LCR, HQLA1 has no haircut (Att A para 9), HQLA2A 15% (Att A para 10), HQLA2B eligible RMBS 25% and HQLA2B corporate debt and equities 50% (Att A para 12). Example: A$100m of HQLA2A counts as A$85m. In a repo, a haircut means the lender advances less than the collateral is worth.

**Hedge fund**: a pooled investment vehicle that may use leverage and short selling. Under APS 210, any facility provided to a hedge fund, money market fund or special purpose funding vehicle is treated entirely as a liquidity facility to a financial institution (Att A para 52).

**High-quality liquid assets** (also known as HQLA): assets that can be turned into cash quickly and reliably, with little loss of value, even in stress. The LCR numerator is the stock of HQLA (Att A para 2). To count, the asset must be unencumbered and meet the operational requirements (Att A paras 22 to 23). Example Bank's HQLA is 17.0.

**HQLA1** (also known as Level 1 assets): the highest-quality HQLA, with no haircut and no cap (Att A para 9). It includes notes and coin, drawable central bank balances and qualifying sovereign, central bank, PSE and MDB securities. As generally understood, for AUD this means notes and coin, balances at the RBA, and Australian Government and semi-government securities; confirm with APG 210.

**HQLA2A**: HQLA with a 15% haircut, including qualifying 20%-risk-weight government-type securities and corporate debt and covered bonds rated at least AA- (Att A para 10). APRA or the relevant regulator must have recognised the asset. As generally understood, APRA has not recognised any AUD assets as HQLA2; verify with APG 210.

**HQLA2B**: lower-quality HQLA: eligible RMBS at a 25% haircut, corporate debt rated A+ to BBB- at 50%, and eligible common equities at 50% (Att A para 12). HQLA2B may not exceed 15% of total HQLA (Att A para 6).

**Hybrid** (also known as hybrid security): an instrument with features of both debt and equity, such as a bond that pays interest but can convert to shares or be written off in stress. Bank hybrids usually count as Additional Tier 1 capital.

**Idiosyncratic stress** (also known as name-specific stress, institution-specific stress): a stress that hits one bank because of its own problems, such as a loss of confidence, while markets as a whole are fine. APS 210 requires stress tests for institution-specific and market-wide scenarios, singly and combined (APS 210 para 62).

**Inflow cap**: the rule that LCR cash inflows counted cannot exceed 75% of total cash outflows (Att A para 30). Example: outflows 100 and inflows 90; inflows counted are 75; net outflows are 25, not 10.

**Initial margin**: collateral posted at the start of a derivative or cleared trade to cover possible future losses if the counterparty defaults. Under the NSFR, assets posted as initial margin get an 85% RSF factor (Att C para 36(a)). Compare **variation margin**.

**Insolvency**: being unable to pay debts as they fall due, or having liabilities that exceed assets. It is a solvency failure, which differs from a temporary liquidity shortage. The word appears in the definition of unsecured wholesale funding (Att A para 44).

**Interbank** (also known as interbank market, money market): lending and borrowing between banks, mostly short-term. Maturing placements with banks are inflows at 100% in the LCR (Att A para 62), and money borrowed from financial institutions runs off at 100% (Att A Table 3).

**Interdependent assets and liabilities**: an asset and a liability that are contractually linked so the liability cannot fall due while the asset remains, the asset's principal flows can only repay the liability, and the liability cannot fund other assets (Att C para 38). APRA decides only in exceptional circumstances, case by case (Att C para 39), and may then set the RSF and ASF factors to zero if four criteria are met (Att C para 40).

**Interest income**: what a bank earns on loans and securities. Net interest income is interest income minus interest expense.

**Interest rate risk**: the risk that changes in interest rates reduce earnings or value. It is separate from liquidity risk, though rate moves can affect deposit behaviour and funding costs.

**Intermediated deposit** (also known as brokered deposit, platform deposit): money a person places with an intermediary, such as a platform, which places it with the ADI. It is treated as a financial institution deposit unless four conditions on legal rights, exercise of rights, disclosure and investment discretion are met (Att A para 35).

**Intraday liquidity**: liquidity needed during the business day to make payments and settle before incoming payments arrive. APS 210 requires active management of intraday liquidity under normal and stressed conditions (APS 210 para 41), and the contingency funding plan must address intraday horizons (APS 210 para 49).

**Irrevocable commitment**: a commitment the bank cannot withdraw, such as an approved loan that must be funded if the customer asks. For MLH, liabilities are total on-balance sheet liabilities plus irrevocable commitments (Att B para 1).

**LCR** (liquidity coverage ratio): stock of HQLA divided by total net cash outflows over the next 30 calendar days (Att A para 3). It is a 30-day survival test under severe stress. Minimum 100% for locally incorporated ADIs (AUD and all-currencies) and 40% for foreign ADIs (APS 210 para 55). Example Bank: 17.0 / 11.55 = 147.2%.

**LCR ADI**: an ADI subject to the liquidity coverage ratio, as classified by APRA (APS 210 para 52). A foreign ADI is an LCR ADI unless APRA decides otherwise (APS 210 para 53). A locally incorporated LCR ADI must also meet the NSFR (APS 210 para 59).

**Lender of last resort**: the central bank acting as the final source of emergency funding when no one else will lend. In Australia, the RBA's Exceptional Liquidity Assistance plays this role (APS 210 para 70).

**Less stable deposit**: the portion of retail deposits that does not meet the stable-deposit test (Att A para 38). It is scored on a scorecard (Att A para 40): score 0 to 2 gives a 10% run-off and 3 or more gives 25% (Att A Table 2). Under the NSFR, less stable retail and SME deposits under one year get 90% ASF (Att C para 13(a)).

**Letter of credit** (also known as LC): a bank's written promise to pay a seller on behalf of a buyer when documents are presented. Trade-related letters of credit are trade finance. Letters of credit not related to trade finance run off at 50% of the average monthly net outflows (Att A Table 3).

**Level 1**: the ADI itself, on a stand-alone basis, as opposed to its consolidated group (APS 210 para 3(a)). The LCR must be met on both Level 1 and Level 2 (Att A para 26).

**Level 2**: the consolidated group of which the ADI is a member (APS 210 para 3(b)). Level 2 reflects restrictions on moving liquidity across borders and legal entities (Att A paras 24, 29). Do not confuse it with HQLA2 ("Level 2 assets" in Basel language).

**Leverage ratio**: a capital measure: Tier 1 capital divided by total exposure, without risk weights. It is not a liquidity measure. The NSFR borrows its derivative netting conditions from the Basel III leverage ratio framework (Att C para 9).

**Liability**: an amount the bank owes to others, such as deposits and bonds. Example Bank's liabilities total A$92.0bn, excluding equity.

**Liquid asset**: an asset that can be turned into cash quickly at little cost or loss. Not every liquid asset is HQLA, and for MLH the list of liquid assets is different (Att B para 2).

**Liquidity**: the ability to meet obligations as they fall due. APS 210 requires an ADI at all times to maintain sufficient liquidity to meet its obligations as they fall due (APS 210 para 12). Compare **solvency**.

**Liquidity facility**: a committed, undrawn back-up facility that would be used to refinance a customer's debt when the customer cannot roll it over in markets. Only the customer's debt maturing within 30 days that the facility backstops counts as a liquidity facility; the rest is a credit facility (Att A para 51). Liquidity facilities to non-financial corporates run off at 30%, and to other financial institutions at 100% (Att A Table 3).

**Liquidity gap**: the net difference between expected inflows and outflows in a time bucket. See **maturity ladder** and **cumulative gap**.

**Liquidity risk**: the risk that an ADI cannot meet payments when due or cannot fund assets without unacceptable cost. It has two linked parts, funding liquidity risk and market liquidity risk (APS 210 para 20).

**Liquidity risk tolerance**: the level of liquidity risk the ADI is willing to assume, documented, approved by the Board, reviewed at least annually, and stating the trade-off between risks and profits (APS 210 paras 16(a), 21, 22, 24).

**Loan-to-deposit ratio** (also known as LDR): loans divided by deposits. Example Bank: 73.0 / 65.0 = 112.3%. A figure above 100% means loans are partly funded by something other than customer deposits.

**Loan-to-valuation ratio** (also known as LVR): a loan balance divided by the value of the property securing it. A standard residential loan to a natural person with an LVR of 80% or below and residual maturity of one year or more attracts a 65% RSF factor (Att C para 35(a)).

**Local operational capacity** (also known as LOC): a foreign ADI's ability to liquidate assets and make or receive payments in Australia without help from staff outside Australia. It must be assessed at least annually, including a scenario of at least three business days (APS 210 paras 67 to 68).

**Margin call**: a demand from a counterparty or clearing house to post more collateral, usually because the value of a derivative or secured position has moved against you. Margin calls are sudden cash needs. The LCR covers collateral outflows from market valuation changes on derivatives and other transactions at 100% of the largest absolute net 30-day collateral flow realised in the past 24 months (Att A Table 3).

**Margin lending**: lending to a customer to buy shares or managed funds, secured by those investments. If the securities fall in value, the lender issues a margin call. In the LCR, maturing collateralised loans to customers for leveraged trading are modelled with a 50% inflow against non-HQLA1 or non-HQLA2 collateral (Att A para 55).

**Market liquidity risk**: the risk that liquidity in financial markets, such as the market for debt securities, may reduce significantly (APS 210 para 20). In that case an asset cannot be sold or repoed quickly without a large price fall. Compare **funding liquidity risk**.

**Market value** (also known as market price): the price at which an asset could be sold now in the market. HQLA is included at market value, less any haircut (Att A paras 9, 10, 12); MLH liquid assets are also included at market value (Att B para 2).

**Mark-to-market** (also known as marking to market, MTM): revaluing a position to today's market price. A derivative with a positive mark-to-market is an asset to the bank; a negative one is a liability. The NSFR uses replacement cost obtained by marking to market (Att C paras 9, 27).

**Master netting agreement** (also known as netting agreement, ISDA master agreement in many cases): a legal agreement under which all derivative trades between two parties can be added up and offset on default, leaving one net amount. In the LCR, derivative flows are netted by counterparty only where a valid master netting agreement exists (Att A Table 3, footnote 5). The NSFR uses net replacement cost where an eligible bilateral netting contract is in place (Att C para 9).

**Maturity**: the date on which a financial instrument is due to be repaid, or the time left until then. See **contractual maturity**, **residual maturity** and **tenor**.

**Maturity ladder** (also known as liquidity gap report, maturity mismatch report, funding gap report): a table that places expected cash inflows and outflows into time buckets (overnight, up to a week, up to a month, and so on), with a net gap and a cumulative gap for each. It shows when the bank is exposed to funding needs.

**Maturity mismatch**: the difference between when assets pay in and when liabilities fall due. Funding 30-year mortgages with 1-year deposits is a large maturity mismatch.

**Maturity transformation**: using short-term funding, such as at-call deposits, to make longer-term loans. It is the core activity of a bank and the source of its liquidity risk. See **bank run**.

**MDB** (multilateral development bank): an international development lender owned by several governments, such as the World Bank. Qualifying MDB securities can be HQLA1 or HQLA2A (Att A paras 9(c), 10(a)), and funding from MDBs under one year gets a 50% ASF factor (Att C para 14(e)).

**MLH** (minimum liquidity holdings): the simpler liquidity regime for smaller ADIs. An MLH ADI must hold at least 9% of its liabilities in specified liquid assets (APS 210 para 57; Att B). APRA may require a higher holding (APS 210 para 58).

**MLH ADI**: an ADI classified by APRA as subject to the minimum liquidity holdings approach instead of the LCR (APS 210 para 52). A foreign ADI is an MLH ADI only if APRA so determines (APS 210 para 53).

**Monetise**: turn an asset into cash, by selling it or by borrowing against it (repo). The function managing liquidity must have the authority, legal and operational capability to monetise any asset in the HQLA stock (Att A para 22(b)).

**Money market fund**: a pooled fund that invests in short-term, low-risk debt. APS 210 treats facilities to money market funds as liquidity facilities to financial institutions in their entirety (Att A para 52), and the trustee of a public unit trust or cash management trust is a financial institution (APS 210 para 10(b)).

**Mortgage**: a loan secured on property. A residential mortgage is the largest asset class for most Australian banks. Standard residential mortgages with residual maturity of one year or more and LVR of 80% or below attract a 65% RSF factor (Att C para 35(a)). Example Bank: A$50.0bn x 65% = 32.50.

**Natural person**: an individual human being, as distinct from a company or trust. Retail deposits are deposits from natural persons (Att A para 34).

**Net cash outflow** (also known as total net cash outflows): expected cash outflows minus the lesser of expected inflows and 75% of outflows, over the next 30 calendar days (Att A para 30). It is the LCR denominator. Example Bank: 13.45 - 1.90 = 11.55.

**Net interest margin** (also known as NIM): net interest income divided by average interest-earning assets. It shows the spread a bank earns between lending and funding. Holding more low-yield liquid assets reduces it.

**Net replacement cost**: the replacement cost of a set of derivative contracts after netting under an eligible netting contract (Att C paras 9, 27).

**Netting**: offsetting amounts owed in each direction so only the difference is paid or counted. See **master netting agreement**. Items cannot be double counted in the LCR (Att A para 31).

**Non-financial corporate** (also known as corporate, non-financial company): a company that is not a financial institution, such as a manufacturer or retailer. Its non-operational deposits run off at 20% if fully insured and 40% if not (Att A Table 3); its undrawn credit facilities at 10% and liquidity facilities at 30%.

**Non-performing loan** (also known as NPL, impaired loan): a loan where the borrower has stopped paying or is not expected to. Whether a loan is performing is determined by reference to APS 220 (Att C footnote 27). Non-performing loans get a 100% RSF factor (Att C para 37(c)).

**Notch**: one step on a credit rating scale, for example from AA to AA-. The LCR assumes collateral calls on a 3-notch downgrade of the ADI (Att A Table 3).

**Notes and coin**: physical currency held by the bank in vaults and ATMs. It is HQLA1 (Att A para 9(a)) and receives a 0% RSF factor if immediately available to meet obligations (Att C para 29(a)).

**Notional** (also known as notional amount, notional principal): the face amount used to calculate payments on a derivative. It is not the amount at risk, which is usually much smaller. Liquidity rules use replacement cost, not notional (Att C paras 9, 27).

**NSFR** (net stable funding ratio): available stable funding divided by required stable funding (Att C para 3), a one-year structural funding test (Att C para 1). A locally incorporated LCR ADI must keep it at 100% or more at all times (APS 210 para 60). Example Bank: 79.75 / 58.50 = 136.3%.

**Off-balance sheet** (also known as OBS): items that can create cash needs but are not (or not fully) on the balance sheet, such as undrawn facilities, guarantees and letters of credit. The LCR has drawdown rates for them (Att A Table 3) and the NSFR has RSF factors (Att C paras 41 to 42).

**Offset account**: a transaction account linked to a home loan, whose balance reduces the interest charged on the loan. It is a deposit for the bank.

**Open market operations** (also known as OMO): the RBA's daily buying, selling and repoing of securities to manage the supply of cash in the banking system and keep the cash rate on target (as generally understood; verify on rba.gov.au). Securities eligible for repurchase with the RBA are used in the MLH regime (Att B para 3).

**Operational deposit**: a deposit a customer keeps with the ADI to use its clearing, custody or cash management services, where the customer has a substantive dependency on the ADI (Att A paras 47 to 48). Qualifying deposits are by-products of the services, not offered mainly for interest, and held in designated accounts (Att A para 49). Excess balances do not qualify (Att A para 50). Run-off is 5% if fully insured and 25% if not (Att A Table 3). Example Bank: A$4.0bn x 25% = 1.00.

**Operational requirements (for HQLA)**: tests that an asset must pass to count in the HQLA stock: available to convert into cash at any time; unencumbered and under the control of the function managing liquidity (typically the treasurer); control evidenced by a separate pool or demonstrable ability to monetise; not pledged or designated to cover operating costs (Att A paras 22 to 23).

**Option**: a contract giving the holder the right, but not the obligation, to buy or sell at a set price. Funding with investor options exercisable within 30 days is treated as callable within the LCR window (Att A para 45).

**Original maturity**: the time between when a contract starts and when it ends. Liquidity rules look at residual maturity instead.

**Originator**: the entity that creates the loans or assets placed into a securitisation. A securitisation's originator cannot issue the RMBS it counts as HQLA2B (Att A para 12(a)(i)). Under APS 210, an originating ADI that meets the APS 120 conditions may exclude the securitisation vehicle's assets and liabilities from MLH and NSFR, but must include the vehicle's cash flows in its LCR (APS 210 para 5).

**Overdraft**: a facility allowing a customer to draw more than the balance in a transaction account, up to a limit. The undrawn part is a credit facility. Whether it is committed or revocable decides its LCR rate.

**Overnight** (also known as O/N): maturing in one business day. Overnight borrowing between banks sets the cash rate.

**Performing loan**: a loan whose borrower is meeting its repayments. Only fully performing exposures give LCR inflows (Att A para 54), and performing loans get lower RSF factors than non-performing ones (Att C para 36(b)).

**Pillar 3** (also known as Pillar 3 disclosure): the part of the Basel framework requiring banks to publish standardised risk information, including capital and liquidity. In Australia APRA's standard APS 330 covers public disclosure (as generally understood; verify on apra.gov.au). Chapter 3 shows how to read the LCR and NSFR disclosure tables.

**Pledge**: handing over an asset to a lender as security. Pledged assets are encumbered. Assets must not be pledged to secure, collateralise or credit enhance any transaction to count as HQLA (Att A para 23).

**Principal**: the amount lent or borrowed, separate from interest. In an amortising loan each payment includes some principal.

**Provision** (also known as allowance for expected credit losses, impairment provision): an accounting charge against profit that reduces the carrying value of loans to reflect expected credit losses. Provisions are non-cash. Some accounting provisions, such as for employee benefits, are liabilities.

**Prudential practice guide** (also known as PPG, APG): see **APG 210**. Non-binding APRA guidance on prudent practice.

**Prudential standard** (also known as APS): a binding rule made by APRA. Standards for ADIs are numbered APS; cross-industry ones are numbered CPS. APS 210 is made under section 11AF of the Banking Act (APS 210 para 1). A prudential practice guide (APG) is non-binding guidance on how to comply.

**PSE** (public sector entity): a government-owned or government-linked body, such as a state authority. Qualifying PSE securities can be HQLA1 or HQLA2A (Att A paras 9(c), 10(a)), and funding with a residual maturity under one year from PSEs gets a 50% ASF factor (Att C para 14(e)). Non-operational deposits from PSEs run off at 20% or 40% depending on insurance cover (Att A Table 3).

**Public unit trust** (also known as managed fund): a pooled investment. Its trustee is a financial institution under APS 210 (APS 210 para 10(b)).

**RBA** (Reserve Bank of Australia): Australia's central bank. It sets the cash rate target, runs the payments system, provides the Exchange Settlement Accounts and may give Exceptional Liquidity Assistance (APS 210 para 70).

**Recognised by APRA (HQLA2)**: HQLA2A and HQLA2B assets only count if recognised by APRA or the relevant prudential regulator in the jurisdiction where the liquidity risk is taken (Att A paras 10, 12).

**Regulatory capital**: capital recognised under APS 111 for meeting capital requirements: Tier 1 and Tier 2. It receives a 100% ASF factor before regulatory adjustments, excluding Tier 2 with under one year to maturity (Att C para 11(a)).

**Rehypothecation** (also known as re-use): the receiver of collateral pledging or lending it onward to a third party. Assets received in reverse repo that have not been rehypothecated and are legally and contractually available may be part of HQLA (Att A para 23). Re-used collateral tied up for 30 days or longer to cover short positions means a zero inflow on the maturing reverse repo (Att A para 56).

**Replacement cost**: what it would cost to replace a derivative contract if the counterparty defaulted, the mark-to-market value of a contract with a positive value to you. The NSFR uses replacement cost for derivative assets and negative replacement cost for derivative liabilities (Att C paras 9, 27), netted if an eligible bilateral netting contract applies.

**Repo** (also known as repurchase agreement, sale and repurchase agreement): a sale of securities for cash with a promise to buy them back later at a higher price. Economically it is a secured loan. Example: sell A$100m of bonds for A$98m cash and buy them back in 7 days for A$98.05m. Funding obtained this way is secured funding; its LCR run-off depends on the collateral (Att A Table 3).

**Reserve requirement**: a rule requiring banks to hold a portion of deposits at the central bank. Att C footnote 25 refers to such requirements in other jurisdictions; central bank reserves get a 0% RSF factor (Att C para 29(b)).

**Residual maturity** (also known as remaining maturity): the time left until a contract is due. The LCR and NSFR use it for deposits, debt and loans (for example Att A para 41; Att C paras 12 to 14, 18). Compare **original maturity** under Common confusions.

**Retail deposit**: a deposit placed by a natural person. Deposits from legal entities, sole proprietorships or partnerships are wholesale (Att A para 34). Retail deposits are split into stable and less stable portions (Att A para 36). Example Bank's retail deposits: stable A$25.0bn, less stable A$15.0bn, term A$10.0bn.

**Retained earnings**: profits kept in the bank instead of being paid out as dividends. They form part of equity and common equity capital. They are an accounting balance, not a pot of cash.

**Reverse repo** (also known as reverse repurchase agreement): the other side of a repo. The bank buys securities, lends cash, and agrees to sell the securities back. Maturing reverse repos secured by HQLA1 are assumed to roll over with zero inflow (Att A para 55). Table 4 sets inflow rates for other collateral (Att A Table 4).

**Revocable facility**: a credit or liquidity facility the provider can cancel. Revocable credit and liquidity facilities have a 5% LCR rate (Att A Table 3). Under the NSFR, irrevocable and conditionally revocable facilities get a 5% RSF factor (Att C Table 1); unconditionally revocable facilities get 1% (Att C Table 1).

**Risk appetite** (also known as risk tolerance): the amount and type of risk an organisation accepts to pursue its objectives. APS 210 calls the liquidity version the liquidity risk tolerance (APS 210 para 21).

**Risk weight**: a percentage assigned to an asset class to reflect credit riskiness when measuring capital requirements. APS 210 uses risk weights from APS 112 to identify HQLA: 0% for HQLA1 sovereign-type securities (Att A para 9(c)(i)) and 20% for HQLA2A (Att A para 10(a)(i)). Other loans qualify for 65% RSF if their risk weight is 35% or lower (Att C para 35(b)).

**RMBS** (residential mortgage-backed securities): bonds backed by a pool of home loans. Eligible RMBS can be HQLA2B with a 25% haircut if rated AA or higher, with at most 80% average LVR at issuance, not issued or originated by the ADI, and meeting other criteria (Att A para 12(a)).

**Rollover risk** (also known as refinancing risk): the risk that when debt matures, the bank cannot replace it at all or only at much higher cost. It is the main risk in short-term wholesale funding.

**RSF** (required stable funding): the amount of stable funding an ADI is required to hold, based on the liquidity and residual maturities of its assets and off-balance sheet exposures (Att C para 16). It is the denominator of the NSFR. Factors range from 0% to 100% (Att C paras 29 to 37). Example Bank's RSF is 58.50.

**Run-off rate**: the percentage of a liability or commitment expected to leave or be drawn within the 30-day stress. The LCR multiplies each balance by its rate (Att A para 30; Table 3). Example: A$25.0bn stable retail x 5% = A$1.25bn.

**Scorecard**: the points table APS 210 uses to split less stable retail deposits into a 10% or 25% run-off. Each balance is scored on four criteria: balance above the government guarantee limit (or A$250,000 equivalent), online account, no established customer relationship, and heavily rate-driven (Att A para 40, Table 1). Score 0 to 2 gives 10% and 3 or more gives 25% (Att A Table 2). The points are 2 for a balance above the limit, 2 for an online account, 1 for no established relationship and 1 for heavily rate-driven (Att A Table 1).

**Secured funding** (also known as collateralised funding): borrowing backed by specific assets that the lender can keep or sell if the borrower defaults, such as repo or covered bonds. Better collateral gives a lower LCR run-off: 0% for HQLA1, 15% for HQLA2A, and 100% for other collateral (Att A Table 3). Other secured funding from domestic sovereigns, PSEs or MDBs is 25%, funding backed by HQLA2B RMBS is 25%, and funding backed by other HQLA2B is 50% (Att A Table 3).

**Securities financing transaction** (also known as SFT): a transaction that lends or borrows securities or cash against securities: repo, reverse repo, securities lending and borrowing, and collateral swaps. Under the NSFR, securities borrowed where the ADI does not keep beneficial ownership are excluded from assets (Att C para 25), and SFTs with a single counterparty may be netted if conditions are met (Att C para 26).

**Securities lending**: lending a security to another party for a fee, usually against collateral, which the lender can return at the end. Securities lent where the ADI retains beneficial ownership are included in assets for the NSFR (Att C para 25).

**Securitisation**: packaging loans (such as mortgages) into a pool, transferring them to a special purpose vehicle, and funding the vehicle by selling securities backed by the pool. Banks use it to raise funding and, sometimes, free up capital. APS 210 allows MLH and NSFR to exclude the vehicle where APS 120 operational requirements are met, but the LCR must include its cash flows (APS 210 para 5).

**Self-securitisation** (also known as internal securitisation): a securitisation in which the bank itself holds the securities it creates, usually so that they can be used as repo collateral with the RBA. They could be CLF collateral (Att C para 32(b)), but RMBS issued by the ADI itself cannot be HQLA2B (Att A para 12(a)(i)).

**Semi-government securities** (also known as semis, state government bonds): bonds issued by Australian state and territory government borrowing authorities. They are eligible for MLH (Att B para 2(b)). As generally understood, they count as HQLA1 for AUD; confirm with APG 210.

**Senior debt** (also known as senior unsecured debt): debt that ranks ahead of subordinated debt and equity if the issuer fails. Most bank wholesale bonds are senior. Maturing unsecured debt issuance within 30 days runs off at 100% (Att A Table 3).

**Senior management**: the executives responsible for running the ADI. APS 210 sets their duties for liquidity, including strategy, controls and reporting (APS 210 paras 19 to 20).

**Settlement**: the final transfer of money or securities that completes a trade or payment. In Australia, interbank payments settle across banks' Exchange Settlement Accounts at the RBA (as generally understood). Operational deposits support customers' access to payment and settlement systems (Att A para 47). Trade date receivables and payables expected to settle in the standard cycle get 0% factors in the NSFR (Att C paras 15(d), 29(d)).

**Short position**: an obligation to deliver a security the bank has sold but does not own, created by borrowing the security or by selling it before it is bought. Liabilities without stated maturity, including short positions, get a 0% ASF factor (Att C para 15(b)). Collateral re-used to cover short positions affects LCR inflows (Att A para 56).

**SME** (small and medium enterprise): a business customer small enough to be managed like a retail customer. For the LCR, SME funding can be treated as retail where it is managed as retail exposures and total funding from the SME is below AUD 2 million, on a consolidated basis where applicable (Att A para 46). Non-operational deposits from SMEs of more than AUD 2m run off at 20% or 40% (Att A Table 3).

**Sole proprietorship**: a business owned by one person, not a separate legal entity. For the LCR its deposits are wholesale, not retail (Att A para 34).

**Solvency**: having assets worth more than liabilities, so that the bank can in principle pay all debts. It differs from liquidity: a solvent bank can fail if it cannot find cash in time. Capital rules address solvency; APS 210 addresses liquidity.

**Sovereign**: a national government. Sovereign securities may be HQLA if they meet the criteria (Att A para 9(c) to (e)). Funding from sovereigns under one year gets a 50% ASF factor (Att C para 14(e)).

**Special purpose vehicle** (also known as SPV, special purpose entity): a separate legal entity set up for a narrow purpose, typically to hold securitised assets and issue securities against them. See **securitisation** and APS 210 para 5.

**Stable deposit**: the part of retail deposits fully covered by the Financial Claims Scheme where the depositor has other established relationships with the ADI that make withdrawal highly unlikely, or the deposit is in a transactional account such as one receiving salaries (Att A para 37). LCR run-off is 5% (Att A Table 3); NSFR ASF factor is 95% (Att C para 12(a)). Example Bank: A$25.0bn x 5% = 1.25.

**Standard residential property loan**: a home loan to a natural person that meets APS 112 conditions. With residual maturity of one year or more and LVR of 80% or below, unencumbered, it receives a 65% RSF factor (Att C para 35(a)). Example Bank's mortgages: A$50.0bn.

**Stressed net cash outflows**: the net cash outflows computed under the LCR stress. They set the limit on foreign-currency sovereign securities that can count as HQLA1 for non-zero risk-weighted sovereigns (Att A para 9(e)).

**Stress scenario**: a defined set of adverse events and assumptions used to test the bank. The LCR scenario is a severe 30-day liquidity stress with prescribed parameters (Att A para 1). APS 210 also requires the ADI's own stress tests (APS 210 para 62).

**Stress test**: a projection of what happens to cash flows and liquidity under a stress scenario. An LCR ADI must run them regularly for short-term and protracted, institution-specific and market-wide scenarios, singly and in combination (APS 210 para 62), and use the results to adjust strategy and the contingency funding plan (APS 210 paras 63, 66).

**Structured investment vehicle** (also known as SIV): an off-balance sheet vehicle that funds long-dated assets by issuing short-term paper. Loss of funding on SPVs, conduits and SIVs runs off at 100% in the LCR (Att A Table 3). SIVs were badly hit in the 2007 to 2009 crisis.

**Subordinated debt** (also known as sub debt, junior debt): debt that ranks behind senior debt in a failure, so it carries more risk and pays more. MLH debt securities must not be subordinated (Att B para 3). Tier 2 capital is typically subordinated debt.

**Subsidiary**: a company controlled by another. An ADI with a material banking subsidiary in another offshore jurisdiction must make sure that the subsidiary keeps an LCR of at least 100% (Att A para 28).

**Superannuation fund** (also known as super fund): a pool of retirement savings. The trustee of a superannuation or pension fund is a financial institution under APS 210 (APS 210 para 10(b)). Super fund deposits that meet the definition of operational deposits get a 50% ASF factor (Att C para 14(c)).

**Supranational** (also known as supranational institution): an international body owned by several states, such as the World Bank or IMF. Supranational debt is an eligible liquid asset for MLH (Att B para 2(d)).

**Survival horizon**: the length of time a bank can meet its obligations in a stress scenario with its own resources. The LCR sets it at 30 calendar days (Att A para 1). Banks usually test longer horizons internally (APS 210 para 62 requires protracted scenarios).

**Swap**: a contract to exchange cash flows, for example fixed-rate for floating-rate interest. Swaps are derivatives, and large swap positions can drive margin calls.

**Syndicated loan**: a loan from a group of lenders under one agreement. Facility amounts are treated by each lender's proportionate share (Att A para 51).

**Tenor**: the length of time from the start of a financial contract to its maturity. A bond issued today due in 5 years has a tenor of 5 years today and a residual maturity of 4 years one year later.

**Term deposit**: see **fixed-term deposit**. Example Bank holds A$10.0bn of retail term deposits (over 30 days, under 1 year, no early withdrawal, less stable), which run off at 0% in the LCR (Att A para 41) and get 90% ASF (Att C para 13(a)).

**Term Funding Facility** (also known as TFF): a facility the RBA introduced in response to COVID-19, announced on 19 March 2020, which gave banks three-year funding at a very low rate. It closed to new drawdowns on 30 June 2021, and banks drew about A$188bn (rba.gov.au). It is not part of APS 210.

**Tier 1 capital**: the sum of Common Equity Tier 1 and Additional Tier 1. It is the top two layers of regulatory capital and the numerator of the leverage ratio.

**Tier 2**: a lower layer of regulatory capital, usually long-dated subordinated debt that absorbs losses in failure. Tier 2 instruments with residual maturity under one year are excluded from the 100% ASF factor (Att C para 11(a)).

**Trade finance**: financing and guarantees connected to international and domestic trade, such as documentary letters of credit. Trade finance-related obligations are modelled at the average of actual monthly net outflows in a recent 12-month period (Att A Table 3) and get a 100% RSF factor on the actual net outflows of the most recent 12 months (Att C para 42).

**Tranche**: one slice of a securitisation or loan, with its own ranking and risk. Senior tranches are paid first.

**Transaction account**: an everyday account used for receiving salary and paying bills. Deposits in transactional accounts where salaries are credited can count as stable (Att A para 37(b)).

**Treasury (bank function)** (also known as group treasury, Treasury): the bank department that manages funding, liquidity, interest rate risk and the liquid asset portfolio. The Treasury function is the one that must have the authority to monetise HQLA (Att A para 22(b)). It must be challenged by an independent liquidity risk oversight function (APS 210 para 28). Not to be confused with the Commonwealth Treasury, which is a government department.

**Treasury bill** (also known as Treasury note): a short-term debt security issued by a government. See **Australian Government Securities**.

**Treasury bond** (also known as Treasury note): a government bond issued by the Australian Government. See **Australian Government Securities**.

**Trigger ratio**: an internal MLH threshold set above the 9% requirement so that the minimum is not breached outside financial stress (Att B para 5). Example: a small mutual with a 9% requirement might set a trigger at 11% and manage to that.

**Unencumbered**: free of any pledge or restriction, so the asset can be sold or repoed at any time. HQLA must be unencumbered (APS 210 para 55; Att A para 22(b)). MLH liquid assets must be free from encumbrances unless approved by APRA for a prudential purpose (Att B para 2).

**Unsecured wholesale funding**: liabilities and general obligations raised from non-natural persons (legal entities, including sole proprietorships and partnerships) that are not collateralised by legal rights to specific assets of the borrower in bankruptcy, insolvency, liquidation or resolution. Derivative obligations are excluded (Att A para 44). Includes funding callable within 30 days or with earliest maturity in that window (Att A para 45).

**Unweighted amount**: the balance of an item before any LCR run-off or inflow rate or NSFR factor is applied. Compare **weighted amount**.

**Variation margin**: collateral exchanged, usually daily, to reflect the current gain or loss on derivative positions. Under the NSFR, variation margin posted is deducted from the negative replacement cost (Att C para 10), and cash variation margin received can offset derivative assets if conditions are met (Att C para 28). Compare **initial margin**.

**Warehouse** (also known as warehouse facility): a funding line used to hold loans temporarily before they are securitised.

**Weighted amount**: the balance after the rate or factor is applied. Example: unweighted A$25.0bn stable retail deposits x 5% = weighted 1.25 outflow.

**Wholesale deposit**: a deposit from a company, trust, fund or other non-natural person. Under the LCR it is split into operational and non-operational, and by counterparty type (Att A Table 3).

**Wholesale funding**: funding raised from institutional and corporate investors and other banks, not from individuals. It includes wholesale deposits and debt securities. Wholesale funding tends to be larger, less sticky and more rate-sensitive than retail funding. Example Bank's wholesale debt is A$21.0bn, 22.8% of liabilities.

**Write-off**: removing a loan from the balance sheet because recovery is not expected. It is an accounting action, not a cash flow.

**Yield**: the return on a bond or investment, usually expressed as an annual percentage of its current price. Bond prices and yields move in opposite directions: when yields rise, prices fall. A fall in price is the market risk behind haircuts.

## Acronyms

| Acronym | Expansion |
|---|---|
| ABCP | Asset-backed commercial paper |
| ABS | Asset-backed security |
| ADI | Authorised deposit-taking institution |
| AGS | Australian Government Securities |
| ALA | Alternative liquid assets (Basel term; appears in Att C para 32(a)) |
| ALCO | Asset and liability committee |
| AT1 | Additional Tier 1 capital |
| APG | Prudential Practice Guide |
| APRA | Australian Prudential Regulation Authority |
| APS | Prudential Standard for ADIs (for example APS 210) |
| ASF | Available stable funding |
| ASIC | Australian Securities and Investments Commission |
| ASX | Australian Securities Exchange |
| AUD | Australian dollar |
| AUSTRAC | Australian Transaction Reports and Analysis Centre |
| BBSW | Bank bill swap rate |
| BCBS | Basel Committee on Banking Supervision |
| BIS | Bank for International Settlements |
| bp, bps | Basis point, basis points |
| CCP | Central counterparty |
| CD, NCD | Certificate of deposit, negotiable certificate of deposit |
| CET1 | Common Equity Tier 1 |
| CFP | Contingency funding plan |
| CFR | Council of Financial Regulators |
| CLF | Committed Liquidity Facility |
| CP | Commercial paper |
| CPS | Prudential Standard that applies across industries (for example CPS 220) |
| ECAI | External credit assessment institution |
| ECB | European Central Bank |
| ECL | Expected credit loss |
| ELA | Exceptional Liquidity Assistance |
| ESA | Exchange Settlement Account |
| EU | European Union |
| EWI | Early warning indicator |
| FCS | Financial Claims Scheme |
| FTP | Funds transfer pricing |
| FX | Foreign exchange |
| HQLA | High-quality liquid assets |
| HQLA1, HQLA2A, HQLA2B | The categories of HQLA (Att A paras 6 to 12) |
| IMF | International Monetary Fund |
| IRB | Internal ratings-based (approach to credit risk, APS 113) |
| LC | Letter of credit |
| LCR | Liquidity coverage ratio |
| LCR ADI | ADI subject to the LCR |
| LDR | Loan-to-deposit ratio |
| LOC | Local operational capacity |
| LVR | Loan-to-valuation ratio |
| MDB | Multilateral development bank |
| MLH | Minimum liquidity holdings |
| MLH ADI | ADI subject to the MLH approach |
| MTM | Mark-to-market |
| NIM | Net interest margin |
| NOHC | Non-operating holding company |
| NPL | Non-performing loan |
| NSFR | Net stable funding ratio |
| OBS | Off-balance sheet |
| OMO | Open market operations |
| PD | Probability of default |
| PSE | Public sector entity |
| RBA | Reserve Bank of Australia |
| RMBS | Residential mortgage-backed securities |
| RSF | Required stable funding |
| SFT | Securities financing transaction |
| SIV | Structured investment vehicle |
| SME | Small and medium enterprise |
| SPV | Special purpose vehicle |
| TD | Term deposit |
| TFF | Term Funding Facility |
| TLAC | Total loss-absorbing capacity (not part of APS 210; listed because it appears in bank reports) |

## Common confusions

### Liquidity vs solvency vs capital

| | Liquidity | Solvency | Capital |
|---|---|---|---|
| Question | Can the bank pay what falls due, in cash, on time? | Are assets worth more than liabilities? | How big is the loss-absorbing cushion of owners' money? |
| Measured by | LCR, NSFR, MLH | Equity above zero; capital ratios | CET1, Tier 1, total capital ratios, leverage ratio |
| Standard | APS 210 | Capital standards (APS 110 to 112) | APS 110 to 112 |
| Failure looks like | Cannot find cash; forced asset sales | Losses exceed equity | Ratio falls below the minimum |

A solvent bank can still fail if depositors leave faster than assets can be sold. Capital is not a pile of cash: Example Bank's A$8.0bn of equity funds assets and is not sitting in the vault.

### LCR vs NSFR vs MLH

| | LCR | NSFR | MLH |
|---|---|---|---|
| Horizon | 30 days of stress (Att A para 1) | One year (Att C para 1) | Point-in-time stock of liquid assets |
| Formula | HQLA / net cash outflows | ASF / RSF | Liquid assets / (liabilities plus irrevocable commitments) |
| Minimum | 100% (locally incorporated, AUD and all currencies); 40% foreign ADI (APS 210 para 55) | 100% (APS 210 para 60) | 9% (APS 210 para 57) |
| Who | LCR ADIs | Locally incorporated LCR ADIs (APS 210 paras 59 to 60) | MLH ADIs |

### Haircut vs run-off rate vs inflow rate vs ASF factor vs RSF factor

| Term | Applied to | Where | Bigger number means |
|---|---|---|---|
| Haircut | Market value of an HQLA asset | LCR numerator (Att A paras 9 to 12) | Asset counts for less |
| Run-off rate | Liability or commitment balance | LCR outflows (Att A Table 3) | More cash leaves |
| Inflow rate | Contractual receivable | LCR inflows (Att A paras 54 to 66) | More cash arrives |
| ASF factor | Liability or capital | NSFR numerator (Att C paras 11 to 15) | More stable, helps the ratio |
| RSF factor | Asset or commitment | NSFR denominator (Att C paras 29 to 37) | Needs more stable funding, hurts the ratio |

Example: A$100 of stable retail deposits has a 5% run-off (outflow 5) and a 95% ASF factor (ASF 95). Same money, two tests, two factors.

### HQLA vs liquid assets vs cash

Cash is notes and coin plus balances at the central bank. HQLA is cash plus certain securities that are unencumbered and operationally available. "Liquid assets" is a looser word: for MLH it means the list in Att B para 2, which includes bank bills and ADI-issued securities that are not HQLA. Example Bank's HQLA (17.0) is cash and RBA balances 5.0 plus government securities 12.0; its other debt securities (3.0) are not HQLA.

### Encumbered vs pledged vs unencumbered

Pledged is one way of being encumbered. Encumbered also covers assets backing covered bonds or securitisations, or used in repos or collateral swaps (Att C footnote 21). Unencumbered means free of all of these. Only unencumbered assets count as HQLA (APS 210 para 55). Under the NSFR, how long an asset is encumbered matters: one year or more gives 100% RSF (Att C para 23).

### Contractual vs behavioural maturity

Contractual maturity is the date in the contract. Behavioural maturity is when customers actually act. An at-call savings account is contractually zero days but behaviourally may last years. APS 210 prescribes rates, so the LCR does not rely on a bank's own behavioural models for most items, but APRA assesses derived assumptions (Att A para 32).

### Residual vs original maturity

A 5-year bond issued 4 years and 9 months ago has an original maturity of 5 years and a residual maturity of 3 months. The LCR and NSFR use residual maturity (for example Att A para 45; Att C para 18). Using original maturity is a common data error.

### Stable vs less stable deposits

Stable: covered by the Financial Claims Scheme and either supported by other relationships or in a transactional account (Att A para 37). Less stable: everything else, scored on four criteria (Att A paras 38 to 40). Run-off 5% vs 10% or 25%; ASF 95% vs 90%.

### Operational vs non-operational deposits

Operational deposits are kept for payments, clearing, custody or cash management services where the customer depends on the bank (Att A paras 47 to 50). Non-operational deposits are parked money. Example Bank: operational A$4.0bn at 25% (not fully insured) = 1.00; corporate non-operational A$6.0bn at 40% = 2.40.

### Credit facility vs liquidity facility

A credit facility funds general business needs. A liquidity facility backs up a customer's maturing market debt (Att A para 51). Different LCR rates: for non-financial corporates, 10% against 30% (Att A Table 3). Example Bank: credit facilities A$5.0bn x 10% = 0.50; liquidity facilities A$1.0bn x 30% = 0.30.

### Committed vs revocable

A committed facility must be honoured; revocable can be cancelled by the bank. Revocable credit and liquidity facilities have a 5% LCR rate (Att A Table 3); committed ones use counterparty-specific rates.

### Repo vs reverse repo

Same trade, opposite sides. In a repo the bank sells securities, receives cash and later buys back: it borrows. In a reverse repo the bank buys securities, pays cash and later sells back: it lends. Repo creates an outflow when it matures; reverse repo an inflow, depending on collateral (Att A Tables 3 and 4).

### Secured vs unsecured funding

Secured funding is backed by named assets; unsecured is not. Unsecured wholesale funding is defined in Att A para 44. Secured funding runs off at 0% to 100% depending on collateral quality, unsecured financial institution funding at 100%.

### Level 1 vs Level 2

Level 1 is the ADI alone; Level 2 is the ADI plus its consolidated subsidiaries (APS 210 para 3). The standard must be met on both (Att A para 26). Do not confuse this with HQLA "Level 2" (HQLA2A and HQLA2B), a different idea.

### ADI vs bank

All banks in Australia are ADIs, but not all ADIs are called banks: credit unions and building societies are ADIs too. APS 210 applies to all ADIs (APS 210 para 2). The word "bank" has legal restrictions on use in Australia (as generally understood; verify on apra.gov.au).

### Foreign ADI vs foreign subsidiary

A foreign ADI is a branch of an overseas bank in Australia (LCR minimum 40% all-currencies, APS 210 para 55(b); LOC assessment, paras 67 to 69). A foreign-owned subsidiary incorporated in Australia is a locally incorporated ADI and faces the full 100% tests.

### Retail vs SME vs wholesale

Retail: natural persons (Att A para 34). SME: small businesses treated as retail where managed as retail and total funding is below AUD 2 million (Att A para 46). Wholesale: all other non-natural persons, including sole proprietorships and partnerships (Att A para 34).

### Market value vs carrying value vs face value

| | What it is | Used in |
|---|---|---|
| Market value | Price now | HQLA (Att A para 9); MLH (Att B para 2) |
| Carrying value | Amount on the balance sheet | NSFR (Att C paras 7, 17) |
| Face value | Amount to be repaid at maturity | Interest and repayment calculations |

Example: a bond with face A$100m, market value A$97m after yields rise, and carrying value A$100m at amortised cost. In the LCR it counts A$97m (HQLA1); in the NSFR, A$100m at carrying value.

### Initial margin vs variation margin

Initial margin is an upfront buffer against future losses and is held until the trade ends (85% RSF if posted, Att C para 36(a)). Variation margin settles daily gains and losses; posted variation margin is deducted from derivative liabilities (Att C para 10).

### Weighted vs unweighted amounts

Unweighted is the balance as reported. Weighted is after the factor. In public disclosures, unweighted values show size and weighted values show regulatory effect. Example: unweighted 25.0, weighted 1.25.

### Funding liquidity risk vs market liquidity risk

Funding: cannot meet obligations when due. Market: cannot sell assets without loss because markets are thin (APS 210 para 20). They feed each other: if funding dries up the bank sells assets, and if markets are thin the sales cost more.

### Prudential standard vs prudential practice guide

A standard is binding and enforceable (APS 210). A practice guide (APG 210) explains good practice and is not binding. When you need the rule, read the standard.

### Other pairs readers mix up

- **Term deposit vs term funding**: a term deposit is a customer deposit; term funding is wholesale debt of long maturity.
- **Treasury function vs Treasury department**: the bank's Treasury manages liquidity; the Australian Treasury is the government department.
- **Bank bill vs bank bill swap rate**: the bill is an instrument; BBSW is the rate derived from trading in it.
- **Run-off vs run on the bank**: run-off is a regulatory percentage; a run is an event.
- **Notional vs replacement cost**: notional is the contract's face amount; replacement cost is the mark-to-market value used for liquidity measures.

---

# Appendix A: Connecting the guide to the dashboard's rules table

The liquidity dashboard built alongside this guide calculates the LCR and NSFR
from a table called `rules.csv`. Each row of that table is one category from
APS 210. This appendix shows how to read it using what the guide has taught.

## The columns

| Column | Meaning | Where the guide explains it |
|---|---|---|
| `category` | A short code for one APS 210 category, for example `dep_retail_stable` | Chapters 5 and 6 |
| `label` | The name shown on the dashboard | |
| `feed` | Which source data set the balance comes from | Chapter 4 (instruments) |
| `lcr_side` | The role in the LCR: `hqla1`, `hqla2a`, `hqla2b`, `outflow`, `inflow` or `none` | Chapter 5 |
| `lcr_factor` | For HQLA: the share of market value kept after the haircut (1 minus the haircut). For outflows: the run-off rate. For inflows: the inflow rate | Chapter 5 quick reference |
| `nsfr_side` | The role in the NSFR: `asf` (available stable funding), `rsf` (required stable funding) or `none` | Chapter 6 |
| `nsfr_factor` | The ASF or RSF factor | Chapter 6 quick reference |
| `ref` | The paragraph of the standard: A = Attachment A, C = Attachment C | |

> **Example:** the row `hqla2a, ..., hqla2a, 0.85, rsf, 0.15, A10; C33(a)` says:
> in the LCR this is an HQLA2A asset counted at 85% of market value (a 15%
> haircut, Att A para 10); in the NSFR it needs 15% stable funding (Att C para
> 33(a)).

## The category families

| Prefix | What it holds | LCR role | NSFR role | Guide section |
|---|---|---|---|---|
| `cash_esa`, `hqla1_*`, `hqla2a`, `hqla2b*` | Unencumbered liquid assets | HQLA numerator | Low RSF (0% to 50%) | Chapter 5 sections 3 to 7; Chapter 6 section 6.5 |
| `hqla*_enc_*`, `sec_encumbered` | Liquid assets pledged as collateral | None: encumbered assets are not HQLA | RSF by length of encumbrance | Chapter 5 section 9; Chapter 6 section 6.4 |
| `sec_other*`, `equities_*` | Securities that are not HQLA | Inflow only if maturing within 30 days | RSF 50% or 85% | Chapter 6 section 6.5 |
| `dep_retail_*`, `dep_sme`, `dep_term_*` | Retail and small business deposits | Outflows at 5%, 10%, 25% or 0% | ASF 90% to 100% | Chapter 5 section 12; Chapter 6 section 6.3 |
| `dep_operational*`, `dep_corp*`, `dep_fi*` | Wholesale deposits | Outflows at 5% to 100% | ASF 0% or 50% | Chapter 5 section 13 |
| `debt_*`, `capital`, `other_liabilities`, `abs_maturing` | Wholesale debt, capital and other funding | 100% outflow if due within 30 days | ASF by remaining maturity | Chapter 5 section 13; Chapter 6 section 6.3 |
| `repo_*` | Secured borrowing | Outflow by quality of collateral | ASF by maturity | Chapter 5 section 14 |
| `revrepo_*`, `margin_lending` | Secured lending | Inflow by quality of collateral | RSF 10% to 50% | Chapter 5 section 18 |
| `deriv_*`, `coll_*`, `nsfr_deriv_*`, `im_posted` | Derivatives and collateral | Outflows and inflows at 100% (20% for one line) | Separate NSFR derivative lines | Chapter 5 section 15; Chapter 6 section 6.5 |
| `fac_*` | Undrawn facilities | Drawdown rates 5% to 100% | RSF 5% (1% if unconditionally revocable) | Chapter 5 section 16; Chapter 6 section 6.7 |
| `trade_finance`, `guarantees`, `buyback_*`, `structured_products` and similar | Contingent obligations | Outflows on special bases | RSF on actual outflows | Chapter 5 section 17 |
| `loan_due30_*`, `other_inflows`, `sec_maturing_30d` | Cash due in within 30 days | Inflows at 50% or 100% | None (the loan balance is counted separately) | Chapter 5 section 18 |
| `loan_*` (others), `other_assets` | Loan balances and other assets | None | RSF 15% to 100% | Chapter 6 section 6.5 |

## Stock rows and flow rows

Most rows hold a **stock**: a balance at a point in time. A few hold a **flow**:
cash expected over the next 30 days. A loan appears twice by design. Its balance
sits in a stock row (for example `loan_mortgage`) and drives the NSFR. The
repayments due on it within 30 days sit in a flow row (`loan_due30_retail`) and
drive the LCR. The flow rows are the ones with `nsfr_side` of `none`.

## What the table does not do

- It does not unwind short-term repos before applying the HQLA2 caps (Att A
  paras 7 and 8; Chapter 5 section 6.4). This matters only when a cap binds.
- It has no line for a Committed Liquidity Facility.
- Two rates are left at zero for the bank to set: affiliated dealer
  obligations and other non-contractual contingent obligations (Att A Table 3).
- It calculates one all-currencies LCR. The standard also requires an
  Australian dollar LCR (APS 210 para 55).

# Appendix B: What was checked, and what was not

## How this guide was produced and checked

1. A syllabus fixed the content of every chapter, the accuracy rules and one
   shared worked example, whose arithmetic was computed by script.
2. Five writers produced the chapters from the text of APS 210 (July 2025).
3. The editor then checked the result:
   - Every numbered paragraph of the main body (11 to 72), Attachment A (1 to
     66), Attachment B (1 to 6) and Attachment C (1 to 42) is cited in the
     guide at least once.
   - Tables 1 to 4 of Attachment A and Table 1 of Attachment C were re-read
     from the published PDF by the position of each number on the page,
     because plain text extraction separates rates from their rows. This
     settled the scorecard points (2, 2, 1, 1), the 25% rate for secured
     funding backed by HQLA2B RMBS (one cell spanning two rows), and the 1%
     factor for unconditionally revocable facilities.
   - All 92 divisions and percentage multiplications written out in the
     chapters were recomputed. None was wrong.
   - All 195 mandatory terms have a glossary entry.

## Facts from outside APS 210 that were checked against official sources

| Statement | Source |
|---|---|
| In Australian dollars, only notes and coin, balances held with the RBA, and Australian Government and semi-government securities qualify as HQLA1, and no Australian dollar assets currently qualify as HQLA2 | APRA, Liquidity frequently asked questions: https://www.apra.gov.au/liquidity-frequently-asked-questions |
| The July 2025 version of APS 210 requires MLH ADIs to value liquid assets at market value, and requires all ADIs to be operationally ready to provide information when requesting Exceptional Liquidity Assistance. APRA deferred a proposal to phase out bank debt securities as MLH liquid assets | APRA, "APRA finalises targeted changes to strengthen banks' liquidity and capital requirements": https://www.apra.gov.au/news-and-publications/apra-finalises-targeted-changes-to-strengthen-banks%E2%80%99-liquidity-and-capital |
| APS 210 is in force from 1 July 2025 | APRA: https://www.apra.gov.au/standards/aps-210 |
| The aggregate Committed Liquidity Facility was phased out to zero as at 1 January 2023, and remains available to be reactivated | APRA: https://www.apra.gov.au/news-and-publications/apra-phases-out-aggregate-committed-liquidity-facility ; RBA Bulletin: https://www.rba.gov.au/publications/bulletin/2024/jan/the-committed-liquidity-facility-2015-2022.html |
| The Term Funding Facility was announced in March 2020 and closed to new drawdowns on 30 June 2021 | RBA (checked by a writer on rba.gov.au) |
| The Financial Claims Scheme covers deposits up to A$250,000 per account holder per ADI | APRA and Treasury (checked by a writer on official sites) |
| Liquidity is reported to APRA under Reporting Standard ARS 210.0. The April 2021 version lists forms 210.1A (LCR, all currencies), 210.1B (LCR, Australian dollars), 210.2 (MLH ratio), 210.3.1 and 210.3.2, 210.4 (three-year funding plan), 210.5 (daily liquidity report) and 210.6 (NSFR). The version now in force may differ in detail | APRA: https://www.apra.gov.au/liquidity ; https://www.apra.gov.au/system/files/2020-12/Reporting%20Standard%20ARS%20210.0%20Liquidity%20-%20clean.pdf |

## Statements that were not checked against an official source

These are worded cautiously in the chapters ("as generally understood").
Confirm them before relying on them.

- **History (Chapter 1):** the dates of overseas events in 2007 to 2009 and
  2023, and of the Basel III publications.
- **Regulators (Chapter 2):** the origin of the "twin peaks" model, membership
  of the Council of Financial Regulators, the exact titles of several APRA
  standards (APS 110, 111, 220, 330; CPS 001, 220, 230), and the description of
  RBA operations and standing facilities.
- **Accounting (Chapter 3):** the classification categories and expected
  credit loss stages in AASB 9, typical statutory balance sheet line names,
  the 35% risk weight for standard mortgages, and capital tier definitions.
- **Public disclosure (Chapter 3):** how APS 330 presents the LCR (averages of
  daily values) and the NSFR (quarter-end), taken from search summaries.
- **Instruments (Chapter 4):** features of Australian instruments, who
  administers the bank bill swap rate, the names of overnight rates, the Basel
  5% test for a significant currency, and the eligibility of self-securitised
  assets for RBA repo.
- **Practice (Chapters 8 and 9):** typical committee membership, typical
  limits and early warning indicators, funds transfer pricing practice, the
  Basel 1% threshold for a significant funding counterparty, and RBA intraday
  arrangements. These describe common practice, not requirements of APS 210.
- **MLH (Chapter 7):** that MLH classification is generally used for smaller
  ADIs, and that "settlement funds" means Exchange Settlement Account balances.
- **Interpretations:** the plain-language reasons given for individual
  factors, the pseudo-code for the HQLA caps, and the illustration of the
  unwind in Chapter 5 section 6 are the guide's own reading. The standard gives
  no worked example. How the Australian dollar LCR is calculated is not set out
  in Attachment A and should be confirmed in APRA's reporting instructions.

## Simplifications in the Example Bank numbers

- Derivatives are included in the LCR (two small outflows) but ignored in the
  NSFR. Under Att C para 37(d), 20% of gross derivative liabilities would add
  to required stable funding.
- Wholesale debt under one year is assumed to be held by financial
  institutions. If it were held by non-financial corporates, sovereigns or
  public sector entities, it would earn 50% available stable funding instead
  of 0% (Att C para 14(a) and (e)).
- "Other liabilities" of A$2.0bn are given no outflow in the LCR.
- All high-quality liquid assets are HQLA1, so no haircut or cap applies.
- Shareholders' equity is treated as equal to regulatory capital.
- There is one currency and one legal entity, so the Australian dollar LCR,
  the all-currencies LCR, Level 1 and Level 2 are all the same number.
