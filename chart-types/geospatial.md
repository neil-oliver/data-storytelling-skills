---
scope: Show a pattern across geography.
use_when: Location is the actual question, not just an available attribute.
---

# Geospatial charts

## Choropleth
- Use a choropleth to map a rate or ratio across regions, never raw counts.
- Normalize values by population or area to avoid size bias.

## Flow map
- Encode origin-destination flows as directional arrows between endpoints.
- Prefer directional glyphs so flow direction reads without legend lookups.
- Strip base-map layers to a minimal backdrop so data marks dominate.

## Spatial data
- Use a map for inherently spatial data like isochrones or travel-time.
- Reserve 3D spatial density surfaces for interactive hotspot-finding, not exact value reads.

## When to map
- Choose a map only when geographic pattern is the actual question; otherwise a bar or table is clearer.

Related: [chart-types/00-selection.md](00-selection.md) · [delivery/decluttering.md](../delivery/decluttering.md)
