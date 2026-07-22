---
name: data-viz-playbook
description: >-
  A portable, source-agnostic method and rule corpus for designing any data visualization:
  structuring and cleaning the data, choosing the chart form, forcing the "so what", and
  polishing delivery. Use when deciding what to plot, which chart type fits, or how to make
  a chart's point land — in any medium (plotting code, inline SVG, a dashboard, a notebook,
  an exported image). Each phase loads only its slice of the corpus, so one agent, or a chain
  of phase-specialized agents, can use it without loading the whole library.
aliases:
  - Data Visualization Playbook
tags:
  - data-viz
  - method
  - four-layer-method
  - workflow
  - chart-selection
  - so-what-gate
keywords:
  - data visualization method
  - four-layer design process
  - chart type selection
  - so what gate
  - delivery principles
  - phase-specialized agents
  - process guardrails
  - rule corpus
---

# Data Visualization Playbook

A method for designing any chart, plus a rule corpus you load on demand. Source- and
medium-agnostic: it applies whether you output plotting code, inline SVG, a dashboard, or an
uploaded image. **This file is the procedure — how to traverse the corpus. The corpus itself
(`chart-types/`, `delivery/`, and the reference files) is pure data; load only the file the
current decision needs.**

## How to use this

Design in four layers, top to bottom. Do not skip a layer. Each layer is a self-contained job
with its own slice of the corpus. One agent can run all four in sequence, or a separate agent
can own each — receiving the previous layer's **output** and passing its own forward.

### Layer 1 — Data · *what to plot, cleaned and shaped*
- **Load:** [[data]]
- **Do:** choose the variables, slice, time window, and baseline; pick summary statistics;
  normalize, bin, and handle missing data.
- **Output:** a clean, shaped dataset **+ a one-line statement of the analytical task**
  (comparison, change over time, part-to-whole, distribution, correlation, ranking, flow,
  single value, geographic, matrix…).

### Layer 2 — Chart type · *the form that makes the message unmissable*
- **Load:** [[00-selection]] (the task → form lookup),
  then the **one** category file it routes you to.
- **Do:** map the analytical task to a form; prefer the simplest honest form that fits.
- **Output:** the chosen chart form **+ any form-specific construction notes** from that file.

### Layer 3 — So what · *the gate: no point, no chart*
- **Load:** [[so-what]]
- **Do:** state metric, cause, impact, and next action in one sentence. If you can't, **stop** —
  return to Layer 1 to fix the data or the framing, or don't ship the chart.
- **Output:** the one-sentence takeaway the chart must deliver.

### Layer 4 — Delivery · *make the message land*
- **Load:** [[00-principles]], then only the delivery topics
  this chart needs (see selection below).
- **Do:** title, axes, color, labels, annotation, decluttering, and polish — all around the takeaway.
- **Output:** the finished chart.

## Which delivery files to load

Don't load all of `delivery/`. Apply the always-on set; add the rest by context.

**Always:** [[00-principles]] · [[titles]] ·
[[subtitles]] · [[axes-and-scales]] ·
[[color-and-emphasis]] · [[labels-and-legends]] ·
[[annotations]] · [[decluttering]] ·
[[formatting-and-ordering]] · [[polish]]

**By context — load only if it applies:**
- Building a color scale (sequential / diverging / categorical) → [[color-palettes]]
- More than one chart, or KPI tiles, in one view → [[dashboards]]
- The chart is interactive (hover, filter, drill, animate) → [[interaction]]
- Choosing typefaces, sizes, or weights → [[typography]]

## Cross-cutting references (pull from any layer when the decision calls for it)
- [[anti-patterns]] — what never to do; honesty and cognitive-bias guards. Consult before shipping.
- [[elevation-swaps]] — when the default form is cluttered or off-message, the sharper reframe.
- [[audience-and-presentation]] — tailoring depth, framing, and sequencing to a specific reader or room.

## Process guardrails
- Define narrative intent — explore or assert — before designing.
- Name your starting assumption aloud to expose bias.
- Write the opposite headline first; test whether a competing story holds.
- Have a critic challenge your axis, comparison, and omission choices before shipping.
- Choose the strongest honest interpretation, not the most persuasive one.

## Running the layers as separate agents
- Give each phase agent **only its layer's `Load` set** — not the whole corpus. That isolation is the point of the split.
- Pass the `Output` of each layer as the input to the next; don't forward the raw files you read.
- The Layer 3 gate is a hard stop: an agent that can't state the so-what returns to Layer 1, it does not proceed to Delivery.
- [[README]] is the map of where every rule lives, if an agent needs to locate one outside its layer.
