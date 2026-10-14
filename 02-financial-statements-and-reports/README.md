# Financial Statements and Report Specifications

*Author: Anicet Safari, CPA · Illustrative work sample, October 2026 · Fictional data*

This folder shows how I define financial reporting requirements and turn them into reports that a system can produce and an auditor can trace.

| File | What it is |
|---|---|
| [`report_specifications.md`](report_specifications.md) | Specifications for three reports: Statement of Cash Receipts and Payments, Statement of Comparison of Budget and Actual Amounts, and a monthly Budget Execution Report. Each states its users, data source, layout, calculation logic and the trial balance tie-outs it must pass. |
| [`financial_statements_worked_example.xlsx`](financial_statements_worked_example.xlsx) | A working model of the first two specifications for a fictional ministry. Every statement line is a formula on one ledger sheet, and a Checks sheet proves the statements agree with the ledger, with each other and with the reconciled bank balance (all six checks pass). |

## What the worked example demonstrates

- **One data source.** Both statements read the same ledger, so they cannot disagree.
- **Classification-driven layout.** Statement lines come from the economic classification in folder 01, not from hand-picked accounts.
- **Built-in tie-outs.** Totals, mapping completeness and closing cash are checked automatically.
- **Variance rule.** The budget-versus-actual statement flags lines executed outside a set threshold (90%–110%); in the example, capital spending (76% executed) is flagged for a narrative explanation.
