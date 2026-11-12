# Report Data and Acceptance Contract

**Version 0.1.0** · 2026-11-12 · Scaffold / not a completed demo

## Grain

Budget fixture: one row per month and department. Request fixture: one row per RequestId. Current sample contains November 2026 only. Use Department and Month as conformed filter keys; do not sum a repeated department budget across request rows.

## Definitions

- Budget: sum of budget fixture amounts.
- Already spent: sum of the separate already-spent fixture amounts.
- Approved requests: sum request Amount where Status is Approved.
- Pending requests: sum request Amount where Status is Pending.
- Available budget: Budget minus Already spent minus Approved requests. Pending and Rejected requests do not reduce it.

## Independent starting values

| Department | Budget | Already spent | Approved requests | Pending requests | Available budget |
|---|---:|---:|---:|---:|---:|
| Operations | 30000 | 22000 | 900 | 0 | 7100 |
| Sales | 20000 | 13500 | 0 | 1200 | 6500 |
| Engineering | 45000 | 38000 | 3500 | 0 | 3500 |
| Total | 95000 | 73500 | 4400 | 1200 | 17100 |

These are fixture expectations, not observed Power BI results. If Sales request R003 is approved, Approved requests become 5600, Pending becomes 0 and total Available budget becomes 15900. Verify this after the implemented refresh process; preserve a separate initial fixture/version for comparison.
