# Color and Fill (Artwork)

A sketch can be artwork as well as geometry: give its curves a color and fill its closed regions.
The colors show on the model, for example legends and markings on a panel's face, and they
decide which layer each piece goes to when you export for a laser.

## Style curves and regions

1. Choose **Style** (**MODIFY** in the model toolbar, or in the sketch toolbar while sketching).
2. Click the curves to color, and click inside closed regions to fill them. Click one again to
   drop it.
3. Choose the **Color**. The list starts with the colors laser software uses for its layers;
   **Other…** takes any color as `#RRGGBB`, and **None** takes a color off.
4. For curves, set a **Line weight** if you want a heavier line (0 is a hairline).
5. Click **Apply**. The card stays open for the next color; ++esc++ closes it.

Each **Apply** is one undo step.

From the model, Style works on any sketch that's showing. While you're sketching, it works on
that sketch.

## How it shows

- Colored curves are drawn in their color, in place of the sketch's usual working colors.
- Filled regions are drawn flat in their color, on the plane or face the sketch is on.
- Both hide and show with the sketch.

A line weight makes a line look heavier on screen, but it isn't drawn to scale: it stays the same
width as you zoom.

A fill belongs to its region. If you delete or redraw the curves around it, the fill goes and
needs applying again.

## Export for a laser

[Exporting the sketch](import-export.md#export-a-sketch) to DXF or SVG puts each color on a layer
of its own, which is how LightBurn and similar programs decide what to cut, score and engrave:

| Layer | Contains |
|---|---|
| **STROKE_RRGGBB** | Curves with that color, for example **STROKE_FF0000** for red |
| **FILL_RRGGBB** | Regions filled with that color, as closed outlines to fill |
| The layer's own name | Unstyled curves on one of the sketch's [layers](layers.md) |
| **CUT**, **ENGRAVE** | Everything else, as before |

SVG files carry the exact colors and real fills. DXF files can only name a color from a fixed
table, so an unusual color is written as the nearest one; the layer's name still gives the exact
color.

## From an assistant

Over [MCP](../automation/mcp.md), the same is done with `set_stroke` and `set_fill`.
