# Layers

A sketch can keep its curves on layers, the way a drawing program does. Hide a layer to get it out
of the way, lock it so you can't pick it by accident, give it a color, or mark it as reference
only so it's left out of extrudes.

Layers matter most for drawings you import. A set of cutting plans arrives with its cut lines,
part numbers, notes and sheet markings each on their own layer, and you can put everything but the
cut lines away.

## The Layers card

While you're editing a sketch, the **Layers** card sits under the browser. Each row is a layer:

| | |
|---|---|
| **Eye** | Hide or show the layer |
| **Lock** | Lock it: still shown, but clicks and tools don't pick its curves |
| **Square** | Filled: its curves are used for profiles. Dashed: [reference only](#reference-layers) |
| **Dot** | The [color](#layer-colors) its curves are drawn in. Hollow means none |
| **Name** | Double-click to rename |
| **Number** | How many curves are on it |

Curves that aren't on any layer are counted on a **(No layer)** row at the bottom.

A sketch doesn't need layers. Until you make one or import a drawing that has them, the card is
empty and everything works as before.

## Draw on a layer

Click a layer. Its name turns bold, and from then on everything you add to the sketch goes on it:
lines, circles, offsets, patterns, and imported curves that have no layer of their own.

Click **(No layer)** to go back to drawing on none.

Choosing a layer is a step you can undo, like hiding or locking one.

## Make, fill and delete layers

| To | Do |
|---|---|
| Make a layer | **+ New**, and give it a name. It gets a color of its own and becomes the layer you're drawing on |
| Move curves to a layer | Select the curves, click the layer, then **Move Here** |
| Take curves off their layer | Select them, click **(No layer)**, then **Move Here** |
| Delete a layer | Click it, then **Delete**. Its curves stay, on no layer |

## Hidden and locked layers

A **hidden** layer isn't drawn, can't be picked, and nothing snaps to it. Its curves are still
part of the sketch: hiding a layer changes what you see, not what the sketch makes.

A **locked** layer is drawn as usual and you can snap to it, but you can't select its curves or
pick them with a tool such as Dimension or Trim.

## Reference layers

Click a layer's **square** to make it reference only. Its curves are drawn dashed, like
[construction geometry](drawing.md), and are left out of every profile: Extrude, Revolve, sheet
metal and fills all ignore them. Click the square again to bring them back.

This is how you extrude a part from imported plans without its lettering cutting holes in it:
make the notes, markings and part numbers reference only, and Extrude sees just the cut lines.

Anything already made from the sketch is rebuilt when you change this.

## Layer colors

Click a layer's **dot** to choose the color its curves are drawn in: one of ten ready colors,
**Other…** for any color, or **None** for the sketch's usual colors.

A curve you've colored yourself with [Style](artwork.md) keeps that color.

A layer's color is for telling layers apart on screen and in exported files. Curves on a
reference layer stay dashed whatever the layer's color.

## Layers from imported drawings

[Importing](import-export.md) a DXF, Illustrator or PDF file keeps the file's layers, with their
names. They arrive shown, unlocked and with no color, ready to hide or mark as reference.

## Layers in exported files

[Exporting the sketch](import-export.md#export-a-sketch) to DXF or SVG writes each layer as a
layer of the file, in its color:

- A layer's name is written with only letters, digits, `-`, `_` and `$`, which every program
  reads: **Cut Lines** becomes **Cut_Lines**.
- A hidden layer is left out.
- A reference layer is left out, as construction geometry is.
- Curves on no layer go to **CUT** and **ENGRAVE**, as before.

## From an assistant

Over [MCP](../automation/mcp.md): `set_layer` puts curves on a layer, `edit_layer` makes or
changes one (name, visible, locked, reference, color, active), and `delete_layer` removes one.
