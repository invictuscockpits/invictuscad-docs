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

### A whole sketch or layer at once

For lettering made of outlines, with hundreds of curves, set **Apply to** to **Whole sketch** or
**A layer** instead of clicking each piece:

- From the model, pick the sketch in the browser. While sketching, it's that sketch. For a layer,
  choose it under **Layer**.
- **Paint** › **Fill its shapes** fills every closed shape in one go. A letter's holes (the middle
  of an A or an O) stay open. With **Color** › **None**, it takes the fills there off.
- **Paint** › **Color its curves** colors every curve, or with **None** takes their color off.

## How it shows

- Colored curves are drawn in their color, in place of the sketch's usual working colors.
- Filled regions are drawn flat in their color, on the plane or face the sketch is on. The
  curves around them aren't drawn over the fill, so lettering shows at its true weight. While
  you're editing the sketch, they're drawn so you can work on them.
- Both hide and show with the sketch.

A line weight makes a line look heavier on screen, but it isn't drawn to scale: it stays the same
width as you zoom.

A fill belongs to its region. If you delete or redraw the curves around it, the fill goes and
needs applying again.

## Export for a laser

Colors and fills decide how a sketch looks, not which layer it goes to. [Exporting the
sketch](import-export.md#export-a-sketch) to DXF or SVG writes each outline once:

| Layer | Contains |
|---|---|
| The layer's own name | Curves on one of the sketch's [layers](layers.md) |
| **ENGRAVE** | Text, and filled shapes as closed outlines (holes too), ready to fill |
| **CUT** | Everything else |
| **CONSTRUCTION** | Construction curves, only if you ask for them |

For a DXF with a layer per color, set up for LightBurn, use the [DXF Builder](../making/dxf-builder.md).

## From an assistant

Over [MCP](../automation/mcp.md), the same is done with `set_stroke` and `set_fill`.
