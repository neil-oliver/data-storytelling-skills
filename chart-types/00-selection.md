---
scope: Pick a chart form from the analytical task.
use_when: Choosing which chart to build.
aliases:
  - Chart selection
tags:
  - data-viz
  - chart-types
  - chart-selection
  - decision-guide
  - chart-taxonomy
keywords:
  - chart selection
  - choosing a chart type
  - comparison charts
  - change over time
  - part-to-whole charts
  - distribution charts
  - correlation charts
  - flow and process charts
  - geospatial charts
  - small multiples
---

# Chart selection

## Task → form

- **Comparison across categories** → bars, columns, dot/lollipop plots. → [[comparison]]
- **Change over time** → line or area; two points → slope; ranking over time → bump. → [[change-over-time]]
- **Part-to-whole** → pie (≤5), waffle, stacked / 100% stacked bar, treemap, ternary (3 parts). → [[part-to-whole]]
- **Distribution / spread** → histogram, box, strip/beeswarm, ECDF, KDE, violin, ridgeline. → [[distribution]]
- **Correlation** → scatter; overplotting → hexbin/density; add regions → quadrant. → [[correlation]]
- **Ranking / deviation** → sorted bars; signed gap → diverging bars; survey → Likert. → [[ranking-and-deviation]]
- **Flow / process / drop-off** → funnel, sankey, waterfall. → [[flow-and-process]]
- **Value across a matrix** → heatmap. → [[matrix-and-heatmap]]
- **Geographic pattern** → choropleth (rates only), flow map, isochrone. → [[geospatial]]
- **Single headline value** → big number, bullet, gauge, progress. → [[single-value]]
- **Uncertainty / forecast** → confidence band or fan chart. → [[change-over-time]]
- **Many series or cohorts at once** → small multiples. → [[small-multiples]]
- **Exact values for lookup** → table. → [[tables]]
- **Cyclical or niche** → radial, polar, hemicycle (sparingly). → [[specialized]]

## Selection rules

- Match the form to the message so the insight is unmissable.
- Choose the form by the question: difference, total, ranking, spread, flow, or story.
- Decide whether the reader wants exact values or overall direction; design for one, not both.
- Know each form's limitations before choosing it, not just its strengths.
- For many small differences favor exact labels; for one dominant pattern favor uniform encoding.
- Never make one chart serve both discovery and direction; the hybrid goes unused.
- Treat the bar chart as the reliable default; reach for novel forms only when they earn it.
- Animate over time or space only when the shifting distribution is the insight.
- For precise two-moment comparison prefer small multiples, static maps, or tables over animation.
- Pick the form that supports your point, then verify it stays honest.
- When the default form is cluttered or off-message, reframe it — see [[elevation-swaps]].

Related: [[elevation-swaps]] · [[so-what]]
