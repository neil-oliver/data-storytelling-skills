---
scope: Map of the data-visualization playbook — what lives where.
use_when: Locating the rule file for a specific decision.
---

# Data Visualization Playbook

A source-agnostic rule set for choosing and designing the right chart. Written for an LLM:
every line is a prescriptive rule, not prose. Load only the file that matches the decision in
front of you.

**How to use it:** the traversal procedure — the four-layer method, per-layer file loads, and
handoffs — lives in [SKILL.md](SKILL.md). This file is just the map.

## Map

- [SKILL.md](SKILL.md) — the method: how to traverse this corpus, layer by layer, as one agent or a chain.
- [data.md](data.md) — Layer 1: what to plot, and preparing it (selection, statistics, normalization, binning, missing data).
- `chart-types/` — Layer 2: pick a form. [00-selection.md](chart-types/00-selection.md) maps analytical task → form; then one file per category (comparison, change over time, part-to-whole, distribution, correlation, ranking & deviation, flow & process, matrix/heatmap, geospatial, single value, small multiples, tables, specialized).
- [so-what.md](so-what.md) — Layer 3: the filter that forces an insight before a chart ships.
- `delivery/` — Layer 4: present it. [00-principles.md](delivery/00-principles.md) holds the cross-cutting rules; then titles, subtitles, axes & scales, annotations, color & emphasis, color palettes, labels & legends, decluttering, formatting & ordering, dashboards, interaction, polish, typography.
- `patterns/` — [elevation-swaps.md](patterns/elevation-swaps.md): default → better reframes.
- [anti-patterns.md](anti-patterns.md) — what never to do, including cognitive-bias guards.
- [audience-and-presentation.md](audience-and-presentation.md) — tailor to the reader, present it, and read charts critically.
