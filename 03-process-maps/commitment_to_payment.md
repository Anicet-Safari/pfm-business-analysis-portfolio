# Commitment-to-Payment (Expenditure) Process

*Author: Anicet Safari, CPA · Illustrative work sample, October 2026*

## Process map

```mermaid
flowchart LR
  subgraph USER[Requesting unit]
    U1[Raise purchase requisition<br/>with full COA coding]
    U5[Receive goods / services<br/>and record goods received note]
  end
  subgraph PROC[Procurement]
    P1[Select supplier per<br/>procurement rules]
    P2[Issue purchase order /<br/>contract]
  end
  subgraph FIN[Finance / Accounts]
    F1{Budget available?<br/>C-04}
    F2[Create commitment]
    F3[Receive invoice]
    F4{3-way match:<br/>PO = GRN = invoice?<br/>C-07}
    F5[Approve payment voucher<br/>C-08]
    F6[Post liability and<br/>release commitment]
  end
  subgraph TRE[Treasury]
    T1[Execute payment from<br/>Treasury Single Account<br/>C-09]
    T2[Post payment; bank<br/>statement to reconciliation]
  end
  U1 --> F1
  F1 -- No --> U1
  F1 -- Yes --> F2 --> P1 --> P2 --> U5 --> F3 --> F4
  F4 -- No: query --> F3
  F4 -- Yes --> F6 --> F5 --> T1 --> T2
```

## Steps

| # | Step | Actor | System event | Control |
|---|---|---|---|---|
| 1 | Raise requisition with full COA code | Requesting unit | Requisition record | `C-06` Combination validation rules (folder 01) |
| 2 | Check funds availability and create commitment | Finance | Commitment reduces available budget | `C-04` Hard stop if available budget is insufficient |
| 3 | Procure and issue PO / contract | Procurement | PO linked to commitment | Segregation: requester ≠ procurement officer |
| 4 | Receive goods / services | Requesting unit | Goods received note (GRN) | Receiver ≠ person who raised the PO |
| 5 | Receive and match invoice | Finance | Invoice matched to PO and GRN | `C-07` Three-way match with tolerance; mismatch blocks payment |
| 6 | Post liability; release commitment | Finance | Dr expense / Cr payables; commitment closed | Automatic; no manual liability posting allowed |
| 7 | Approve payment voucher | Authorised officer | Voucher approved | `C-08` Approval limits by amount; preparer ≠ approver |
| 8 | Pay | Treasury | Dr payables / Cr TSA | `C-09` Payee bank details from verified supplier master only |
| 9 | Reconcile | Treasury / Accounts | Bank statement imported | `C-10` Monthly bank reconciliation (folder 07) |

## Key data objects

Requisition → Commitment → Purchase order → Goods received note → Invoice → Payment voucher → Payment → Bank statement line. Each object carries the reference of the one before it, so any payment can be traced back to the budget line it consumed.

## Exceptions handled

| Exception | Handling |
|---|---|
| Invoice exceeds PO by more than tolerance | Blocked; requires PO amendment and a new funds check |
| Partial delivery | Partial GRN; invoice matched to quantity received; commitment stays open for the balance |
| Supplier bank details changed | Change only through supplier master workflow with independent verification (`C-09`) |
| Year-end open commitments | Listed for review; carried forward or cancelled per fiscal rules |
