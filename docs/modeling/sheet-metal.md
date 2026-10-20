# Sheet Metal

Sheet metal parts are bodies of one thickness: flat walls joined by bends. Cahaba Studio knows each
part's **rules** (thickness, bend radius, K-factor, and optionally a bend table) and unfolds it
into a **flat pattern**: the blank to cut, with its bend lines, ready for a laser, plasma or punch.

## The Sheet Metal tab

In the Design workspace, the tabs in the row above the tools choose which tools show:

| Tab | Tools |
|---|---|
| **SOLID** | Everything for solid parts (the usual panels) |
| **SHEET METAL** | **CREATE**: Sketch, Extrude, Flange, Hem, Convert to Sheet Metal, Hole, Reference Plane. **MAKE**: Edit Flat Pattern, Export Flat Pattern, Nest Parts, DXF Builder. MODIFY, ASSEMBLE and INSPECT as on the Solid tab |

Editing a sheet metal feature (double-click it in the [History panel](history.md#the-history-panel)) switches to the Sheet Metal tab.

## Start a part

There are two ways to make a sheet metal part.

### Flange

**Flange** does two jobs: it starts a sheet metal part from a sketch, or it bends walls up from
a part's edges ([below](#add-a-wall-flange-on-edges)). Choose it with a sketch selected in the
browser (or before there's any part) and it starts a part; otherwise click a sketch on its card
to switch to starting one.

Started from a sketch, a flange sets the part's rules. It works in two ways:

- **A closed sketch** (a rectangle, any outline with holes): a flat plate the thickness.
- **An open profile of lines** (an L, a U, a hat section): a bent part in one step. Each corner
  becomes a bend, the lines are one face of the sheet, and the part runs **Width** along the
  sketch's normal.

1. Draw the sketch, select it in the browser, then choose **SHEET METAL › CREATE › Flange**.
2. Click the sketch for **Profile**.
3. Set the rules and size:

    | Field | |
    |---|---|
    | **Thickness** | The sheet's thickness |
    | **Bend radius** | The inside radius of every bend. It starts at the material's typical radius for the thickness ([below](#bend-radius)); type your own to change it |
    | **K-factor** | Where the neutral layer sits, as a share of the thickness from the inside of a bend. It sets how long each bend is when flat. It starts at the part's material's value (see below); change it to use your own |
    | **Width** | Open profiles: how far the part runs from the sketch |
    | **Thickness side** | Open profiles: the thickness to the left or right of the lines, walking them from the first |
    | **Both ways** | Open profiles: half the width each way from the sketch |
    | **Flip** | The thickness (plates) or width (profiles) the other way |
    | **Bend table** | Optional: your shop's bend figures (see [Bend tables](#bend-tables)) |

4. Click **OK**.

### Convert to Sheet Metal

A plate you made with **Extrude**, or a part imported from a STEP file, becomes sheet metal with
**SHEET METAL › CREATE › Convert to Sheet Metal**. Pick the body. Its shape doesn't change; it
gets rules. **Thickness** 0 measures it; **Bend radius** starts at the material's typical radius.

Edge flanges and hems also work on a plain plate that hasn't been converted: they measure the
sheet's thickness at the edge you pick.

## The K-factor and the material

When a part's rules don't set a K-factor, it comes from the part's
[physical material](materials-and-appearances.md): typical air-bending values, such as 0.43 for
5052 aluminum, 0.44 for mild steel, 0.45 for 304 stainless and 0.40 for copper. A part with no
material uses 0.44. Change the material and the flat pattern follows. Type a K-factor on the
Flange or Convert to Sheet Metal card to set your own, whatever the material.

### Bend radius

Unless you type one, a new part's bend radius is what the material actually bends to at that
thickness. For the materials SendCutSend bends (5052 aluminum, mild steel, 304 and 316
stainless, brass and copper) it's the radius in [their published bend
specs](https://sendcutsend.com/bending-calculator/#bend-specs), so a part you send them folds as
modeled. Between two of their thicknesses it's in proportion. For other materials it's a common
shop minimum: 2 thicknesses for 6061-T6, 3 for 7075, 2024 and titanium, 1 to 2.5 for the other
steels, more for thick plate. A part with no material bends at 1 thickness. The radius is set
when the part is made and kept with it, so changing the material later doesn't change parts
you've already made: type a new **Bend radius** for that.

## Add a wall: Flange on edges

1. Choose **SHEET METAL › CREATE › Flange**.
2. Click a straight edge along the outside of the sheet; only edges are picked, not the faces
   beside them. Ctrl+click more edges to flange them all at once: each gets its own flange. Any
   plate works, even one extruded the ordinary way: its thickness is measured at the edge.
3. Set **Angle** (90° by default) and **Length** (the flat wall past the bend), or drag the arrow
   in the view. **Bend radius** 0 uses the part's (on a plate that isn't sheet metal yet, the
   material's typical radius). **Flip** bends it the other way.
4. Under **Extent**, **Offset 1** and **Offset 2** pull the flange in from the edge's ends, for a
   flange narrower than its edge. Each end pulled in gets a **Relief**, a slot cut into the sheet
   beside the bend so it doesn't tear: **Rectangular** or **Round**, or **None**. **Relief
   width** and **Relief depth** start at the material's (1 to 2 thicknesses wide, deeper than the
   bend); type your own to change them.
5. Click **OK**.

### Corners

Where two of the edges meet at a square corner of the sheet and the flanges are 90°, they close
the corner the way a blank folds up: both bends end at the corner, and each wall runs on past it
until its inside face is a small **Corner gap** (0.2 mm unless you change it) from the other's.
The walls' ends are square to them, as they're cut on the blank, so outside the corner there's a
notch the thickness of the sheet. The same goes where a flange meets one you made before with
another Flange: that one's wall runs on past the corner too. Under **Corners**, choose **Open**
to stop each wall at the end of its edge instead. Other corners (other angles, a corner that isn't square) stay open.

On the blank, the square where the two bends would cross is left out: that's the corner's
relief, and it's what **Corner relief** **Square** (the default) gives. To cut more round the
corner:

- **Square** with a **Relief size** bigger than a bend's length when flat: a bigger square,
  centered where the bends' middles cross.
- **Round**: a circle that size on the blank (0: a bend's length flat plus the thickness). It
  takes a little longer to work out.

## Hem

A **Hem** folds an edge right back over the sheet, to stiffen it or to take off a sharp edge.

1. Choose **SHEET METAL › CREATE › Hem** and click a straight edge along the outside of the sheet.
2. Set **Length** (the folded-back part) and **Gap** (between the hem and the sheet; 0 closes it).
   **Flip** folds it under instead of over. **Extent** works as for an edge flange.
3. Click **OK**.

## Work on the flat pattern

A sheet metal body has a **Flat Pattern** row under it in the browser. Double-click it, or choose
**SHEET METAL › MAKE › Edit Flat Pattern**, and the part lies flat. The face you had selected (or
its largest flat face) stays where it is, and the rest lies in its plane. Dashed lines across it
show where it bends.

**Export DXF**, beside **Finish Flat Pattern** at the top of the window, saves the blank for the
laser: its outline, its holes, and its bend lines on their own layer, with what you've done to
it flat.

Work on it like any part: sketch on it, cut through it, add holes, chamfer its corners, pocket or
engrave it. Then click **Finish Flat Pattern** at the top of the window (or double-click the row
again). The part folds back up with everything you did:

- On a flat wall, what you did moves across exactly: any depth, any shape.
- A cut across a bend wraps round it, through the sheet.
- Material added on a flat wall moves across too. Material added across a bend, or outside the
  blank, is refused.

The work stays in the part's history, between **Unfold** and **Fold** in the Features list.
Change a flange later and the part unfolds and folds again with it. The sketches you drew on the
flat part are hidden when it folds back. One undo opens it flat again.

## Export Flat Pattern

1. Select the part, then choose **SHEET METAL › MAKE › Export Flat Pattern** (or right-click its
   Flat Pattern row › **Export Flat Pattern...**).
2. The blank appears beside the part, with its bend lines. The card shows its size, how many bends
   it has, and the thickness.
3. Optionally click **Fixed face**: the flat face that stays put, which sets how the blank is
   oriented. By default it's the largest flat face.
4. Choose **DXF** or **SVG** and click **Save...**.

| Layer | DXF color | What's on it |
|---|---|---|
| **CUT_OUTSIDE** | Red | The outline |
| **CUT_INSIDE** | Green | Holes and cutouts. Round holes in walls come out as true circles |
| **BEND** | Magenta | Bend lines, down the middle of each bend |

Each bend is laid out at the length of its neutral layer: (inside radius + K-factor × thickness) ×
bend angle, unless a bend table covers it.

### Imported parts unfold too

The flat pattern works from the part's shape, not its history. A STEP file of a sheet metal part
from any CAD program unfolds as long as it's made of flat walls and bends of one thickness. The
bends can be **cylindrical** or **conical** (a bend whose radius grows along it, as in a tapered
flange). A conical bend unrolls into a ring sector. On a part without Cahaba Studio rules, the card
measures the thickness and starts the K-factor at the material's value.

**MAKE › Export Flat** and **Nest Parts** also unfold sheet metal parts, so you can nest blanks
straight onto a sheet (see [Nest Parts on Sheets](../making/nesting.md)).

## Bend tables

A bend table holds your shop's own figures for how long bends come out flat, from test bends on
your press brake. Put it in **Bend table** on the Flange or Convert to Sheet Metal card, a row
each:

```
# angle, inside radius, value
90, 2, 3.5
45, 2, 1.2
```

or on one line, rows between semicolons: `90, 2, 3.5; 45, 2, 1.2`. Leave the radius out
(`90, 3.5`) for a row that fits any radius. **Table gives** says what the values are:

- **Deductions** (the default): how much shorter the blank is than the two legs measured to where
  their outsides meet.
- **Allowances**: the bend's own length when flat.

Between two angles in the table it interpolates. A bend the table doesn't cover uses the K-factor.
