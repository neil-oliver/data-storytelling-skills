---
scope: Show how values move over time.
use_when: The x-axis is time, or the story is a trend, turning point, rank shift, or forecast.
---

# Change-over-time charts

## Line
- Use line charts for value or trend over time.
- Keep to one to three lines; five is the ceiling before spaghetti — highlight one or split to small multiples.
- Recolor only the message-carrying series; mute the rest to gray.
- Plot a prior-year or peer benchmark line to separate your moves from market-wide ones.
- Prefer LOESS or a moving average over connect-the-dots for dense, noisy trends; keep raw data faint behind it.
- Avoid LOESS on thin data, sharp shifts, seasonality, or when you need precision.
- Break the series at data gaps with dashed segments; never interpolate silently.
- Render forecast segments dashed and actuals solid, separated by a labeled divider.
- Plot the running cumulative level, not just per-step percent deltas, to expose drift.
- Never start a trend line at a known outlier.
- Use smooth curves only for gentle trends; use straight segments for sharp shifts.
- Connect points with a line only when values are sequential.
- Increase line contrast where multiple lines cross or overlap.
- Distinguish similar or overlapping lines with dashed, dotted, and solid styles.
- Show point markers only when time intervals are irregular or sparse.

## Area
- Use area charts to emphasize total volume across a trend.
- Place the most important area series at the bottom for a stable baseline.
- Anchor a filled area chart's baseline at zero.
- Use a normalized (100%) stacked area to show category proportions of a whole over time.
- Don't overlap many filled areas; switch to lines or small multiples.

## Slope
- Use a slope chart for change between exactly two time points; prefer it over grouped bars.
- Avoid slope charts for many categories, unordered categories, or close endpoint labels.
- Don't force a zero baseline; prioritize trend visibility.

## Bump & rank
- Use a bump or rank chart for rank changes across three or more periods.
- Avoid rank charts when the gaps between values, not the order, are the story.

## Uncertainty & forecasts
- Show projections as a confidence band or fan chart, not a single forecast line.
- Widen fan-chart bands into the future; keep the central path dashed.
- Overlay many forecast vintages against one dark actual line to expose bias.

## Difference between two series
- Fill the area between two crossing lines, switching color at the crossover.
- Shade the gap between two converging lines to show the difference directly.

## Step
- Use a step chart for cumulative totals that jump in discrete lumps.
- Use step lines for discrete status levels that hold, then jump between states.

## Sparkline
- Use sparklines for direction and pattern; always pair with the absolute value for scale.

## Ribbon
- Use a ribbon to show composition over time and how ranks change.

## Combination (dual-axis)
- Use a line-and-bar combo for two measures on dual axes.
- Avoid dual y-axes when both series share the same unit — the relationship becomes a scale artifact.

Related: [small-multiples](small-multiples.md) · [annotations](../delivery/essentials.md#annotations) · [axes-and-scales](../delivery/essentials.md#axes-and-scales)
