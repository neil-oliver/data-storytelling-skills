---
scope: Produce a finished image file to a fixed quality bar — canvas, regions, text fitting, label collisions, vector specifics, export, and the visual check.
use_when: The deliverable is an image someone will drop into a slide, doc, or page — not a recommendation, a spec, or live code.
---

# Render

Optional, and deliberately tool-neutral. Nothing here names a library, a language, or a
file format beyond the two things you can hand someone — a vector file or a raster one.
The same targets hold whether the image comes out of a plotting library, a browser, a
notebook, hand-written vector markup, or a design tool. Use whatever is already available
and hold it to these.

The design decisions are already made by the time you get here: form, takeaway, color,
labels, annotation. This stage is about the artifact surviving contact with a real canvas.

## Fix the canvas before drawing
- Size the canvas from the medium first: wide for slides, portrait or column-width for documents, square for social, tall for mobile.
- Fix the aspect ratio up front; resizing after layout invalidates every label position and text fit.
- For raster output, render at twice the pixel dimensions the image will be displayed at, so text stays crisp when scaled or projected. When the destination is unstated, assume a full-bleed slide is displayed at 1280×720 and say what you assumed.
- For vector output, set explicit dimensions and a matching coordinate system so the file scales without clipping.
- Give the canvas an opaque background matching its destination; transparent backgrounds turn dark text invisible on dark slides.

## Reserve regions before plotting
- Divide the canvas into title block, plot area, and footer, and hold each to its budget.
- Never run the plot area to the canvas edge; reserve margin for marks and labels that extend past the last data point.
- Size the right margin from the longest direct label plus its value, not from the plot.
- Reserve the footer for the source line and data notes.
- Account for the destination's own frame: leave margin for the chrome a slide or page template puts around the image, and drop the chart's title if the destination already supplies one.
- Leave the annotation zones empty when laying out the plot; annotations placed last land on whatever is already there.

## Fit the text
- Budget the title block for a full-length takeaway at full size; wrap to a second line rather than shrinking the type.
- Wrap, never shrink below the legibility floor — the type hierarchy has to survive the fit.
- Measure text extent before placing it; text that overflows the canvas is invisible, not merely small.
- Escape or disable the renderer's inline markup before drawing any text: currency, math, and underscore characters are live syntax in many text engines, which will either crash the render or silently swallow the glyph. Labels carrying money hit this constantly.
- Choose where a wrapped line breaks. Never split a number from its unit or currency symbol — that changes what the chart says — and never break inside a hyphenated term.
- Judge the smallest text at final display size, not at authoring size.
- Keep every glyph inside the canvas on all four edges, including descenders and rotated labels.
- Flow the title, subtitle, plot, and footer from measured heights, not fixed offsets; the moment a title wraps to an extra line, fixed offsets put it on top of whatever sits below.

## Resolve label collisions
- Detect overlapping direct labels and fix them: nudge apart, add a leader line, or drop the least important.
- Check annotations against gridlines, axis labels, and data marks, not just against each other.
- When labels crowd past resolving, label fewer things — the peak, the trough, the current value — rather than shrinking them all.
- Verify each label still points unambiguously at its own mark after any nudge.
- Require a real gutter, not bare non-overlap: text separated by a hair still reads as crowded.
- When checking collisions programmatically, ignore anything not actually drawn — hidden, zero-extent, or off-canvas elements — or the check drowns in false positives and you stop trusting it.

## Verify, then export
- Look at the rendered image, not the code or markup that produced it. Clipping, overlap, and collisions are invisible in source and obvious on screen.
- Read every number printed on the chart back against the source data; a formatter that rounds, scales, or truncates wrongly prints a confidently false value.
- Check the glyphs that actually rendered, not just the strings you formatted: currency, math, and markup characters are silently swallowed or restyled by some text engines, so text that is correct in code can be wrong on the canvas.
- Confirm nothing is cut off at any edge and the smallest text is legible.
- Check the palette survives its destination: grayscale, projector, and a dark background.
- Confirm fonts are embedded or fall back to a family that exists wherever the file will open.
- Re-render after each fix and look again; two or three passes is normal, and the loop exits on the image, not on the code.

## When the output is vector

- Convert text to outlines, or embed the font in the file; a bare font-family reference reflows or substitutes wherever that font is absent.
- Keep the file self-contained — no external images, stylesheets, or font URLs. It has to render standalone on a machine you will never see.
- Author at the narrowest width the file will be placed at: the consumer sets the final size, and scaling up degrades gracefully where scaling down drives text under the legibility floor.
- Set a minimum stroke weight that survives being scaled down; hairlines that read at full size vanish at half.
- Rasterize the shipped file with a renderer independent of the one that wrote it, and look at that. Exporting a raster copy from the same call inspects a different artifact and hides malformed markup, unintended transparency, and missing fonts.

Related: [polish](delivery/polish.md) · [typography](delivery/typography.md) · [labels-and-legends](delivery/labels-and-legends.md) · [annotations](delivery/annotations.md)
