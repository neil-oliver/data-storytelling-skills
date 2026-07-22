---
scope: What to plot, and how to prepare it — selection, baselines, statistics, normalization, binning, missing data.
use_when: Deciding which data, slice, window, or baseline to show, or choosing a statistic, denominator, adjustment, binning, or gap handling before plotting.
aliases:
  - Data
tags:
  - data-viz
  - data
  - summary-statistics
  - normalization
  - binning
  - missing-data
keywords:
  - summary statistics
  - mean vs median
  - normalization
  - inflation adjustment
  - histogram bins
  - missing data handling
  - baseline period
  - per-capita normalization
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

Related: [[so-what]] · [[distribution]] · [[axes-and-scales]] · [[anti-patterns]]
