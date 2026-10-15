# Delivered Work — Financial Management Workbook (Fractional CFO engagement)

*Author: Anicet Safari, CPA*

## The engagement

| Item | Detail |
|---|---|
| Client | A small Kigali company (SiliconHills Ltd) |
| Role | Part-time Fractional CFO, pro bono |
| Period | May 2023 to date |
| Evidence | Certificate of good completion signed by the Managing Director (submitted with the application) |

## The problem

The company is run by its owner-manager and needed a simple, reliable way to record transactions, know its cash position, control spending against a budget and produce financial statements for the owner and for tax and statutory filing.

## What I did

1. **Requirements analysis.** Reviewed with the Managing Director how money came in and went out, what decisions he needed information for, and what the Rwanda Revenue Authority and other filings required.
2. **Chart of accounts design.** Defined a short, numbered chart of accounts matched to the company's activities, with each account mapped to a statement line and a cash-flow class.
3. **Workbook design and build.** Built an Excel workbook with a single entry point (the cash book) from which every report is calculated: budget versus actual, income statement, balance sheet, cash flow summary and bank reconciliation, plus automatic checks.
4. **User training.** Trained the Managing Director to record transactions and read the reports himself.
5. **Ongoing Fractional CFO support.** Monthly review of the books, management accounts, cash-flow monitoring, annual financial statements and support on RRA filings.

## What is in this folder

| File | Content |
|---|---|
| [`financial_management_workbook_template.xlsx`](financial_management_workbook_template.xlsx) | **A rebuilt template of the workbook design delivered to the client** (cash-book based, as delivered). The client's own file contains confidential financial data and is not published. This version reproduces its structure and logic with a fictional company and fictional figures. |
| [`financial_management_workbook_IFRS_for_SMEs.xlsx`](financial_management_workbook_IFRS_for_SMEs.xlsx) | **Extended version, prepared October 2026 (not part of the client delivery).** Shows how the same design scales to accrual accounting under the IFRS for SMEs Accounting Standard, with an integrated three-statement forecast model. Fictional company and figures. |

### Extended IFRS for SMEs version (Rwanda)

| Layer | Sheets |
|---|---|
| Entity | Company_Info — corporate information and statement of directors' responsibilities under Law Nº 007/2021 of 05/02/2021 governing companies |
| Inputs | Settings (Rwandan tax and payroll rates), COA, Opening_TB, Sales_Register, Purchase_Register, Payroll (PAYE and RSSB), Cash_Book, Fixed_Assets, Loan_Schedule, Tax_Computation, Journals |
| Ledger | Trial_Balance — every account built by formula from the input sheets |
| Statement of financial position | Non-current and current assets; equity; non-current liabilities (borrowings, deferred tax); current liabilities (trade and other payables, current portion of borrowings, PAYE and social security payable, current income tax) |
| Statement of comprehensive income | Revenue, cost of sales, gross profit, other income, administrative and selling expenses, operating profit, finance income and costs, profit before tax, income tax expense, profit for the year, other comprehensive income |
| Other statements and notes | Statement of changes in equity, statement of cash flows (indirect method), and 13 notes including expenses by nature, income tax reconciliation, borrowings, payables and share capital |
| Rwandan rules | Corporate income tax 28%; wear and tear 50% (computers and ICT) and 25% (other assets) on reducing balance; deferred tax; quarterly prepayments; PAYE bands; RSSB pension, occupational hazards, maternity and CBHI; VAT registration threshold flag |
| Three-statement model | Actual year linked to the statements, plus a three-year forecast with assumptions, PPE and loan schedules, ratios, cash as the balancing figure and a balance check every year |
| Checks | 23 automatic tests covering the ledger, statements, notes, payroll, loan, tax computation and model |

Stated simplifications: no comparative prior-year column, VAT, impairment or provisions; prepayment amounts are illustrative inputs; the forecast holds deferred tax constant.

### Workbook structure

| Sheet | Purpose |
|---|---|
| Settings | Company, year, reporting month, opening balances, variance threshold |
| Chart_of_Accounts | 15 accounts with type, statement line and cash-flow class |
| Cash_Book | The only transaction-entry sheet; code validation from a drop-down list; running balance |
| Budget | Annual budget by account, phased by month |
| Budget_vs_Actual | Year-to-date budget, actual and variance for any month; flags variances beyond the threshold |
| Income_Statement, Balance_Sheet, Cash_Flow | Produced automatically from the cash book |
| Bank_Reconciliation | Agrees the cash book with the bank statement |
| Checks | Balance sheet balances; every transaction validly coded; cash flow agrees to cash book; budget report agrees to income statement; bank reconciled |

## Results for the client

- All transactions recorded and classified consistently.
- Cash position visible at any time.
- Spending monitored monthly against an approved budget.
- Financial statements available on time for the owner and for statutory filing.
- Strengthened compliance with tax and statutory reporting obligations.
- Stronger capacity of the Managing Director to manage the company's finances himself.

## Relevance to PFM system work

The same disciplines apply at government scale: chart of accounts design, a single source of transactions feeding all reports, budget control, built-in reconciliation and automated checks. Folders 01–07 show how I apply them to a public-sector context.
