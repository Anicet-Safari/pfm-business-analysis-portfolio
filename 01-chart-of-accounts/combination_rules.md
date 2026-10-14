# Account Combination Validation Rules

*Author: Anicet Safari, CPA · Illustrative work sample, October 2026*

These rules run at data entry (journal, commitment, payment and receipt screens). A posting that breaks a rule is rejected with the message shown; it is not posted and corrected later.

## Rules

| ID | Rule | Applies when | Error message |
|---|---|---|---|
| CR-01 | Every segment must hold an active code for the posting date. | All postings | "Segment {name}: code {code} is not active on {date}." |
| CR-02 | Revenue codes (economic class `1`) may only be used by administrative units flagged as revenue-collecting. | Economic starts with `1` | "Unit {code} is not authorised to record revenue." |
| CR-03 | Expense codes (class `2`) need a function and a programme other than the defaults. | Economic starts with `2` | "Expense postings need a function and a programme." |
| CR-04 | The programme must map to the function entered. | Programme ≠ `00000` | "Programme {p} belongs to function {f1}, not {f2}." |
| CR-05 | Capital codes (class `3`) need a project code other than `000000`. | Economic starts with `3` | "Capital spending must be linked to a project." |
| CR-06 | Fund codes `20`–`29` (external) need a project code other than `000000`. | Fund in `20`–`29` | "Externally financed postings need a project code." |
| CR-07 | Balance-sheet codes (classes `6`, `7`) use the default function, programme and location. | Economic starts with `6` or `7` | "Balance-sheet accounts do not carry function, programme or location." |
| CR-08 | Postings to suspense (`79xxxxx`) need a reason code and are reported weekly until cleared. | Economic starts with `79` | "Suspense postings need a reason code." |
| CR-09 | Expense postings need available budget on the same fund, unit, economic sub-group and programme. | Commitments and payments | "Insufficient budget: available {amount}." |

## Test cases

| # | Combination | Expected | Rule tested |
|---|---|---|---|
| T1 | `10-030101-2211010-0912-04010-0102-000000` | Accept | — |
| T2 | `10-030101-2211010-0000-00000-0102-000000` | Reject | CR-03 |
| T3 | `10-030101-2211010-0721-04010-0102-000000` | Reject | CR-04 |
| T4 | `10-030101-3111010-0912-04010-0102-000000` | Reject | CR-05 |
| T5 | `20-030101-2211010-0912-04010-0102-000000` | Reject | CR-06 |
| T6 | `10-030101-1140010-0000-00000-0000-000000` | Reject | CR-02 (unit not revenue-collecting) |
| T7 | `10-030201-1140010-0000-00000-0000-000000` | Accept | — |
| T8 | `10-030201-6110010-0912-00000-0000-000000` | Reject | CR-07 |

## Design notes

- Rules CR-02 to CR-08 check the **structure** of the code string and can run without the budget. Rule CR-09 checks **funds availability** and needs the budget ledger. They are kept separate so structural errors are caught even before the budget is loaded.
- Each rule has an ID so it can be traced to user stories and test scripts (see folder 05).
