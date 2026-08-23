---
scope: The delivery rules that apply to every chart — principles, titles, subtitles, axes, color, labels, annotations, decluttering, formatting, and polish.
use_when: Designing the presentation of any chart. Read this whole file once per chart; it is the always-on set, not a menu.
---

# Delivery essentials

Everything here applies to every chart, which is why it is one file rather than ten. Read
it straight through once the takeaway is settled, then design around that sentence.

Topic-specific rules that apply only sometimes live in their own files, listed at the
bottom.

## Principles

- Design a clear visual hierarchy so the main message reads in seconds.
- Direct the eye to the story zone; don't weight everything equally.
- State the data source on or near the chart to build trust.
- Strip jargon so a non-technical reader grasps the insight instantly.
- Make framing choices visible; let data, not design tricks, shape the narrative.
- Give enough context that a reader interprets a dip before reacting.
- Ensure every number drives an action or decision, or cut it.
- Preserve whitespace; don't fill every region.
- Ask what's missing from the visual story before publishing.

## Titles

- Write the title as the takeaway/finding, using active verbs, not a bland topic label.
- Lead with the conclusion; let the data support it.
- Pair a takeaway-sentence title with a descriptive subtitle naming what's measured.
- Place the title top-left in the largest font, never below the chart.
- Keep titles to roughly 6-12 words: one chart, one message.
- Keep every takeaway title defensible against the data; never overreach past what it supports.
- Use neutral, descriptive labels for reference/discovery charts so scanners locate the figure.
- Use interpretive headlines for persuasion.
- For media or engagement, a question or bold hook headline can pull readers in.
- Avoid question titles on analytical charts; they make readers hunt for the answer.
- Use a call-to-action title stating the recommended next step, when you want action.
- Name the highlight colors inside the title to replace a separate key; when an accent is blue, set that word apart without color — heavier weight, or a small swatch beside it if the title is already bold throughout (blue text reads as a link).
- Avoid generic data-only titles that omit your analytical point.

## Subtitles

- Write the subtitle stating what is measured, over what period, and how.
- Use the subtitle for units, timeframe, geography, source, and data notes.
- Pair a bold headline with a dry, factual subtitle to frame the effect.
- Add a subtitle naming the cause behind the pattern on direction charts.
- Add a subtitle stating why the metric misleads when it can.
- In small multiples, state per-panel what each measures in its subtitle.
- Color category names in the intro text to prime readers before the chart — except a blue accent, which reads as a link; bold that one instead.

## Axes and scales

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
- Avoid negative axis values; where you keep a value axis at all, use a labeled split axis with plain-language directions instead.
- Anchor an index scale by labeling the 1.0 (or 100) baseline as the average.
- Prefer a single axis over two when one scale suffices; avoid dual y-axes outright when both series share the same unit.
- Use a log scale for data spanning several orders of magnitude; label it, and avoid it for audiences who read it as linear.
- Show units once at the top tick, not on every gridline.
- Use enough ticks to read values, but not so many they crowd.
- Mute gridlines, ticks, and axis labels so they support, not compete.
- Include gridlines only when viewers must estimate precise values; drop the value axis once data labels give exact values.
- Avoid 45-degree rotated labels; switch to horizontal bars for long labels.
- Give each ternary component its own axis with a consistent tick direction.
- Share one axis and scale across compared panels.
- Extend the time window far enough to expose the seasonal pattern.

## Color and emphasis

- Use color functionally to guide attention to the main point.
- Highlight the priority data in one saturated accent; desaturate everything else to gray.
- Color only the categories that matter; mute the rest to gray.
- Keep context data visible but recessive so the point still has comparison.
- Limit a focused, story-driven chart to two or three hues; categorical palettes may need more (see [color-palettes](color-palettes.md)).
- Avoid rainbow-coloring categories with no meaning; color must encode something.
- Color bars by whether they meet the target, not by category identity.
- Split marks by color at a reference line: above one color, below another.
- Encode direction of change with color and arrows (favorable up, unfavorable down).
- For a change metric, use diverging color scaled by magnitude.
- Tie color meaning to the reader's stake (e.g. better-for-buyers vs better-for-sellers).
- Avoid loaded color (green=good, red=alarm) that pushes a verdict onto neutral data.
- Give the actual series a strong dark color; mute forecast lines to one lighter hue.
- Assign each group one consistent color across every panel and view.
- Distinguish categories by both marker shape and color, not color alone.
- Choose colorblind-safe hues; avoid red-green pairings for categories.
- Never rely on color alone to distinguish series; add text labels.
- Fade overlaid raw points so a smoothed line stays dominant.
- Color density bins on a sequential, perceptually uniform scale so hotspots pop.

- Echo the focal series' color in its title and label text to tie them together.
- Match the palette to brand colors while preserving contrast.

- Saturation grabs attention before darkness; build a saturation hierarchy with grey last.
- Never use grey as an equal category color; it reads as less important.
- A hue change implies a new category — don't recolor unimportant data with a new hue.
- Avoid blue for colored text; readers mistake it for a link.
- Cap the visual hierarchy at three or four priority levels.

## Labels and legends

