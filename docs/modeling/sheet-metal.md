# Sheet Metal

Sheet metal parts are bodies of one thickness: flat walls joined by bends. InvictusCAD knows each
part's **rules** (thickness, bend radius and K-factor) and unfolds it into a **flat pattern**: the
blank to cut, with its bend lines, ready for a laser, plasma or punch.

## The Sheet Metal tab

In the Design workspace, the two tabs left of the tools choose which tools show:

| Tab | Tools |
|---|---|
| **SOLID** | Everything for solid parts (the usual panels) |
| **SHEET METAL** | **CREATE**: Sketch, Flange, Edge Flange, Hole, Reference Plane. **MAKE**: Flat Pattern, Nest Parts. MODIFY, ASSEMBLE and INSPECT as on the Solid tab |

Editing a sheet metal feature (double-click it in the browser) switches to the Sheet Metal tab.

## Start a part: Flange

A **Flange** starts a sheet metal part and sets its rules. It works from a sketch in two ways:

- **A closed sketch** (a rectangle, any outline with holes): a flat plate the thickness.
- **An open profile of lines** (an L, a U, a hat section): a bent part. Each corner becomes a bend,
  the lines are one face of the sheet, and the part runs **Width** along the sketch's normal.

1. Draw the sketch, then choose **SHEET METAL › CREATE › Flange**.
2. Click the sketch for **Profile**.
3. Set the rules and size:

    | Field | |
    |---|---|
    | **Thickness** | The sheet's thickness |
    | **Bend radius** | The inside radius of every bend. 0 uses the thickness |
    | **K-factor** | Where the neutral layer sits, as a share of the thickness from the inside of a bend (0.44 by default). It sets how long each bend is when flat. Use your shop's or supplier's value |
    | **Width** | Open profiles: how far the part runs from the sketch |
    | **Thickness side** | Open profiles: the thickness to the left or right of the lines, walking them from the first |
    | **Both ways** | Open profiles: half the width each way from the sketch |
    | **Flip** | The thickness (plates) or width (profiles) the other way |

4. Click **OK**.

The rules belong to the body: edge flanges and the flat pattern use them.

## Add a wall: Edge Flange

1. Choose **SHEET METAL › CREATE › Edge Flange**.
2. Click a straight edge along the outside of the sheet.
3. Set **Angle** (90° by default), **Length** (the flat wall past the bend), and **Bend radius**
   (0 uses the part's). **Flip** bends it the other way.
4. Click **OK**.

## Flat Pattern

1. Select the part, then choose **SHEET METAL › MAKE › Flat Pattern**.
2. The blank appears beside the part, with its bend lines. The card shows its size, how many bends
   it has, and the thickness.
3. Optionally click **Fixed face**: the flat face that stays put, which sets how the blank is
   oriented. By default it's the largest flat face.
4. Choose **DXF** or **SVG** and click **Save...**.

| Layer | DXF color | What's on it |
|---|---|---|
| **CUT_OUTSIDE** | Red | The outline |
| **CUT_INSIDE** | Green | Holes and cutouts. Round holes come out as true circles, even across a bend's edge |
| **BEND** | Magenta | Bend lines, down the middle of each bend |

Each bend is laid out at the length of its neutral layer: (inside radius + K-factor × thickness) ×
bend angle.

### Imported parts unfold too

The flat pattern works from the part's shape, not its history. A STEP file of a sheet metal part
from any CAD program unfolds as long as it is made of flat walls and cylindrical bends of one
thickness. On a part without InvictusCAD rules, the card measures the thickness and starts the
K-factor at 0.44; change them to match how the part will be made.

**MAKE › Export Flat** and **Nest Parts** also unfold sheet metal parts, so you can nest blanks
straight onto a sheet (see [Nest Parts on Sheets](../making/nesting.md)).
