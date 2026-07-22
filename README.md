---
scope: Map of the data-visualization playbook — what lives where.
use_when: Locating the rule file for a specific decision.
aliases:
  - Data Visualization Playbook Map
tags:
  - data-viz
  - index
  - navigation
  - four-layer-method
  - playbook-map
  - rule-corpus
keywords:
  - data visualization playbook
  - chart type selection
  - so what filter
  - delivery principles
  - elevation swaps
  - anti-patterns
  - audience and presentation
  - four-layer method
---

# Data Visualization Playbook

A source-agnostic rule set for choosing and designing the right chart. Written for an LLM:
every line is a prescriptive rule, not prose. Load only the file that matches the decision in
front of you.

**How to use it:** the traversal procedure — the four-layer method, per-layer file loads, and
handoffs — lives in [[SKILL]]. This file is just the map.

## Map

- [[SKILL]] — the method: how to traverse this corpus, layer by layer, as one agent or a chain.
- [[data]] — Layer 1: what to plot, and preparing it (selection, statistics, normalization, binning, missing data).
- `chart-types/` — Layer 2: pick a form. [[00-selection]] maps analytical task → form; then one file per category (comparison, change over time, part-to-whole, distribution, correlation, ranking & deviation, flow & process, matrix/heatmap, geospatial, single value, small multiples, tables, specialized).
- [[so-what]] — Layer 3: the filter that forces an insight before a chart ships.
- `delivery/` — Layer 4: present it. [[00-principles]] holds the cross-cutting rules; then titles, subtitles, axes & scales, annotations, color & emphasis, color palettes, labels & legends, decluttering, formatting & ordering, dashboards, interaction, polish, typography.
- `patterns/` — [[elevation-swaps]]: default → better reframes.
- [[anti-patterns]] — what never to do, including cognitive-bias guards.
- [[audience-and-presentation]] — tailor to the reader, present it, and read charts critically.
