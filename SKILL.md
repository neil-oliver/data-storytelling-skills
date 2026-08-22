---
name: data-viz-playbook
description: >-
  A complete method for producing and reviewing data visualizations, backed by ~600
  prescriptive rules loaded on demand. Use it whenever the task involves a chart, graph,
  plot, dashboard, KPI tile, or any data visualization: recommending a chart type ("how
  should I show this?"), building a chart from a question or dataset, preparing and shaping
  data to plot, writing chart titles and annotations, or reviewing and improving an existing
  chart supplied as an image, plotting code (matplotlib, plotly, ggplot, d3, Recharts,
  Vega-Lite), inline SVG, or a BI/dashboard spec. Use it even when the word "chart" is
  absent — "visualize this", "show the trend", "what's wrong with this graph", "make this
  dashboard clearer". Source- and medium-agnostic: it applies to any data source and any
  output medium.
---

# Data Visualization Playbook

One system for getting from a question — or from an existing chart — to a visualization
with a defensible point. **This file is the procedure. Everything else is a rule corpus
loaded on demand:** open only the file the current decision needs; each file's
`scope`/`use_when` frontmatter says when it applies. The corpus lives in `chart-types/`
(one file per chart family), `delivery/` (one file per presentation topic), and a few
cross-cutting root files.

## Entry points

- **Create** — you have a question, a dataset, or both, and need the right chart
  recommended and built → run [the create loop](#the-create-loop).
- **Review** — a chart already exists (image, code, spec, or dashboard) and needs critique
  or improvement → run [the review pass](#the-review-pass).

Both share the same corpus and the same bar: a chart ships only with a one-sentence
takeaway it visibly supports.

## The create loop

This is a loop, not a waterfall. Expect to go around parts of it two or three times —
that is the method working, not failing. The two failure modes it exists to prevent:
designing the whole chart on paper before touching the data, and polishing a chart whose
takeaway never survived contact with the real numbers.

**1. Frame it.** Pin down the question, who is asking, the decision the answer feeds,
and the output medium (slide, doc, dashboard, notebook, social) — the medium sets the
aspect ratio, size, and interactivity budget everything downstream must fit.
Name your intent — exploring for patterns or asserting a known point — and your starting
assumption, out loud: bias enters here, not at the color picker. If several questions hide
inside the request, split them; one chart does one job. When a specific audience, reader,
or venue is named, also load [audience-and-presentation.md](audience-and-presentation.md).

**2. Envision the target.** Before shaping any data, sketch the ideal outcome as a
hypothesis: the analytical task (comparison, change over time, part-to-whole,
distribution, correlation, ranking, flow, single value, geographic, matrix), the form
that would make the answer unmissable, and the takeaway you expect to write. Load
[chart-types/00-selection.md](chart-types/00-selection.md) to map task → form, then the
category file for each form still in play — usually one. If two or three forms are
genuinely plausible, carry them all forward and let the real data decide (see
[Parallel work](#parallel-work)).

**3. Interrogate the data.** Load [data.md](data.md). Test the hypothesis against
reality: run the actual queries, pulls, and transforms, and check whether the data can
take the shape the target needs — variables, grain, time window, baseline, denominators.
Explore freely when you don't yet know what the data holds, but return with an aim.
- The data supports the target → shape it (slice, window, normalize, bin, handle gaps)
  and continue.
- It can't → change the target (back to 2) or reframe the question (back to 1). Never
  force data into a form it doesn't support.

**4. Build it for real.** Produce the actual chart with the actual data in the output
medium — run the plotting code, render the SVG, fill the dashboard spec. Not a mock-up:
real numbers, rendered where you can see the result. You cannot judge a chart you haven't
built, and the next step depends on looking at it.

**5. The so-what gate.** Load [so-what.md](so-what.md). Look at the built chart and state
its point in one sentence: metric, cause, impact, next action. Then write the opposite
headline and check whether it survives the same chart — keep the strongest honest
interpretation, not the most persuasive one.
- The takeaway holds → carry the sentence into delivery; it becomes the title.
- It's weaker or different than expected → loop: revise the target (2) or the slice,
  baseline, or statistic (3), rebuild (4), retest.
- No honest story exists → say so. "No meaningful difference" is a legitimate, reportable
  finding; a chart without a point is not.

**6. Deliver.** Design everything around the takeaway sentence. Load
[delivery/00-principles.md](delivery/00-principles.md) and the always-on topics:
[titles](delivery/titles.md) · [subtitles](delivery/subtitles.md) ·
[axes-and-scales](delivery/axes-and-scales.md) ·
[color-and-emphasis](delivery/color-and-emphasis.md) ·
[labels-and-legends](delivery/labels-and-legends.md) ·
[annotations](delivery/annotations.md) · [decluttering](delivery/decluttering.md) ·
[formatting-and-ordering](delivery/formatting-and-ordering.md) ·
[polish](delivery/polish.md). They are short — read the set in one batch rather than
nine sequential opens. Add by context only if it applies:
- Building a color scale (sequential / diverging / categorical) → [delivery/color-palettes.md](delivery/color-palettes.md)
- More than one chart, or KPI tiles, in one view → [delivery/dashboards.md](delivery/dashboards.md)
- The chart is interactive (hover, filter, drill, animate) → [delivery/interaction.md](delivery/interaction.md)
- Choosing typefaces, sizes, or weights → [delivery/typography.md](delivery/typography.md)

Before shipping, sweep [anti-patterns.md](anti-patterns.md). An integrity failure found
here goes back into the loop (3 or 5) — never into a footnote.

**Output.** Deliver three things: the finished chart (or its code/spec), the one-sentence
takeaway, and the data notes a reader needs to trust it — source, time window,
exclusions, caveats.

## The review pass

Input: a chart as an image, plotting code, a spec, or a whole dashboard — plus whatever
is known about its data and audience.

**1. Reconstruct intent.** Identify the analytical task the chart is attempting (use the
taxonomy in [chart-types/00-selection.md](chart-types/00-selection.md)) and its claimed
takeaway, held to the bar in [so-what.md](so-what.md). If the takeaway can't be stated
from the chart alone, record that as finding #1 — it is usually the root cause of
everything else.

**2. Run three lenses.** They are independent reads of the same artifact, so run them in
parallel (see [Parallel work](#parallel-work)):
- **Integrity** — [anti-patterns.md](anti-patterns.md), plus [data.md](data.md) when the
  underlying data or queries are visible: axes, truncation, cherry-picking, misleading
  statistics, bias.
- **Form** — [chart-types/00-selection.md](chart-types/00-selection.md), the category
  file for the form on screen (judge the form it *should* be with 00-selection.md, not by
  loading extra category files), and [elevation-swaps.md](elevation-swaps.md): is this
  the right chart at all, and is there a sharper reframe?
- **Delivery** — [delivery/00-principles.md](delivery/00-principles.md) plus delivery
  topics, judging what the chart is missing as much as what it has: the create loop's
  step-6 lists are the file checklist (always-on topics, plus the by-context ones that
  apply). When a specific audience, reader, or venue is named, add
  [audience-and-presentation.md](audience-and-presentation.md).

**3. Report — then fix, if asked.** Deliver a one-line verdict; then the single
highest-leverage change — the fix that unblocks or rewrites the most other findings,
often but not always the missing takeaway from step 1; then prioritized findings, each
naming the violated rule and the concrete fix. Integrity findings outrank form; form outranks polish. To apply the
fixes yourself, enter the create loop at step 3 or 4 with the reconstructed intent as the
target.

## Parallel work

Parallelism here is about the task, not the machinery: fan work out to parallel subagents
where the harness provides them; otherwise do the same pieces sequentially — the steps
and outputs are identical.

- **Review lenses** (integrity / form / delivery) never depend on each other — run all
  three at once, then merge into one prioritized report.
- **Candidate forms**: when step 2 of the create loop leaves 2–3 plausible forms, build
  cheap real-data drafts of each in parallel, judge them all at the so-what gate, keep one.
- **Multi-chart views**: once each chart's target and takeaway are agreed, build the
  charts in parallel. Fix the shared style first — palette, fonts, number formats
  ([delivery/dashboards.md](delivery/dashboards.md)) — so the parallel outputs merge into
  one coherent view.
- **Do not split one chart's loop.** Envision → interrogate → build → so-what for a
  single chart is sequential by nature: each step consumes the previous step's output,
  so handing the steps to separate agents adds handoffs without saving time.
