# Patterns and Mirror

Copy features (extrudes, revolves, sweeps, lofts, holes) in a row or grid, around an axis, along
a path, or across a plane. The copies follow the original when you change it.

To repeat geometry inside a sketch instead, see [sketch patterns](../sketching/editing.md#patterns).

## Make a pattern

1. Choose **MODIFY › Rectangular Pattern**, **Circular Pattern** or **Path Pattern**.
2. Click the **Features** field, then a face of each feature to copy: clicking a face picks the
   feature that made it. Leave it empty to copy the whole body.
3. Fill in the rest:

    | Pattern | Fields |
    |---|---|
    | **Rectangular** | **Direction** (a line, edge or axis), **Count**, **Spacing** (negative goes the other way). Optional **Direction 2**, **Count 2**, **Spacing 2** for a grid |
    | **Circular** | **Axis**, **Count**, **Angle** (360° spreads them evenly around) |
    | **Path** | **Path** (edges or sketch curves), **Count**, **Spacing** (0 spreads them over the whole path), **Turn with the path** |

4. Click **OK**.

## Mirror

1. Choose **MODIFY › Mirror Features**.
2. Pick the **Features** (or nothing, for the whole body).
3. Pick the **Plane**: XY, XZ, YZ, a [reference plane](reference-planes.md), or a flat face.
4. Click **OK**.

!!! tip
    Model half of a symmetric part and mirror it. Changes to the half you modeled show up on both
    sides.

If InvictusCAD can't tell which body to change, set the **Body** field at the bottom of the card.

Double-click a pattern or mirror in the browser to change it.
