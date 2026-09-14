# Real Rate Reveal — V1

A premium, minimal Notion product for US/UK freelancers that answers one question:
**"How much did I REALLY earn from this client?"**

This was built directly inside Notion using a live Notion integration (not exported as
CSV/template files) because that integration was available in this session. Everything
below already exists as a working Notion workspace — no import step is required.

👉 **Open it here:** https://app.notion.com/p/3dab79fed5d18137a6b5cacdef3f4574

> This page was created as a **private draft**. Open the link above, then use Notion's
> "Move to" to place it wherever you want in your own workspace (or share it with your
> team) — it stays private until you do.

## What was built automatically

- The **Real Rate Reveal** home page — header, subtitle, Quick Actions (Add Client /
  Log Hours / Log Payment), and a **Client Health** section with a board grouped by
  status (🟢 GOOD / 🟡 WATCH / 🔴 RENEGOTIATE) and a table sorted by
  *Money Left on the Table* (highest first).
- Exactly **3 databases**, wired together with two-way relations:
  - **Clients** — 19 properties: Client Name, Target Hourly Rate, the two relations,
    5 rollups (Total Amount Received, Total Real Hours, Unpaid/Free Hours,
    Scope Creep Hours, Avg Payment Delay), and 10 formulas (Real Hourly Rate,
    Expected Earnings, Money Left on the Table, Scope Creep Impact, Unproductive
    Hours Ratio, Rate Score, Payment Score, Workload Score, Client Health Score,
    Client Status).
  - **Time Log** — Entry, Client, Date, Hours Spent, Work Type (Billable / Free /
    Unpaid / Scope Creep), Unpaid/Free Hours (formula), Scope Creep Hours (formula).
  - **Payments** — Payment, Client, Amount Received, Due Date, Date Received,
    Payment Delay (Days) (formula), Payment Delay Status (formula).
- All formulas exactly as specified (see "Formula notes" below for two small,
  necessary judgment calls).
- One realistic demo client, **BrightPath Media**, with the 5 time entries and 2
  payments from the brief already entered, so you can see the whole system working
  with real numbers the moment you open it.

## V2: visual & UX pass

A follow-up pass polished presentation only — no database, formula, relation, or
rollup was touched:

- Home page now opens with a real `# REAL RATE REVEAL` heading and a short
  **"How it works"** (5 steps), before Quick Actions.
- The single "Client Health" section was split into two clearly headed, separately
  scannable sections: **Client Health** (board, grouped by status) and
  **Biggest Financial Impact** (table, sorted by Money Left on the Table).
- Added a short **"What the numbers mean"** glossary (Real Hourly Rate, Money Left
  on the Table, Scope Creep, Client Health Score) using the exact microcopy from
  the brief.
- Added a plain-text note (on the home page and on the BrightPath Media page)
  about manually reordering properties — see below.

## V3: Average Payment Delay display fix

The **Payments** database and its "Payment Delay (Days)" / "Payment Delay Status"
formulas are untouched. On **Clients**, the existing "Avg Payment Delay (Days)"
rollup (a signed number — negative for early, positive for late) is also untouched,
because `Payment Score` and `Client Health Score` read it directly; changing its
type would have broken those formulas.

Instead, a new formula property, **"Avg Payment Delay"**, was added next to it.
It reads the same untouched rollup and renders it the way you asked:
- Average before the due date → `"X days early"`
- Average exactly on the due date → `"On time"`
- Average after the due date → `"X days late"`
- No payments yet → `"Not tracked"`

The averaging itself is unchanged — it's the same mean of signed day-deltas as
before, just displayed in words instead of a signed number. For BrightPath Media
(5 days late, then 2 days early → average +1.5) this now reads **"1.5 days late"**
instead of "1.5".

Nothing else was touched: Rate Score, Payment Score, Workload Score, Client
Health Score, Real Hourly Rate, Expected Earnings, and Money Left on the Table
all use the exact same formula code as before (verified by comparing each
formula's internal reference after the change).

## What you may want to do manually

- **Reorder properties on a client's page**, if you want the exact on-page reading
  order from the brief (Money Left on the Table → Real Hourly Rate vs Target →
  Health Score → …). Notion lets you drag properties in the page's Properties panel
  in a few seconds; this isn't something the API can safely do without risking the
  relations already linked to your demo data, so it was left as-is (in the same
  order the properties are listed in the spec). Both the home page and the
  BrightPath Media page carry a short note about this.
- **Double-check the "Client Health" board is grouped by Client Status** — it was
  configured that way, but Notion's API doesn't echo grouping back for
  confirmation. If it ever shows one column instead of three, open the view's
  "···" menu → Group → Client Status (a few seconds).
- **Show "Unproductive Hours Ratio" as a percent**, if you'd like the literal `%`
  sign — open the formula editor for that property and switch its number format to
  "Percent". It already calculates correctly (0.2 = 20%); this is purely cosmetic.
- **Two payment-delay properties now exist on Clients**: "Avg Payment Delay (Days)"
  (the raw signed number, kept only because Payment Score/Health Score need it)
  and "Avg Payment Delay" (the friendly "X days early/late" text — this is the one
  to read). If you'd rather see only one, hide "Avg Payment Delay (Days)" from any
  table view you use (Show/Hide in the "···" menu) — it will keep working for the
  scores either way, it just won't be visible.
- **Move the page** out of "Private" into wherever you keep client-facing tools,
  and share it with anyone who needs access.

## Formula notes (small judgment calls made to satisfy the spec)

- **Real Hourly Rate** guards against divide-by-zero: a client with 0 hours logged
  shows `$0`.
- **Rate Score / Workload Score** default to their neutral midpoint (25) for a
  brand-new client with no hours logged yet, matching the brief's "a new client
  with no history may initially receive the neutral/default score."
- **Payment Score** is neutral (20/25) only when a client has *no payments at all*
  yet. Once payments exist, it's 25 for an on-time-or-early average delay, and
  decreases as the average delay grows (avg delay × 10, floored at 0) — calibrated
  so the BrightPath Media demo client lands exactly on the health score of 55 and
  status 🟡 WATCH specified in the brief.

## Demo data check (BrightPath Media, Target Hourly Rate $75)

| Metric | Expected | 
|---|---|
| Total Received | $1,140 |
| Real Hourly Rate | ≈ $38/hr |
| Unpaid / Free Hours | 2h |
| Scope Creep Hours | 4h |
| Scope Creep Impact | $300 |
| Expected Earnings | $2,250 |
| Money Left on the Table | $1,110 |
| Unproductive Hours Ratio | 20% |
| Avg Payment Delay | 1.5 days |
| Client Health Score | 55 |
| Client Status | 🟡 WATCH |

Every formula above was built and verified against this exact scenario before the
demo data was entered.
