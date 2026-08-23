---
scope: Build categorical, sequential, and diverging color palettes that look good.
use_when: Constructing or picking the color palette for a chart or map.
---

# Color palettes

## General craft
- Decide lightness and saturation levels before choosing hues.
- Keep hues in a narrow range — neighbours or complements, not scattered.
- Never pair maximum saturation with maximum brightness; it reads as harsh neon.
- Prefer soft, desaturated tones over garish saturation unless the subject demands vibrancy.
- Give palette colors distinct lightness levels so they stay separable in grayscale.
- Default to warm tones paired with blue: versatile, calm, and colorblind-safe.
- Fix an off palette by adjusting saturation and lightness before adding new hues.
- Separate same-colored shapes with thin white strokes.

## Categorical
- Cap categorical palettes at about four to six clearly distinct colors.
- Color related categories as lighter and darker shades of one hue, not many hues.
- Prefer colorblind-safe pairs like blue-orange; never red-green at equal brightness.
- Distinguish series with dashes, patterns, or line weight, not more colors.

## Sequential
- Run sequential scales light to dark, raising saturation toward high values.
- Keep sequential palettes to one hue or neighbours; never jump across the wheel.

## Diverging
- Make diverging palettes symmetrical: light centre, equally dark ends, neutral midpoint.
- Centre a diverging scale on the true neutral point, not assumed symmetry.
- Use opposite hues on a diverging scale to signal genuine contrast.

## Test
- Test every palette in grayscale and colorblind simulation before committing.
- Ensure every color clears contrast against the background; pastels fail on white.

Related: [color-and-emphasis](essentials.md#color-and-emphasis) · [typography](typography.md) · [matrix-and-heatmap](../chart-types/matrix-and-heatmap.md)
