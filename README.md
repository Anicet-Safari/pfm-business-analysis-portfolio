# Public Financial Management — Business Analysis Portfolio

**Anicet Safari, CPA (ICPAR), FMVA, MBA (Finance)**
Kigali, Rwanda · anice.safari@gmail.com · [linkedin.com/in/safari-anicet-cpa](https://www.linkedin.com/in/safari-anicet-cpa)

This repository holds practical business-analysis work on public financial management (PFM) systems: chart of accounts design, financial statement and report specifications, budgeting and accounting process maps, expenditure and revenue workflows, a functional specification for a financial-system module, user stories with acceptance criteria, an internal controls matrix and reconciliation procedures.

## About this work

- **Author.** Every document here was written by me. Each file carries an author line.
- **Status.** Folder 08 describes real work delivered to a client; the workbook in it is a rebuilt template with fictional figures, because the client's own file is confidential. The documents in folders 01–07 are **illustrative work samples** I prepared in October 2026 to show how I approach PFM business analysis; they are not deliverables from a client engagement.
- **Data.** All entities, amounts and transactions are fictional. No data from any employer or client is used.
- **Standards referenced.** IPSAS (cash and accrual basis, including IPSAS 24 on budget reporting), IMF GFSM 2014 economic classification, UN COFOG functional classification, COSO 2013 internal control framework, swimlane process maps (in Mermaid, which renders on GitHub) and INVEST / Given-When-Then for user stories.

## Index — mapped to the Terms of Reference

| # | ToR item | Folder | Main deliverables |
|---|---|---|---|
| 1 | Chart of accounts design or review | [01-chart-of-accounts](01-chart-of-accounts) | Segment design note, segment code lists, account-combination validation rules |
| 2 | Design of financial statements and reports; financial reporting requirements | [02-financial-statements-and-reports](02-financial-statements-and-reports) | Report specifications (IPSAS cash basis, budget vs actual), worked statement workbook with trial balance tie-outs |
| 3 | Budgeting and accounting business processes; expenditure and revenue workflows | [03-process-maps](03-process-maps) | Budget execution, commitment-to-payment and revenue receipting process maps with control points |
| 4 | Functional specifications for financial systems | [04-functional-specifications](04-functional-specifications) | Functional specification for a bank reconciliation module |
| 5 | Analytical and functional deliverables supporting system implementation | [05-user-stories](05-user-stories) | User stories with acceptance criteria; requirements traceability matrix |
| 6 | Internal control processes | [06-internal-controls](06-internal-controls) | Commitment-to-payment controls matrix (COSO-mapped) |
| 7 | Reconciliation procedures | [07-reconciliation-procedures](07-reconciliation-procedures) | Bank and sub-ledger reconciliation procedure with a worked example |
| 8 | Proven practical work | [08-delivered-work](08-delivered-work) | Case study of the financial management workbook delivered under my Fractional CFO engagement (May 2023 to date), with a rebuilt template of the workbook |

## How the pieces connect

The documents follow one thread, the way they would on a real system implementation:

1. The **chart of accounts** (01) defines the codes every transaction carries.
2. The **process maps** (03) show where transactions start, who approves them and which controls apply.
3. The **controls matrix** (06) lists those controls, their owners and how a system enforces them.
4. The **functional specification** (04) and **user stories** (05) turn one process (bank reconciliation) into testable system requirements, traced in the traceability matrix.
5. The **reconciliation procedure** (07) is the user-side procedure that the module in 04 automates.
6. The **report specifications** (02) define the outputs, each tied back to the trial balance.

## Related professional background

- **CPA (ICPAR)**, FMVA (CFI), MBA in Finance.
- Four and a half years reviewing companies' filed financial statements and annual returns for compliance at the Rwanda Development Board.
- Bookkeeping in Tally ERP9 at an accounting firm; hands-on use of QuickBooks, Sage and Odoo.
- Since 2023, part-time pro bono Fractional CFO support to two small companies, including designing a financial management workbook (chart of accounts, cash book, budget vs actual, automated statements).
