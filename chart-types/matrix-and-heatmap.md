---
scope: Encode values across a two-dimensional matrix as color.
use_when: The story is a pattern across two categorical axes (e.g. rows × time).
---

# Matrix & heatmap charts

## Heatmap
- Use a heatmap to show one metric across two categorical axes.
- Print the underlying value inside each cell for exact readouts.
- Order rows and columns meaningfully (by value, cluster, or time), not alphabetically.
- Use a sequential scale for magnitude and a diverging scale around a meaningful midpoint.
- Map darker, more saturated cells to higher values; a single-hue gradient stays colorblind-friendly.
- Size cells for legibility — neither too narrow nor too wide.
- Label the color scale's meaning and units.
- Keep the cell grid quiet; let color carry the signal.

## Density matrix
- For thousands of overplotted points, use a hexbin — see [correlation.md](correlation.md).

Related: [delivery/color-and-emphasis.md](../delivery/color-and-emphasis.md) · [delivery/formatting-and-ordering.md](../delivery/formatting-and-ordering.md)