- Label data series directly adjacent to the marks instead of using a legend.
- Label lines directly at their ends; match label color to the line.
- Label bars directly with their values instead of forcing axis lookups.
- Print percentage values inside diverging/Likert bars; people judge stacked lengths poorly.
- Print the underlying value inside each heatmap cell for exact readouts.
- Label only critical points: peak, trough, current, and change onset.
- Label the measure of central tendency explicitly; never just say "average".
- Label each distribution group with its defining threshold and sample size n.
- Label deltas clearly, e.g. "+12% vs last week" or "95% of target met".
- Give quadrant regions plain-language names describing what points there represent.
- Use brackets or braces to label groups in place, removing legend-hunting.
- Replace technical jargon with plain language anyone grasps instantly.
- When a legend is unavoidable, place it right under the title.
- Spell out abbreviations in a subtitle legend when using short codes.
- For lookup audiences, show exact numeric values beside each item.
- For pattern audiences, drop per-item numbers so the eye reads the shift.
- Check every label's spelling and mark units clearly.

- Place the legend near where its colors first appear.
- Order legend entries to match the reader's scanning flow (top-first, left-to-right).
- Arrange many or long legend labels in a grid, not cramped lines.
- Mirror the chart's strokes, outlines, and patterns exactly in legend swatches.
- Keep the color key on-screen — sticky or repeated — so readers never scroll to find it.

## Annotations

- Place each annotation directly on the shape or moment it explains.
- Position each annotation next to its data region, not in a legend.
- Translate the visual shape into plain sentences within the annotation.
- Add a directional arrow to a line's endpoint to punctuate where it's heading.
- Use difference arrows to mark point-to-point change and its magnitude.
- Anchor each metric with a benchmark, target, threshold, or prior-period comparison.
- Add labeled reference lines for targets, thresholds, and averages.
- Draw a threshold line and shade the portion above it to expose excess.
- Show a normal-variation band so routine noise isn't read as a trend change.
- Shade and label the meaningful period on a time series to explain a spike.
- Mark causal events with a labeled vertical reference line at their position.
- Annotate inflection points with the events that caused them.
- Mark known one-off events, promos, and methodology changes separately from the trend.
- Style incomplete or late-attributing trailing periods so they don't read as decline.
- Overlay labeled quadrant regions on scatters to turn positions into named categories.
- Annotate what one mark represents (e.g. "each dot is one metro area").
- Note what a computed line is (e.g. an N-year average) for wider audiences.
- Include a starting reference value so a waterfall's final total makes sense.
- Label missing-data spans directly on the chart for honesty.
- State totals in words to spare the audience mental math.
- Use annotations to carry secondary messages the title can't hold.

- Color only the semantic word in a sentence, not the whole phrase.
- Add a background-color outline behind annotation text when it overlays chart elements.
- Shade grey ranges to mark contextual periods or zones.

## Decluttering

- Remove any element that doesn't encode data or support the message.
- Maximize data-ink; strip gradients, textures, shadows, and borders.
- Never use 3D effects that distort perceived magnitude.
- Set non-critical elements to light gray so they recede.
- Fade raw data to low opacity when a processed trend matters more.
- Consolidate minor categories to reduce cognitive load.
- Avoid background shading unless it encodes meaning.
- Remove decorative icons and imagery that encode nothing.
- Keep the default view minimal; reveal detail on demand via interaction.

## Formatting and ordering

### Number & date formatting
- Round numbers to the precision the decision needs, not raw digits.
- Never let rounding print a figure that contradicts the data: a real change that rounds to zero, or a sign that disappears, needs another decimal or a different unit. "-0%" against a real decline is a false statement, not a tidy one.
- Trim decimals and abbreviate large numbers (K, M) to declutter dashboards.
- Keep precise decimals for scientific, financial, or engineering data where rounding erodes credibility.
- Use thousands separators and consistent units.
- Fold units into tick labels (e.g. $50), on the top tick only — see [axes-and-scales](#axes-and-scales).
- Signal direction with an up or down arrow and percent, not just the value.
- Format dates and axis ticks consistently; avoid ambiguous formats.

### Line & bar styling
- Distinguish actuals from forecast with solid vs dashed styling.
- Keep histogram bars gap-free so adjacent bins read as a continuous range.

### Sorting & ordering
- Sort categorical bars by value unless a natural or fixed order exists.
- Keep category order consistent across related charts for comparison.
- Order stacked segments by size or a stable, meaningful sequence.
- Cluster related categories together instead of scattering them along the axis.

## Polish

- Prioritise clarity and readability over decorative styling.
- Aim for a polished, presentation-ready look; don't rely on manual patch-up.
- Align chart elements cleanly on a shared grid; avoid misaligned layouts.
- Keep spacing consistent — even bar gaps, uniform margins, balanced whitespace.
- Build a clear type hierarchy with legible fonts — see [typography](typography.md).
- Match aspect ratio and text sizes to the display context (slide, doc, mobile); when you are producing the image file yourself, [render](../render.md) holds the canvas and resolution targets.
- Prefer soft, intentional palettes over harsh, outdated defaults.
- Set annotations in a distinct style so they read as commentary, not data.
- Keep styling — colors, fonts, layout — stable across contexts and when embedded.

## Load these only when they apply
- Building a color scale (sequential / diverging / categorical) → [color-palettes](color-palettes.md)
- More than one chart, or KPI tiles, in one view → [dashboards](dashboards.md)
- The chart is interactive (hover, filter, drill, animate) → [interaction](interaction.md)
- Choosing typefaces, sizes, or weights → [typography](typography.md)
- Producing the image yourself → [render](../render.md)

Related: [so-what](../so-what.md) · [anti-patterns](../anti-patterns.md)
