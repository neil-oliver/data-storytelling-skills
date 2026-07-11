---
scope: Pick a chart form from the analytical task.
use_when: Choosing which chart to build.
---

# Chart selection

## Task → form

- **Comparison across categories** → bars, columns, dot/lollipop plots. → [comparison.md](comparison.md)
- **Change over time** → line or area; two points → slope; ranking over time → bump. → [change-over-time.md](change-over-time.md)
- **Part-to-whole** → pie (≤5), waffle, stacked / 100% stacked bar, treemap, ternary (3 parts). → [part-to-whole.md](part-to-whole.md)
- **Distribution / spread** → histogram, box, strip/beeswarm, ECDF, KDE, violin, ridgeline. → [distribution.md](distribution.md)
- **Correlation** → scatter; overplotting → hexbin/density; add regions → quadrant. → [correlation.md](correlation.md)
- **Ranking / deviation** → sorted bars; signed gap → diverging bars; survey → Likert. → [ranking-and-deviation.md](ranking-and-deviation.md)
- **Flow / process / drop-off** → funnel, sankey, waterfall. → [flow-and-process.md](flow-and-process.md)
- **Value across a matrix** → heatmap. → [matrix-and-heatmap.md](matrix-and-heatmap.md)
- **Geographic pattern** → choropleth (rates only), flow map, isochrone. → [geospatial.md](geospatial.md)
- **Single headline value** → big number, bullet, gauge, progress. → [single-value.md](single-value.md)
- **Uncertainty / forecast** → confidence band or fan chart. → [change-over-time.md](change-over-time.md)
- **Many series or cohorts at once** → small multiples. → [small-multiples.md](small-multiples.md)
- **Exact values for lookup** → table. → [tables.md](tables.md)
- **Cyclical or niche** → radial, polar, hemicycle (sparingly). → [specialized.md](specialized.md)

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
- When the default form is cluttered or off-message, reframe it — see [patterns/elevation-swaps.md](../patterns/elevation-swaps.md).

Related: [patterns/elevation-swaps.md](../patterns/elevation-swaps.md) · [../so-what.md](../so-what.md)
