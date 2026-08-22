---
scope: Format numbers and dates; style and order marks.
use_when: Setting number precision, units, styling, or sort order.
---

# Formatting & ordering

## Number & date formatting
- Round numbers to the precision the decision needs, not raw digits.
- Trim decimals and abbreviate large numbers (K, M) to declutter dashboards.
- Keep precise decimals for scientific, financial, or engineering data where rounding erodes credibility.
- Use thousands separators and consistent units.
- Fold units into tick labels (e.g. $50) when it aids clarity.
- Signal direction with an up or down arrow and percent, not just the value.
- Format dates and axis ticks consistently; avoid ambiguous formats.

## Line & bar styling
- Distinguish actuals from forecast with solid vs dashed styling.
- Keep histogram bars gap-free so adjacent bins read as a continuous range.

## Sorting & ordering
- Sort categorical bars by value unless a natural or fixed order exists.
- Keep category order consistent across related charts for comparison.
- Order stacked segments by size or a stable, meaningful sequence.
- Cluster related categories together instead of scattering them along the axis.

Related: [labels-and-legends](labels-and-legends.md) · [comparison](../chart-types/comparison.md)
