# Internal Controls Matrix — Budget, Expenditure, Revenue and Treasury

*Author: Anicet Safari, CPA · Illustrative work sample, October 2026*

The matrix in [`controls_matrix.csv`](controls_matrix.csv) lists 12 key controls across the processes mapped in folder 03. For each control it records the risk addressed, the control activity, whether it is preventive or detective, automated or manual, its frequency, owner, COSO 2013 component, the evidence it leaves and how an auditor would test it.

## Summary

| ID | Control | Type | Nature |
|---|---|---|---|
| C-01 | Budget load reconciled to appropriation law | Preventive | Manual |
| C-02 | Releases capped at appropriation | Preventive | Automated |
| C-03 | Monthly review of budget execution report | Detective | Manual |
| C-04 | Funds-availability hard stop on commitments | Preventive | Automated |
| C-05 | Reallocation workflow with two-level approval | Preventive | Automated |
| C-06 | Account combination validation | Preventive | Automated |
| C-07 | Three-way match (PO, GRN, invoice) | Preventive | Automated |
| C-08 | Payment approval limits and segregation of duties | Preventive | Automated |
| C-09 | Supplier bank details from verified master only | Preventive | Automated + manual |
| C-10 | Monthly bank reconciliation, prepared ≠ approved | Detective | Manual + system |
| C-11 | Unique payment reference on every bill | Preventive | Automated |
| C-12 | Suspense ageing review and 30-day clearance | Detective | Manual + system |

## Design choices

- **Prefer automated preventive controls** where the system can enforce the rule (C-02, C-04, C-06, C-07, C-08). They work on every transaction and cannot be skipped.
- **Keep detective controls for what the system cannot judge** — whether spending is on track (C-03), whether reconciling items are genuine (C-10), whether a suspense item belongs to a payer (C-12).
- **Every control leaves evidence** that an internal or external auditor can test, listed in the matrix.
- **Segregation of duties is built into roles**, not left to instructions: preparer ≠ approver for vouchers (C-08) and reconciliations (C-10).
