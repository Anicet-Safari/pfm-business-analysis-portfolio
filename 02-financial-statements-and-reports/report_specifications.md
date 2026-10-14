# Report Specifications

*Author: Anicet Safari, CPA · Illustrative work sample, October 2026*

Each specification uses the same template, so developers, accountants and auditors read them the same way.

---

## RPT-01 Statement of Cash Receipts and Payments

| Item | Specification |
|---|---|
| **Purpose** | Annual primary statement for a budget entity reporting on the IPSAS cash basis. |
| **Users** | Accounting officer, Accountant General, Auditor General, Parliament. |
| **Frequency / period** | Annual (fiscal year); also produced quarterly as an interim statement. |
| **Data source** | General ledger cash postings, filtered by administrative segment (entity) and fiscal period. |
| **Selection** | Economic classes `1` (receipts) and `2`, `3` (payments). Balance-sheet classes `6`, `7` are excluded from the lines but used for opening and closing cash. |
| **Grouping** | Statement lines are mapped from economic categories through a maintained mapping table (economic code → statement line), not hard-coded in the report. |
| **Columns** | Current year actual; prior year actual (comparative). |
| **Calculated lines** | Total receipts = Σ receipt lines. Total payments = Σ payment lines. Net increase / (decrease) in cash = total receipts − total payments. Closing cash = opening cash + net change. |
| **Sign convention** | Receipts and payments are both shown as positive amounts; net decrease shown in brackets. |
| **Rounding** | RWF thousands; rounding differences pushed to the largest line, never to totals. |
| **Notes** | Each line carries a note reference; notes list the economic items making up the line. |

**Tie-outs (report cannot be released unless all pass):**

| # | Test |
|---|---|
| T1 | Total receipts = Σ trial balance credits on class `1` for the entity and period. |
| T2 | Total payments = Σ trial balance debits on classes `2` and `3` for the entity and period. |
| T3 | Every economic code with a balance maps to exactly one statement line (no unmapped and no double-mapped codes). |
| T4 | Opening cash = prior year closing cash as published. |
| T5 | Closing cash = cash book balance = reconciled bank balance (see folder 07). |

---

## RPT-02 Statement of Comparison of Budget and Actual Amounts

| Item | Specification |
|---|---|
| **Purpose** | Shows how the approved budget was executed, as required where the budget is made publicly available (IPSAS 24 approach). |
| **Users** | Same as RPT-01, plus the Budget Department and the Public Accounts Committee. |
| **Data source** | Budget ledger (original appropriation and all approved reallocations and supplementary budgets) and the general ledger actuals, on the **same basis and classification**. |
| **Columns** | Original budget · Final budget · Actual on comparable basis · Variance (final − actual) · Execution rate (actual ÷ final). |
| **Rows** | Same statement lines as RPT-01, so the two statements reconcile line by line. |
| **Rules** | Final budget = original + approved reallocations ± supplementary budget, from the budget ledger audit trail. Execution rate shows 0 when the final budget is zero (no division error). |
| **Explanations** | Any line executed outside a configurable threshold (default 90%–110%) is flagged; the accounting officer must enter a narrative explanation before the report is finalised. |

**Tie-outs:**

| # | Test |
|---|---|
| T1 | Actual column totals = RPT-01 totals. |
| T2 | Original budget column = appropriation as voted. |
| T3 | Final budget − original budget = Σ approved budget adjustments in the budget ledger. |

---

## RPT-03 Monthly Budget Execution Report

| Item | Specification |
|---|---|
| **Purpose** | In-year management report: how much of each budget line is committed, paid and still available. |
| **Users** | Accounting officer, budget managers, the Budget Department. |
| **Frequency** | Monthly, available by working day 5 after month-end; on demand during the month. |
| **Parameters** | Entity, programme, fund, period (month, year-to-date). |
| **Columns** | Final budget · Released (cash ceilings) · Commitments outstanding · Payments YTD · Available = final budget − commitments outstanding − payments YTD · % paid. |
| **Drill-down** | From any line to the list of commitments and payments behind it. |
| **Exceptions** | Lines where Available < 0 are shown in a separate exception section (they indicate a failed funds-availability control). |

**Tie-outs:**

| # | Test |
|---|---|
| T1 | Payments YTD = general ledger actuals for the same period and segments. |
| T2 | Commitments outstanding = open commitment register for the same segments. |
| T3 | No line shows Available < 0 (otherwise raise a control incident, see folder 06, control C-04). |

---

## Worked example

RPT-01 and RPT-02 are built in [`financial_statements_worked_example.xlsx`](financial_statements_worked_example.xlsx) for a fictional ministry, with tie-out tests T1, T2, T3 and T5 (RPT-01) and T1 (RPT-02) automated on the **Checks** sheet. T4 needs the prior-year published statement, so it is checked manually.
