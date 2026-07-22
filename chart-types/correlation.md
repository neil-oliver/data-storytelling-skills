---
scope: Show the relationship between two or more numeric variables.
use_when: The story is whether variables move together, and where the outliers are.
aliases:
  - Correlation charts
tags:
  - data-viz
  - chart-types
  - scatter-plot
  - bubble-chart
  - hexbin
  - quadrant-chart
keywords:
  - scatter plot
  - bubble chart
  - hexbin
  - density plot
  - quadrant chart
  - trend line
  - outliers
  - overplotting
---

# Correlation charts

## Scatter
- Use scatter to show correlation between two numeric variables and to spot outliers.
- Fade raw dots and overlay a smoothed line; annotate what the line represents.
- Add a trend line only after distinguishing signal from noise.
- Leave genuinely noisy data as a scatter rather than forcing an unfitting line.

## Bubble
- Encode a secondary variable as mark size rather than adding another axis.
- Size bubbles proportionally to value; never use 3D or area tricks that distort magnitude.

## Density (overplotting)
- When thousands of points overplot, use a hexbin or density-binned view.
- Color density bins on a sequential, perceptually uniform scale so hotspots pop.

## Quadrant
- Partition a scatter into labeled quadrants to turn positions into named categories.
- Split the two metrics at meaningful thresholds; name quadrants (e.g. winners, laggards).

Related: [[so-what]] · [[annotations]]
