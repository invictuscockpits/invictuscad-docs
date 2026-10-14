# Drawings

A drawing is a sheet of paper with views of your model on it, dimensioned and noted, to print or
send to whoever is making the part. It doesn't change the model, and it follows it: when the
model changes, the views and dimensions change with it.

## Start a drawing

1. Choose **MAKE › Drawing**. A sheet opens over the 3D view, with the **Base View** card ready.
2. On the card, choose the **Body**, the side it's **Seen from** (front, top, right, left, back,
   bottom or isometric) and whether to show **Hidden lines**. Click **Place**.

When the model has more than one part placed, **Body** also offers **(Whole assembly)**, for a
view of everything together.

The drawing is listed under **Drawings** in the browser. Double-click it there to open it again.

The drawing's tools are the row of icons above the sheet. Hover over one for its name and what it
does; this page calls them by those names.

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

### Section views

A section view shows the part cut open, with the cut material hatched.

1. Select the view to cut.
2. Click **Section View**.
3. Click where the cut should pass through the view. Clicking a corner or a hole's center puts
   it exactly there.
4. Click where the section goes:

    | Put it | The cut runs | Seen from |
    |---|---|---|
    | To the right or left of the view | Up the view | That side |
    | Above or below the view | Across the view | That side |

    A line follows the cursor to show which cut you'll get.

The view it was cut from gets the cutting line, with arrows pointing the way the section looks
and a letter at each end. The section is captioned **SECTION A-A** and stays in line with the
view it came from. Letters run A, B, C on their own.

Cuts are straight, right across the view. Holes and other openings are left clear of hatching.

A section is cut from a view seen square on (front, top, right and so on). **Section View** is
off for an isometric view.

### Detail views

A detail view shows a small area of a view, larger.

1. Select the view. A section view works too.
2. Click **Detail View**.
3. Click the middle of the area, then click again to set how far out its circle reaches.
4. Click where the detail goes.

The detail is drawn at twice the scale of the view it came from and captioned, for example,
**DETAIL B (2:1)**. The view it came from gets the circle and the letter. A detail of a section
keeps the hatching.

Sections and details follow the model, and you can dimension and note them like any other view.

## The sheet

**Sheet** opens a card for:

- **Size**: A4 to A0, Letter, Tabloid, ANSI C or ANSI D, landscape.
- **Scale**: of the views. 0.5 is half size (1:2), 2 is twice (2:1).
- **Title**, **Drawn by**, **Date** and **Number**, which fill in the title block.
- **General tolerance**: the tolerance of dimensions that don't carry their own, such as ±0.1. It
  gets a box in the title block, **TOLERANCE UNLESS NOTED**. Leave it empty for no box.

### More than one sheet

A drawing can have several sheets, all the same size: the assembly on the first, say, and a part
on each of the others.

| To | Do |
|---|---|
| Add a sheet | **+ Sheet**. It opens, empty |
| Go between sheets | **‹** and **›**, either side of **1 of 2** |

Whatever you place goes on the sheet that's showing. Each sheet's title block says which it is
(**1 OF 2**). A sheet with something on it can't be removed.

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

On an isometric view, a dimension always runs straight from one point to the other and reads the
model's true length, not its foreshortened length on the page.

Dimensions measure the model, not the paper: a 100 mm edge reads 100 on a half-size view. They
are written in the document's unit, and they follow the model.

The tool stays on for the next dimension. ++esc++ ends it.

To move a dimension, click its number and drag. To remove it, select it and press ++delete++.
++delete++ only ever removes what's selected on the sheet, never the drawing.

## Tolerances and dimension text

Double-click a dimension's number to open its card.

| Field | What it does | Reads |
|---|---|---|
| **Before** | Words before the number | 2X 60 |
| **After** | Words after it | 60 TYP |
| **Tolerance** | See below | |
| **Decimal places** | **As few as it needs** drops trailing zeros. A number keeps them | 100.00 |
| **Reference** | Puts the dimension in brackets | (100) |

The kinds of tolerance:

| Tolerance | Fill in | Reads |
|---|---|---|
| **Plus or minus** | **Over**: how far either way | 60 ±0.2 |
| **Over and under** | **Over** and **Under**, each as a positive amount | 60, then +0.1 above -0.05 |
| **Limits** | **Over** and **Under** | 60.1 above 59.95, in place of the number |
| **Fit** | **Fit**: the fit's letters | Ø20 H7 |

This works on every dimension: lengths, diameters, radii and angles. A length's tolerance is
written in the document's unit; an angle's is in degrees. To see a tight tolerance in full, raise
the decimal places: +0.021 needs three.

The size itself still comes from the model. A tolerance says how far a made part may be from it;
it doesn't change the model.

## Angles

Click **Angle**, click two straight edges, then click where the number goes.

Two edges make two angles, a sharp one and the rest of the half turn. Where you put the number
picks which: inside the corner for the angle between the edges, outside past the corner for the
other. A preview shows the angle before you click.

The arc is centered where the two edges' lines meet, even when the edges themselves stop short of
each other, and it passes through the spot you clicked. On an isometric view, the angle is the
true angle in the model.

Edges that are parallel in the view have no angle between them and can't be picked together. The
tool stays on for the next angle; ++esc++ ends it. Move and remove an angle like any other
dimension.

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

## Parts list

A parts list is a table that writes itself from the assembly: a row for each
[component](../assemblies/components.md), with how many of it are placed and its material. A body that
isn't in a component gets a row too.

1. Place a view of the **(Whole assembly)**.
2. Click **Parts List**.

The list goes at the top left of the sheet, and each part gets a numbered balloon above the view,
pointing at the first one of it. Drag the list and the balloons where you want them.

The list and its balloons keep up with the model: place another copy of a part and its quantity
goes up; add a part and it gets a row. A drawing has one parts list; clicking **Parts List** again
selects it.

Without a view of the assembly on the sheet, you get the list with no balloons. To add a balloon
for a part later, use `add_drawing_balloon` with `part` from an assistant.

Dimensions, angles, notes, hole notes, center marks and balloons all work on a view of the
assembly, and can run from one part to another: the distance between two parts, say. They follow
when a part is moved.

## Export

**Export** saves the drawing as:

| Format | Contains |
|---|---|
| **PDF** | Each sheet at its true size, a page each: views, dimensions, notes, tables and the title block |
| **DXF**, **SVG** | The lines, on the layers **BORDER**, **VISIBLE**, **HIDDEN**, **DIMENSION**, **CENTER**, **HATCH** and **SECTION**. Numbers and words aren't included. Several sheets are laid side by side |

## From an assistant

Over [MCP](../automation/mcp.md): `add_drawing`, `edit_drawing`, `add_drawing_view`,
`edit_drawing_view`, `delete_drawing_view`, `add_drawing_dimension`, `edit_drawing_dimension`,
`delete_drawing_dimension` (an angle is `kind: "angle"` between two edges; a dimension takes
`prefix`, `suffix`, `tolerance`, `plus`, `minus`, `fit`, `places` and `reference`), `add_drawing_note`, `add_drawing_hole_note`,
`add_drawing_centermark`, `add_drawing_balloon`, `add_drawing_table`, `add_drawing_parts_list`,
`edit_drawing_annotation`, `delete_drawing_annotation` and `export_drawing`. A section or detail
view is `add_drawing_view` with `section_of` or `detail_of`; a view of everything is
`assembly: true`. `edit_drawing` with `sheets` sets how many sheets there are, and views, notes and
tables take a `sheet`.
