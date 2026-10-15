# Procedure — Monthly Bank and Sub-Ledger Reconciliation

*Author: Anicet Safari, CPA · Illustrative work sample, October 2026*

| Item | Value |
|---|---|
| Procedure ID | FIN-PRO-07 |
| Applies to | All bank accounts held by the entity (TSA sub-accounts, project accounts, revenue collection accounts) and the payables, commitments and suspense sub-ledgers |
| Control implemented | `C-10` Monthly bank reconciliation; `C-12` Suspense clearance |
| Deadline | Working day 10 after month-end |

## 1. Roles

| Role | Duty |
|---|---|
| Reconciliation Officer | Prepares reconciliations; investigates and clears reconciling items |
| Chief Accountant | Reviews and approves; must not be the preparer |
| Accounting Officer | Receives the monthly status summary and escalations |

## 2. Part A — Bank reconciliation

**Step 1. Gather inputs (working days 1–2).**
Obtain the bank statement for the month (electronic or certified copy) and run the cash book report for the same account and period. Confirm the statement's opening balance equals last month's closing balance.

**Step 2. Match transactions (days 2–5).**
Tick each cash book entry against the statement, first by reference and amount, then by amount and date. Record what is left on each side.

**Step 3. Classify unmatched items.**

| Unmatched on… | Type | Treatment |
|---|---|---|
| Cash book, receipt | Uncredited receipt (deposit in transit) | Reconciling item; must clear in the next statement |
| Cash book, payment | Unpresented payment | Reconciling item; follow up if older than 60 days; cancel and re-issue only with approval if older than the validity period |
| Statement, debit (charges, direct debits) | Cash book adjustment | Post to the cash book with the correct economic code |
| Statement, credit (unidentified) | Cash book adjustment | Post to suspense with a reason code (`C-12`) |
| Either side, wrong amount | Error | Correct by journal with supporting documents; never by changing the original entry |

**Step 4. Prepare the two-sided statement.**

| Cash book side | Bank side |
|---|---|
| Balance per cash book | Balance per bank statement |
| ± Cash book adjustments (charges, direct credits, errors) | + Uncredited receipts |
| | − Unpresented payments |
| **= Adjusted cash book balance** | **= Adjusted bank balance** |

The two adjusted balances must be equal. An unexplained difference is never written off or carried as a balancing figure.

**Step 5. Review and approve (by day 10).**
The Chief Accountant checks that: inputs are complete; each reconciling item has support; items older than 90 days are explained; adjustments were posted; and the adjusted balance agrees with the general ledger cash account. Approval is signed and dated.

## 3. Part B — Sub-ledger to general ledger reconciliation

| Sub-ledger | Reconcile to | Common causes of difference | Action |
|---|---|---|---|
| Payables (supplier balances) | GL account `7110010` | Manual journals posted directly to the control account; invoices posted in a different period | Block direct posting to control accounts; correct with cut-off journal |
| Open commitments | Budget execution report (RPT-03) commitments column | Commitments closed in procurement but not in finance | Close stale commitments after confirming with the requesting unit |
| Suspense | GL account `7900010` and the suspense ageing report | Items cleared without a reversing entry | Clear with a journal referencing the original receipt |

For each, the procedure is the same: run the sub-ledger total and the GL balance at the same date; list and explain each difference; correct errors by journal; sign off.

## 4. Escalation

| Condition | Escalate to | When |
|---|---|---|
| Reconciliation not approved by day 10 | Accounting Officer | Day 11 |
| Unexplained difference remains | Chief Accountant, then Accounting Officer | Immediately |
| Reconciling item older than 90 days | Chief Accountant (written explanation on file) | At month-end review |
| Suspected irregular transaction | Accounting Officer and internal audit | Immediately |

## 5. Evidence retained

Signed reconciliation statement, bank statement, cash book report, list of reconciling items with support, journals posted, and the sub-ledger to GL schedules. Retained for the statutory period and available to internal and external audit.

## 6. Worked example

See [`bank_reconciliation_worked_example.xlsx`](bank_reconciliation_worked_example.xlsx): cash book RWF 160,040k less bank charges RWF 45k = RWF 159,995k; bank RWF 171,375k plus uncredited receipts RWF 3,620k less unpresented payments RWF 15,000k = RWF 159,995k. Difference nil.
