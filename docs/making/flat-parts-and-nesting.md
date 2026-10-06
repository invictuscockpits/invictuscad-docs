# Flat Parts and Nesting

For lasers, routers and plasma tables.

## Export a sketch

Export any sketch to **DXF (R12)** or **SVG** at real size, with geometry on separate layers:
`CUT`, `ENGRAVE` (text outlines) and `CONSTRUCTION`. These files open directly in LightBurn,
SheetCam and Vectric.

## Flat parts from bodies

Lay a body flat and export its outline, with layers your CAM program can map to operations:

| Layer | Contains |
|---|---|
| `CUT_OUTSIDE` | The outer profile |
| `CUT_INSIDE` | Openings that go all the way through |
| `ENGRAVE` | Pockets and engraved text |

## Nesting

Nest copies of parts on a sheet to save material. Parts are packed as rectangles and can be
turned 90 degrees. True-shape nesting, kerf compensation and lead-ins are planned.
