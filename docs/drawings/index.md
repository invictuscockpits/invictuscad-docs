# Drawings

A drawing is a sheet of paper with views of your model on it, dimensioned and noted, to print or
send to whoever is making the part. It doesn't change the model, and it follows it: when the
model changes, the views and dimensions change with it.

## Start a drawing

1. Choose **MAKE › Drawing**. A sheet opens over the 3D view, with the **Base View** card ready.
2. On the card, choose the **Body**, the side it's **Seen from** (front, top, right, left, back,
   bottom or isometric) and whether to show **Hidden lines**. Click **Place**.

The drawing is listed under **Drawings** in the browser. Double-click it there to open it again.

| To | Do |
|---|---|
| Zoom and pan | Wheel; drag with the middle or right button |
| Fit the sheet | ++f++ |
| Close the drawing | **Close Drawing**, or ++esc++ with nothing selected |

++esc++ steps back one thing at a time: out of a tool, then the selection, then the drawing.

## Views

| To | Do |
|---|---|
| Add a view of a body | **Base View** |
| Move a view | Click it, then drag |
| Show or hide its hidden lines | Select it, then **Hidden Lines** |
| Remove it | Select it, then **Delete View** or ++delete++. Its dimensions and notes go with it |

### Projected views

A projected view is the view from another side, kept in line with the one it came from.

1. Select a **front** view.
2. Click **Projected View**.
3. Click above it for the top view, below for the bottom, or beside it for the right or left.

A projected view can only be dragged along its line, and it follows when the front view moves.
Projected views come from a front view; for anything else, use **Base View**.

## The sheet

**Sheet** opens a card for:

- **Size**: A4 to A0, Letter, Tabloid, ANSI C or ANSI D, landscape.
- **Scale**: of the views. 0.5 is half size (1:2), 2 is twice (2:1).
- **Title**, **Drawn by**, **Date** and **Number**, which fill in the title block.

## Dimensions

Click **Dimension** (or press ++d++), then click what to measure and where the number goes.

| To measure | Click |
|---|---|
| An edge's length | The edge, then where the number goes |
| Between two corners | One corner, then the other, then where the number goes |
| To a hole's center | A corner, then the hole (or click the hole's center directly) |
| From a hole or corner to an edge | The hole's center or the corner, then the edge |
| A hole | The hole's circle: see [Hole notes](#hole-notes) |
| A circle that isn't a hole | The circle, for its diameter (an arc gives its radius) |

For two corners, where you put the number decides the direction: above or below them measures
across the page, beside them measures up the page, and off to a corner measures straight between
them. A preview shows what you'll get before you click.

A dimension to an edge is measured square to that edge.

Dimensions measure the model, not the paper: a 100 mm edge reads 100 on a half-size view. They
are written in the document's unit, and they follow the model.

The tool stays on for the next dimension. ++esc++ ends it.

To move a dimension, click its number and drag. To remove it, select it and press ++delete++.

## Hole notes

A hole made with the [Hole](../modeling/holes-and-threads.md) tool can be noted in one click, and
what the note says is read from the hole:

- its diameter, and its depth or **THRU**;
- a counterbore with its diameter and depth, or a countersink with its diameter and angle;
- its thread, for a tapped hole;
- how many holes like it the feature made, as **4X**.

For example:

```
4X Ø6.6 THRU
CBORE Ø11 x 6.4 DEEP
```

Click **Hole Note** (or just **Dimension**), click the hole, then click where the note goes. Any
of the hole's circles will do, in a view where the hole is seen face on.

The note keeps up when the hole is changed. Double-click it to write your own words in its place;
clear them to go back to what the hole says.

A circle that wasn't made with the Hole tool, such as a circle you extruded, gets its diameter
only.

## Center marks, notes and balloons

| Tool | What it does | How |
|---|---|---|
| **Center Mark** | A cross through the middle of a circle | Click the circle |
| **Note** | Words on the sheet, with an arrow if they point at something | Click what it points at, then where it goes. Or click empty paper for a note with no arrow |
| **Balloon** | A number in a circle with an arrow | Click what it points at, then where it goes. Balloons number themselves 1, 2, 3 |

Notes and balloons that point at the model follow it.

To change any of them: click to select, drag to move, ++delete++ to remove. Double-click a note to
change its words, or a balloon to change its number.

## Tables

A table is rows and columns of words: a parts list, or a hole chart.

1. Click **Table**.
2. Give it a **Title** and its **Columns**, separated by `;` (for example `Item; Description; Qty`).
3. Fill in the rows. The table starts with a row for each balloon on the drawing, by its number.
   **From Balloons** adds rows for balloons placed since.
4. Click **OK**.

Drag a table to move it. Double-click it to change it.

The link between a table and its balloons is the number: row 2 is about balloon 2. If you
renumber a balloon, change the table's row to match.

## Export

**Export** saves the drawing as:

| Format | Contains |
|---|---|
| **PDF** | The whole sheet at its true size: views, dimensions, notes, tables and the title block |
| **DXF**, **SVG** | The lines, on the layers **BORDER**, **VISIBLE**, **HIDDEN**, **DIMENSION** and **CENTER**. Numbers and words aren't included |

## From an assistant

Over [MCP](../automation/mcp.md): `add_drawing`, `edit_drawing`, `add_drawing_view`,
`edit_drawing_view`, `delete_drawing_view`, `add_drawing_dimension`, `edit_drawing_dimension`,
`delete_drawing_dimension`, `add_drawing_note`, `add_drawing_hole_note`,
`add_drawing_centermark`, `add_drawing_balloon`, `add_drawing_table`,
`edit_drawing_annotation`, `delete_drawing_annotation` and `export_drawing`.
