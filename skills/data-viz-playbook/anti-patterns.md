---
scope: Honesty and clarity failures to avoid.
use_when: Reviewing a chart before shipping; catching distortion, clutter, and bias.
---

# Anti-patterns

## Scale & axis
- Never truncate a bar-chart value axis; truncation exaggerates differences.
- Never break a value axis; it distorts real variation.
- Avoid axis ranges that make trivial gaps look dramatic or real gaps look flat.
- Never start a time series at an outlier or peak to manufacture a trend.
- Never crop the time window to a favorable start that fakes or hides a trend.
- Never compress or stretch gridlines to inflate certain values.
- Avoid dual y-axes; independent scales fake correlation between unrelated series.

## Summary & statistics
- Never plot only the mean; equal averages can hide very different distributions.
- Distrust a single summary statistic; the underlying distribution can overturn it.
- For skewed data, show both mean and median so viewers aren't misled.
- A gain and loss of equal percent leave you below start; never treat them as offsetting.

## Data & framing
- Show full context; never cherry-pick data, facts, or a date range to fit a claim.
- Never omit categories or points that would reframe the comparison.
- Compare only items measured under identical methodology and conditions.
- Don't infer causation from a single correlated change.
- Technically true facts stripped of context still create a false impression.

## Cognitive bias
- Bias enters at framing, before chart type or color is chosen — name your assumption.
- Avoid confirmation bias; seek disconfirming evidence, not just data that fits.
- Avoid survivorship bias; include cases that dropped out before the final stage.
- Avoid availability bias; weight all relevant periods, not just recent ones.
- Avoid anchoring; don't over-weight the first data point you see.

## Encoding & form
- Avoid 3D bars, pies, or perspective; extrusion distorts proportions and hides values.
- Avoid pie charts when slice magnitudes must be compared; prefer a sorted bar.
- Avoid radar/spider charts; connecting lines and areas mislead across categories.
- Avoid word clouds; non-linear font scaling hides patterns.
- Avoid rank charts when the gaps between values, not the order, are the story.
- Avoid waterfalls with too many steps; they clutter.
- Avoid LOESS on small, thin, or sharply-shifting data; it overfits.
- Avoid rainbow-coloring categories that carry no meaning.
- Avoid loaded color (green=good, red=alarm) that pushes a verdict onto neutral data.

## Composition & reading
- Never overload one chart with multiple equal-priority messages.
- Never make one chart answer both discovery and direction.
- Avoid uniform-size tile grids that make everything feel equally important.
- Don't mix unrelated metrics on one view; drop tiles that don't serve its purpose.
- Avoid designs that dramatize a single dip and demand instant reaction.
- Don't annotate a movement smaller than the metric's typical wobble.
- Don't split your argument into prose; embed it in the chart.

Related: [so-what](so-what.md) · [axes-and-scales](delivery/axes-and-scales.md) · [data](data.md)
