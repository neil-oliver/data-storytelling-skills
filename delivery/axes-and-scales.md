---
scope: Design axes, baselines, and scales.
use_when: Setting axis ranges, gridlines, ticks, or choosing a scale.
---

# Axes & scales

- Label every axis with both its variable and its unit of measurement.
- Never use arbitrary placeholder labels like A, B, C.
- Anchor scales at a labeled, meaningful baseline so direction reads instantly.
- Start bar and area value axes at zero; truncating exaggerates differences.
- Line charts may omit zero to zoom in and reveal patterns.
- Never break or truncate a value axis; it distorts differences.
- Set the axis window intentionally; start and end frame the whole narrative.
- Choose a range proportionate to the data so effect size reads truthfully.
- If a non-zero baseline is unavoidable, disclose the axis range prominently.
- Annotate axis endpoints with meaning (higher/lower, before/after) so readers skip mental math.
- Avoid negative axis values; use a labeled split axis with plain-language directions instead.
- Anchor an index scale by labeling the 1.0 (or 100) baseline as the average.
- Prefer a single axis over two when one scale suffices.
- Avoid dual y-axes when both series share the same unit.
- Use a log scale for data spanning several orders of magnitude; label it, and avoid it for audiences who read it as linear.
- Show units once at the top tick, not on every gridline.
- Use enough ticks to read values, but not so many they crowd.
- Mute gridlines, ticks, and axis labels so they support, not compete.
- Include gridlines only when viewers must estimate precise values; drop the value axis once data labels give exact values.
- Avoid 45-degree rotated labels; switch to horizontal bars for long labels.
- Give each ternary component its own axis with a consistent tick direction.
- Share one axis and scale across compared panels.
- Extend the time window far enough to expose the seasonal pattern.

Related: [data](../data.md) · [anti-patterns](../anti-patterns.md)
