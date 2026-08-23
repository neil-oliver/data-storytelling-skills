---
name: data-viz-playbook
description: >-
  The method for deciding what to plot, whether the data supports it, and whether the
  result has a point worth showing — then building, reviewing, or rendering it. Use it for
  any chart, graph, plot, dashboard, KPI tile, or data-visualization task, including
  "visualize this", "render this", "chart this data", "show me the trend", "what's wrong
  with this graph", "make this dashboard clearer". It covers what a styling, palette, or
  component guide does not: mapping the question to an analytical task and chart form,
  interrogating whether the data can actually support that form, forcing a one-sentence
  takeaway before anything ships, critiquing an existing chart — usually a screenshot —
  for integrity, form, and delivery, and holding an image you render yourself to a
  production bar. Load it in addition to any visual-design or palette skill, not instead
  of one: those decide how a chart looks, this decides what it says, whether it is honest,
  and whether it earns its place. Source- and medium-agnostic: any data source, any output
  medium.
---

# Data Visualization Playbook

One system for getting from a question — or from an existing chart — to a visualization
with a defensible point. **This file is the procedure. Everything else is a rule corpus
loaded on demand:** open only the file the current decision needs; each file's
`scope`/`use_when` frontmatter says when it applies. The corpus lives in `chart-types/`
(one file per chart family), `delivery/` (one file per presentation topic), and a few
cross-cutting root files.

When another visualization or design skill is loaded alongside this one, they divide
cleanly rather than compete. That one owns house style: palette, components, and the look
of the finished thing — use it for those. This one owns the decisions, and they come from
this corpus: which analytical task the question actually is, which form serves it, whether
the data supports that form, whether a takeaway survives the built chart, and what a
rendered image has to clear. Another skill's nearest equivalent is written for a different
job and will not route you through the so-what gate, so reaching for it there skips the
part that decides whether the chart is worth shipping.

## Entry points

