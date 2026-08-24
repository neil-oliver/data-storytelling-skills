---
scope: What to plot, and how to prepare it — selection, contextualising comparisons, baselines, statistics, normalization, binning, missing data.
use_when: Deciding which data, slice, window, or baseline to show; finding the comparison that makes a result mean something; or choosing a statistic, denominator, adjustment, binning, or gap handling before plotting.
---

# Data

## What to plot
- Plot only variables that serve the narrative, not every column.
- Present all relevant categories; omitting one can invert the comparison.
- Scrutinise which slice, filter, or aggregation you show; each yields a different story.
- Set the time window deliberately; the range chosen picks the story.
- Show enough history to reveal real trends, not an anomalous start point.
- Never start a series at a known outlier or peak.
- Anchor a time series to a recognizable, deliberately chosen baseline period.
- Include a comparative baseline and reference period; never ship a bare single series.
- Compare only items measured under identical methodology and conditions.
- Ground stated causes in segmentation evidence, not correlation or hypothesis.
- Prefer precise numbers over vague descriptions.

## Contextualising the result
A number on its own carries no meaning — the comparison you set beside it decides what it
says. Work out what this result should be measured against before deciding what it means.

- Search for context in this order: the dataset in front of you, then data the user or
  their organisation already holds, then anything published outside. Stop at the first
  level that answers the question.
- Exhaust the data you already have first. A prior period, another segment or region, a
  peer unit, a plan or budget column, the same metric either side of a known change —
  most "we need outside data" turns out to be a column already present.
- Ask what internal sources exist rather than assuming there are none; the user knows
  what is in their warehouse and you do not.
- Suspect a cause wider than the user's own actions when the pattern is unusually clean,
  moves in step across segments that share no mechanism, coincides with a known seasonal
  cycle, or matches something happening to the whole market.
- Say what you would look for and why, and get the user's agreement, before going outside
  the data you were given. External research takes time and pulls in sources they may not
  trust or be permitted to cite.
- When nobody is available to agree, do not research: ship the chart, and say which
  competing explanations it cannot rule out.
- Never present external data as equivalent to the user's own. Label its source and date,
  and say whether it was measured comparably — see the methodology rule above.
- When the context simply is not available, state what the result cannot distinguish
  rather than letting the chart imply it can.

## Summary statistics
- Inspect the distribution's shape before picking any single summary statistic.
- Report the median, not the mean, when outliers or skew distort the average.
- Use the mean for total impact, the median for the typical case.
- Show both mean and median for skewed data so viewers aren't misled.
- Label the measure of central tendency explicitly; never just say "average".
- Show margins of error so readers see the range around a value.
- Aggregate many samples or surveys rather than trusting a single one.

## Normalization & adjustment
- Normalize raw totals by a denominator like population before comparing entities.
- Re-sort after normalizing; per-capita ranking often reverses raw totals.
- Adjust monetary values for inflation before comparing across years.
- Index to a baseline and label 1.0 (or 100) as the reference.
- Show absolute values alongside percentages; equal +/- percents don't cancel out.

## Aggregation & binning
- Collapse trailing small categories into one "Others" bucket to focus on leaders.
- Order small-multiple panels by a meaningful metric, not alphabetically.
- For histograms, use equal-width bins spanning the full min to max.
- Derive bin width from spread and sample size, then tune by eye until skew or modes appear.

## Missing data
- Break the series and dash the gap; never interpolate across missing data.
- Label missing-data spans directly on the chart for honesty.
- Include every relevant row, even ones that contradict your point.

Related: [so-what](so-what.md) · [distribution](chart-types/distribution.md) · [axes-and-scales](delivery/essentials.md#axes-and-scales) · [anti-patterns](anti-patterns.md)
