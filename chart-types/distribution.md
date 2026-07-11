---
scope: Show spread, shape, and outliers of values.
use_when: The story is the distribution itself, not a single summary number.
---

# Distribution charts

Averages hide structure — reach here whenever spread, shape, or outliers matter. Choosing among these: box plots for lay audiences; KDE, violin, or ridgeline for stat-literate ones; strip or beeswarm to keep every point.

## Histogram
- Use a histogram to reveal one numeric variable's distribution shape.
- Use equal-width, gap-free bins spanning the full min to max.
- Tune bin count between noise and oversimplification until skew or modes appear.
- Name skew by the long thin tail's direction, not the peak.
- Label shape plainly: one peak symmetric, two peaks bimodal, flat uniform.

## Box plot
- Use a box plot to compare groups' medians, spread, and outliers compactly.
- Annotate what box, whiskers, and dots mean for non-technical readers.
- Prefer box plots over bars-of-averages when spread and skew matter.

## Strip / dot & beeswarm
- Use a strip or dot plot to show each group's points and outliers.
- Use a beeswarm when spread across individual units is the story.
- Arrange dots without overlap so the distribution reads instantly.
- Scale dot size by a relevant variable so weight reads visually.

## ECDF
- Overlay ECDF curves to compare full distributions and percentiles across groups.

## KDE / density
- Overlay KDE density curves with semi-transparent fills to compare shapes.

## Violin
- Use violin plots when both distribution shape and summary stats matter.

## Ridgeline
- Use ridgeline plots to compare many distributions compactly.
- Avoid ridgelines with heavy overlap or too few groups.

## Butterfly (back-to-back)
- Use a butterfly chart to mirror two distributions across a shared center.

## Labeling
- Label each group with its defining threshold and sample size n.

Related: [patterns/elevation-swaps.md](../patterns/elevation-swaps.md) · [data.md](../data.md) · [so-what.md](../so-what.md)