- **Create** — you have a question, a dataset, or both, and need the right chart
  recommended and built → run [the create loop](#the-create-loop).
- **Review** — a chart already exists — usually as an image — and needs critique or
  improvement → run [the review pass](#the-review-pass).
- **Render** — you are producing the picture yourself rather than handing over a design
  for someone else to build → run [the render stage](#the-render-stage), on top of either
  of the above.

Create and Review share the same corpus and the same bar: a chart ships only with a
one-sentence takeaway it visibly supports.

## What every create run reads

Six files, in this order. They are the method; skipping one is how a chart ships with the
wrong form, a claim the data doesn't support, or no point at all.

1. [chart-types/00-selection.md](chart-types/00-selection.md) — analytical task → form
2. the category file for the form (or forms) still in play
3. [data.md](data.md) — what to plot, and shaping it
4. [so-what.md](so-what.md) — the gate
5. [delivery/essentials.md](delivery/essentials.md) — every rule that applies to every chart
6. [anti-patterns.md](anti-patterns.md) — the pre-ship sweep

[render.md](render.md) joins them whenever you produce the image yourself. Everything
else in the corpus is genuinely conditional — load it only when its `use_when` matches.

A review run reads the same corpus through the three lenses below, not this sequence.

## Working with the user

Work as a companion, not a black box. Two habits keep it that way, and both have a bar —
silence and noise cost trust equally:

**Ask only when the answer would change the chart.** First try to resolve the gap
yourself — from the request, from looking at the data, or with a stated default. Ask when
a genuine fork remains: the metric or question is ambiguous ("growth" of what, measured
how?), the audience or medium is unknown *and* would change the form, explore-vs-assert
is unclear, or the request supports two defensible readings. Between asking and
defaulting, weigh what a wrong guess costs: state a default when being wrong means a
cheap re-cut — size, palette, rounding — and ask when it means a rebuild, because the
metric, the question, or the form was wrong. Ask at the natural moment — usually while
framing, or when a review can't reconstruct the chart's intent — batch the questions into
one round, and lead each with your recommended answer. Never ask what looking at the data
would tell you, and never ask permission for choices the corpus already settles. When no
one is there to answer — a scheduled run, a batch job — never stall: take the best
default and hand it over with the assumption stated plainly enough to be corrected.

**Surface the core choices as they happen.** One or two sentences at each hinge: the
target you're envisioning and why; the feasibility verdict when the data talks back; the
takeaway when it passes the gate, or "no honest story" when it doesn't; a review's
verdict before its detail. These are the candidates, not a checklist to complete — scale
the budget to the job, so a single quick chart may warrant only the target up front and
the takeaway at the end. Don't narrate rule-level execution — tick formats, exact hues,
label placement; the shipped chart shows those. If you looped, say what changed and why,
not every step you retook.

The one that always earns its sentence is a story that shifted: when the data moved the
takeaway off what was asked for, say so *before* handing over the chart, naming both the
result they expected and what replaced it. Finding out from the title feels like an
ambush; hearing it first reads as the method working.

## The create loop

This is a loop, not a waterfall. Expect to go around parts of it two or three times —
that is the method working, not failing. The two failure modes it exists to prevent:
designing the whole chart on paper before touching the data, and polishing a chart whose
takeaway never survived contact with the real numbers.

**1. Frame it.** Pin down the question, who is asking, the decision the answer feeds,
and the output medium (slide, doc, dashboard, notebook, social) — the medium sets the
aspect ratio, size, and interactivity budget everything downstream must fit. A gap here
that would change what you build is the one thing worth a clarifying question now (see
[Working with the user](#working-with-the-user)).
Name your intent — exploring for patterns or asserting a known point — and your starting
assumption, out loud: bias enters here, not at the color picker. If several questions hide
inside the request, split them; one chart does one job. When a specific audience, reader,
or venue is named, also load [audience-and-presentation.md](audience-and-presentation.md).

**2. Envision the target.** Before shaping any data, sketch the ideal outcome as a
hypothesis: the analytical task (comparison, change over time, part-to-whole,
distribution, correlation, ranking, flow, single value, geographic, matrix), the form
that would make the answer unmissable, and the takeaway you expect to write. Load
[chart-types/00-selection.md](chart-types/00-selection.md) to map task → form, then the
category file for each form still in play. If two or three forms are genuinely plausible,
carry them all forward and let the real data decide (see [Parallel work](#parallel-work)).
A category file may point you at a form you hadn't considered — follow that
cross-reference and load it. A better form surfacing mid-loop is the corpus working, not
scope creep.

**3. Interrogate the data.** Load [data.md](data.md). Test the hypothesis against
reality: run the actual queries, pulls, and transforms, and check whether the data can
take the shape the target needs — variables, grain, time window, baseline, denominators.
Explore freely when you don't yet know what the data holds, but return with an aim.
- The data supports the target → shape it (slice, window, normalize, bin, handle gaps)
  and continue.
- It can't → change the target (back to 2) or reframe the question (back to 1). Never
  force data into a form it doesn't support.

**4. Build it for real.** Produce the actual chart with the actual data, in whatever
medium the output calls for. Not a mock-up: real numbers, rendered where you can see the
result. You cannot judge a chart you haven't
built, and the next step depends on looking at it. What you need here is a chart good
enough to judge the story by, not a finished artifact — if the layout is rough but the
shape of the story is legible, that is enough to reach the gate. Production polish belongs
in delivery, and in [the render stage](#the-render-stage) when an image file is the
deliverable.

**5. The so-what gate.** Load [so-what.md](so-what.md). Look at the built chart and state
its point in one sentence: metric, cause, impact, next action. Then write the opposite
headline and check whether it survives the same chart — keep the strongest honest
interpretation, not the most persuasive one.
- The takeaway holds → carry the sentence into delivery; it becomes the title.
- It's weaker or different than expected → loop: revise the target (2) or the slice,
  baseline, or statistic (3), rebuild (4), retest — and tell the user when the story has
  shifted from what they asked for.
- No honest story exists → say so. "No meaningful difference" is a legitimate, reportable
  finding; a chart without a point is not.

**6. Deliver.** Design everything around the takeaway sentence. Load
[delivery/essentials.md](delivery/essentials.md) — one file holding every rule that
applies to every chart: principles, titles, subtitles, axes and scales, color and
emphasis, labels and legends, annotations, decluttering, formatting and ordering, and
polish. Read it whole; it is the always-on set, not a menu to sample. Then add only what
the chart actually needs:
- Building a color scale (sequential / diverging / categorical) → [delivery/color-palettes.md](delivery/color-palettes.md)
- More than one chart, or KPI tiles, in one view → [delivery/dashboards.md](delivery/dashboards.md)
- The chart is interactive (hover, filter, drill, animate) → [delivery/interaction.md](delivery/interaction.md)
- Choosing typefaces, sizes, or weights → [delivery/typography.md](delivery/typography.md)

When a rule applies but the input it needs doesn't exist — an inflation adjustment with no
deflator, a benchmark nobody has — disclose the gap on the chart. Inventing the input is
worse than the gap, and silently dropping the rule hides a real limit on what the chart
can claim.

Before shipping, sweep [anti-patterns.md](anti-patterns.md). An integrity failure found
here goes back into the loop (3 or 5) — never into a footnote.

**Output.** If you are producing the image yourself rather than handing over something
the recipient will build, continue to [the render stage](#the-render-stage) before handing
anything over — that applies to a quick inline picture just as much as to a file. Either way, deliver three things: the finished chart (or its code/spec),
the one-sentence takeaway, and the data notes a reader needs to trust it — source, time
window, exclusions, caveats.

## The review pass

Input: most often an image — a screenshot, an export, a slide someone was sent — and
sometimes the code or spec behind it, plus whatever is known about its data and audience.

An image is enough to review most of what matters, and it also bounds what you may claim.
Form, encoding, axis ranges, labels, color, clutter, and whether a takeaway lands are all
judgeable from pixels alone. What happened to the data before it reached the chart is not:
whether a category was dropped, a window cherry-picked, a statistic poorly chosen, or a
comparison drawn across incompatible methodologies. Judge what you can see; put the rest
to whoever owns the data as questions rather than findings, and say which of your findings
would change if the answer went the other way.

**1. Reconstruct intent.** Identify the analytical task the chart is attempting (use the
taxonomy in [chart-types/00-selection.md](chart-types/00-selection.md)) and its claimed
takeaway, held to the bar in [so-what.md](so-what.md). If the takeaway can't be stated
from the chart alone, record that as finding #1 — it is usually the root cause of
everything else — and if you also can't tell what the chart was *trying* to say, ask its
owner rather than reviewing a guess.

**2. Run three lenses.** They are independent reads of the same artifact, so run them in
parallel (see [Parallel work](#parallel-work)):
- **Integrity** — [anti-patterns.md](anti-patterns.md), plus [data.md](data.md) when the
  underlying data or queries are visible: axes, truncation, cherry-picking, misleading
  statistics, bias.
- **Form** — [chart-types/00-selection.md](chart-types/00-selection.md), the category
  file for the form on screen (judge the form it *should* be with 00-selection.md, not by
  loading extra category files), and [elevation-swaps.md](elevation-swaps.md): is this
  the right chart at all, and is there a sharper reframe?
- **Delivery** — [delivery/essentials.md](delivery/essentials.md), judging what the chart
  is missing as much as what it has, plus any by-context file the chart's own features
  call for (a color scale, a dashboard, interactivity, type). When a specific audience,
  reader, or venue is named, add
  [audience-and-presentation.md](audience-and-presentation.md).

**3. Report — then fix, if asked.** Deliver a one-line verdict; then the single
highest-leverage change — the fix that unblocks or rewrites the most other findings,
often but not always the missing takeaway from step 1; then prioritized findings, each
naming the violated rule and the concrete fix. Integrity findings outrank form; form
outranks polish. A critique is feedback on someone's work: name what the chart gets right
before what it gets wrong, and aim every finding at the chart, not its author. To apply
the fixes yourself, enter the create loop at step 3 or 4 with the reconstructed intent as
the target.

## The render stage

Run this stage whenever you are the one producing the image — rendering a chart to a
file, drawing it inline, exporting a picture, or otherwise handing back something to look
at rather than something to build from. Being asked to "visualize" or "show" a result
puts you here.

It is skipped in exactly one case: the deliverable stops at the design — a form, a
takeaway, and the delivery decisions — which the recipient will build in their own tool,
on their own data, in their own house style.

That is the whole test, and it is worth being precise about what "optional" means here.
It means some tasks legitimately end at the design. It does not mean a rendered chart may
skip these targets, and it is not licence to fall back on however you would otherwise
draw a chart. Knowing how to produce an image is not the same as holding one to a
standard: skipping this stage is how charts ship with clipped titles, colliding labels,
illegible type, and numbers that contradict the data — each of them invisible in the code
that produced them and obvious in the image.

Load [render.md](render.md). It fixes the production targets — canvas and aspect,
reserved regions, text fitting, label collisions, export, and the visual check — without
naming a library, a language, or a format beyond vector versus raster. Use whatever tool
is already to hand and hold it to those targets; the corpus stays deliberately neutral so
the same design can be rendered anywhere, by anyone.

Two things make this stage worth running as its own pass rather than folding it into
step 4. First, its exit condition is visual, not logical: you render, look at the image,
fix what only the image reveals, and render again — clipping, collisions, and overflow
are invisible in source. Second, it carries the last integrity check in the whole method:
every number printed on the chart gets read back against the source data, because a
formatter that rounds or scales wrongly will print a confidently false value onto an
otherwise honest chart.

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
