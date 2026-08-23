---
scope: Reframe a default chart into a sharper one.
use_when: The obvious chart is cluttered, off-message, or hides the point.
---

# Elevation swaps

When you see the pattern on the left, consider the swap on the right.

## Reveal what a summary hides
- Mean bars hiding spread → distribution view (box, strip, beeswarm, KDE, violin, ridgeline).
- One value per category hiding range → box plots or dumbbells.
- Bars of averages → plot individual points to expose spread and outliers.
- Heavy overplotting → hexbin or density map instead of raw dots.

## Show movement, difference, and flow
- Grouped bars over two periods → slope chart, to surface movers and rank change.
- Two paired values per category → dumbbell instead of two bar charts.
- The gap between two series → plot the signed difference directly (diverging bar).
- Two crossing or converging lines → shade the difference area, switching color at the crossover.
- A total redistributing between categories → flow diagram (sankey), not paired bars.
- A start-to-end value → waterfall of step changes, not a bar per period.
- Per-step percent deltas → running cumulative level.

## Add context and uncertainty
- A bare KPI → add goal percent, trend, or vs-prior context.
- A single forecast line → confidence band or fan chart.
- A bare bar vs a target → bullet chart.
- A scatter of positions → labeled quadrants naming each region.
- A table snapshot → add inline sparklines for each row's trend.

## Untangle and focus
- Many overlapping lines (spaghetti) → small multiples with shared axes, one series per panel.
- Overlapping series where one matters → recolor only the signal, gray the rest.
- Long-tail ranking → roll minor items into "Others", keep the top.
- Dense noisy trend → LOESS or moving-average smoothing over the faded raw data.

## Fix weak defaults
- Cluttered pie → sorted bar (ranking) or waffle (part-to-whole).
- Word cloud → bar chart of frequencies.
- Decorative 3D → flat 2D that doesn't distort heights.
- Dual-axis chart → two split charts sharing the x-axis.
- Uniform dashboard grid → labeled sections with a sized-up primary metric.
- Raw counts on a map → choropleth of a normalized rate.
- Animation for precise comparison → small multiples of the key moments.

## When to break convention
- For scroll-stopping media, a striking custom form can beat a plain bar — keep exact value labels.

Related: [00-selection](chart-types/00-selection.md)
