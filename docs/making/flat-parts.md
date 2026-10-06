# Flat Parts for Laser, Plasma and Router

**Export Flat** turns a plate-like body into a 2D drawing for cutting: its outline, the holes
through it, and the pockets and engraving on it, each on its own layer. Send it to LightBurn,
SheetCam, Vectric or anything that reads DXF or SVG.

## Export a body flat

- Right-click the body in the browser › **Export Flat as DXF...** or **Export Flat as SVG...**,
  **or**
- select the body (or the face to look at) and choose **MAKE › Export Flat**.

Then choose where to save. When it's done, the message shows the part's size.

## Layers

| Layer | DXF color | What's on it |
|---|---|---|
| **CUT_OUTSIDE** | Red | The outline |
| **CUT_INSIDE** | Green | Openings that go right through |
| **ENGRAVE** | Blue | Pockets, recesses and engraved text, and a counterbore's top |

Set your cutting software to cut CUT_INSIDE first, then CUT_OUTSIDE, and to engrave or pocket
ENGRAVE.

## Which side it's drawn from

InvictusCAD looks at the part square to its largest flat face, choosing the side with the
engraving and pockets on it, and lines it up with its longest straight edge so it comes out
square. The lower-left corner is at the origin. To choose the side yourself, select that face
before **MAKE › Export Flat**.

Sizes are in the document's unit. DXF files are R12, which nearly everything reads.

To export a **sketch** rather than a body, see [Import and export drawings](../sketching/import-export.md#export-a-sketch).
