# Inventory Metrics and Data Validation Guide

## Core metrics
| Metric | Definition | Interpretation note |
|---|---|---|
| Closing stock | Opening stock + receipts - issues ± adjustments | Reconcile with the source ledger |
| Inventory turnover | Cost of goods sold / average inventory value | Use matching periods and valuation basis |
| Days of inventory | Average inventory / daily usage or COGS | State the denominator explicitly |
| Stockout rate | Stockout item-days / total item-days | Define what qualifies as a stockout |
| Reorder flag | Available stock <= reorder point | Confirm lead time and safety-stock policy |

## Validation checks
- Ensure SKU and warehouse keys are stable and non-null.
- Detect duplicate transaction IDs.
- Flag negative quantities and unexplained adjustments.
- Confirm units of measure before aggregating quantities.
- Reconcile opening and closing balances by SKU and location.
- Check transaction timestamps and reporting cut-off rules.

## Analysis questions
1. Which SKUs contribute most to inventory value?
2. Which locations experience repeated stockouts?
3. How does supplier lead time relate to replenishment risk?
4. Which slow-moving items may need review?

## Caveats
Do not label an item obsolete using age alone. Consider demand, seasonality, lead time, and business policy.