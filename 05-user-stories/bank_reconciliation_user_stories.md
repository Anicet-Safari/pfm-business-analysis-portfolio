# User Stories — Bank Reconciliation Module

*Author: Anicet Safari, CPA · Illustrative work sample, October 2026*

Stories follow the INVEST criteria. Acceptance criteria use Given / When / Then so they can be turned directly into test cases. Requirement IDs refer to the functional specification in folder 04.

---

### BR-US-01 Import a bank statement
**As a** Reconciliation Officer **I want** to import the monthly bank statement **so that** I can reconcile it with the cash book without retyping it.
*Covers: FR-01, FR-03*

- **Given** a statement file for a registered account in the agreed format, **when** I import it, **then** every line is stored with value date, booking date, amount, sign, reference and narrative, and the line count and totals shown equal the file's control totals.

### BR-US-02 Reject an invalid statement
**As a** Reconciliation Officer **I want** the system to reject a statement that does not follow on from the last one **so that** no transactions are missed or doubled.
*Covers: FR-02*

- **Given** the last imported statement closed at 1,250,000, **when** I import a statement whose opening balance is 1,240,000, **then** the import is rejected with the message "Opening balance does not equal previous closing balance (difference 10,000)".
- **Given** a statement for 1–31 March is already imported, **when** I import one covering 15–31 March, **then** the import is rejected as an overlapping period.

### BR-US-03 Match by reference automatically
**As a** Reconciliation Officer **I want** items with the same reference and amount matched automatically **so that** I only review true exceptions.
*Covers: FR-04, FR-07*

- **Given** a payment of 4,500,000 with reference PV-2026-0145 in the cash book and a statement debit of 4,500,000 with reference PV-2026-0145, **when** auto-match runs, **then** the two are matched and the match shows "Rule 1".
- **Given** the same reference but amounts of 4,500,000 and 4,050,000, **when** auto-match runs, **then** they are **not** matched and both appear as unmatched.

### BR-US-04 Match by amount within a date window
**As a** Reconciliation Officer **I want** items matched on amount within a short date window when references are missing **so that** bank entries without our reference still reconcile.
*Covers: FR-05*

- **Given** one cash book receipt of 320,000 on 10 March and one statement credit of 320,000 on 12 March with no reference, **when** auto-match runs with a ±3-day window, **then** they are matched under "Rule 2".
- **Given** two cash book receipts of 320,000 on 10 and 11 March and one statement credit of 320,000 on 12 March, **when** auto-match runs, **then** nothing is matched, because there is more than one candidate.

### BR-US-05 Record bank charges from the statement
**As a** Reconciliation Officer **I want** to record bank charges found on the statement as a cash book entry **so that** the cash book reflects them.
*Covers: FR-08*

- **Given** an unmatched statement debit of 12,500 described "Monthly account fee", **when** I create an adjustment with economic code for bank charges, **then** a cash book entry of 12,500 is posted, coded and matched to the statement line, and the audit trail shows my user ID.

### BR-US-06 Post unidentified receipts to suspense
**As a** Reconciliation Officer **I want** unidentified receipts posted to suspense with a reason **so that** they are tracked until cleared.
*Covers: FR-09*

- **Given** a statement credit of 75,000 with no matching bill or reference, **when** I post it to suspense with reason "Payer not identified", **then** it is posted to account 7900010 and appears on the suspense ageing report in the 0–30 day band.

### BR-US-07 Block submission while a difference remains
**As a** Chief Accountant **I want** reconciliations with unexplained differences blocked from submission **so that** only complete reconciliations reach me.
*Covers: FR-10*

- **Given** bank balance + uncredited receipts − unpresented payments ± other items differs from the cash book balance by 3,000, **when** the officer clicks Submit, **then** submission is blocked and the difference of 3,000 is shown.
- **Given** the difference is zero, **when** the officer clicks Submit, **then** the reconciliation is routed to the approver.

### BR-US-08 Approve and lock the period
**As a** Chief Accountant **I want** to approve the reconciliation and lock the period **so that** reconciled figures cannot change afterwards.
*Covers: FR-11, FR-12*

- **Given** a submitted reconciliation that I did not prepare, **when** I approve it, **then** its status becomes Approved and no matching or back-dated cash book posting is allowed for that account and period.
- **Given** I prepared the reconciliation myself, **when** I try to approve it, **then** the system refuses: "Preparer cannot approve own reconciliation".

---

See [`traceability_matrix.csv`](traceability_matrix.csv) for the requirement → story → test → control links.
