# Chart of Accounts — Segment Design for a Government IFMIS

*Author: Anicet Safari, CPA · Illustrative work sample, October 2026 · Fictional codes*

## 1. Purpose

This note designs a segmented chart of accounts (COA) for a central-government financial management information system (IFMIS). The COA must let one transaction answer four questions at once: **who** spent (administrative unit), **on what** (economic nature), **for what purpose** (function and programme) and **with whose money** (source of funds). Budget, accounting and reporting all use the same codes, so the budget can be compared with actuals line by line.

## 2. Design principles

1. **One code block for budget and accounts.** The budget is prepared and executed on the same segments the ledger uses. This is what makes the budget-versus-actual statement (folder 02) possible without manual mapping.
2. **International classifications at the core.** The economic segment follows the IMF *Government Finance Statistics Manual 2014* (GFSM 2014). The functional segment follows the UN *Classification of the Functions of Government* (COFOG). This allows GFS and COFOG reporting without a separate mapping exercise.
3. **Segments are independent.** Each segment answers one question only. Meaning is never packed into another segment's digits.
4. **Hierarchical codes.** Each segment rolls up (for example, item → sub-item → group → class), so reports can be produced at any level.
5. **Controlled combinations.** Not every combination is valid. Validation rules (section 5) stop invalid postings at data entry, rather than after month-end.
6. **Room to grow.** Each level has spare code ranges so new entities, programmes or items do not force a redesign.

## 3. Segment structure

| # | Segment | Length | Question it answers | Example | Basis |
|---|---|---|---|---|---|
| 1 | Fund / source of funds | 2 | Whose money? | `10` Domestic revenue | National |
| 2 | Administrative unit | 6 | Who is responsible? | `030101` Ministry X, Planning and Statistics Unit | National |
| 3 | Economic classification | 7 | What is bought or received? | `2211010` Office supplies | GFSM 2014 |
| 4 | Function | 4 | For what purpose? | `0912` Primary education | COFOG |
| 5 | Programme / sub-programme | 5 | Which policy programme? | `04010` Basic education access | National |
| 6 | Location | 4 | Where? | `0102` District code | National |
| 7 | Project | 6 | Which externally financed or capital project? | `000000` = none | National |

Full code string: `FF-AAAAAA-EEEEEEE-FFFF-PPPPP-LLLL-JJJJJJ` (34 digits).

Example of a fully coded transaction (office supplies bought by a fictional directorate for primary education, domestic funds, no project):

```
10-030101-2211010-0912-04010-0102-000000
```

## 4. Economic segment hierarchy

The economic segment follows GFSM 2014 at the top levels and adds national detail below them.

| Level | Digits | Example code | Example name |
|---|---|---|---|
| Class | 1 | `2` | Expense |
| Category | 2 | `22` | Use of goods and services |
| Group | 3 | `221` | Office and general |
| Sub-group | 5 | `22110` | Office supplies and stationery |
| Item | 7 | `2211010` | Office supplies |

Top-level classes used: `1` Revenue, `2` Expense, `3` Transactions in non-financial assets, `4` Transactions in financial assets, `5` Transactions in liabilities, plus balance-sheet accounts for cash, receivables, payables and suspense. The sample code list is in [`economic_classification.csv`](economic_classification.csv).

## 5. Account combination rules

The full rule set is in [`combination_rules.md`](combination_rules.md). The main rules are:

- Revenue codes (class `1`) may only be used with a revenue-collecting administrative unit.
- Expense codes (class `2`) require a function and a programme; they may not use the default `0000` / `00000`.
- Capital codes (class `3`) require a project code other than `000000`.
- Externally financed funds (`20`–`29`) require a project code.
- Balance-sheet codes (cash, payables, suspense) do not carry function, programme or location codes.
- Every programme maps to exactly one function. The system validates the pair.

## 6. Review checklist (for reviewing an existing COA)

When reviewing an existing chart rather than designing a new one, I check:

| Area | Question | Typical finding |
|---|---|---|
| Coverage | Can every reporting requirement (GFS, COFOG, IPSAS notes, donor reports) be produced from the segments? | Donor reports need a project segment that is missing or optional |
| Overlap | Does any segment repeat information held in another? | Economic codes with an embedded function digit |
| Granularity | Are there items nobody budgets or posts to? | Hundreds of unused item codes |
| Suspense | Are suspense and miscellaneous accounts controlled and cleared? | "Other expenses" used for a large share of spending |
| Stability | Can codes change without breaking history? | Codes reused for different meanings across years |
| Mapping | Is there a documented mapping to GFS and COFOG? | Mapping kept in an analyst's spreadsheet only |

## Files

- [`coa_segments.csv`](coa_segments.csv) — segment definitions and sample values
- [`economic_classification.csv`](economic_classification.csv) — sample economic codes, GFSM 2014-aligned
- [`combination_rules.md`](combination_rules.md) — validation rules with test cases
