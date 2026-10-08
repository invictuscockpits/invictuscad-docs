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

1. Choose **MODIFY › Mirror**.
2. Choose what to mirror:
    - **Features:** click a face of each feature to copy. The copies join the same body, mirrored.
    - **Bodies:** pick bodies. Each gets a mirrored copy as a body of its own.
    - **Components:** click placed components. Each gets an opposite-hand copy as a new component,
      named after the original with "Mirror" added. Use it for left- and right-hand parts.
3. Pick the **Plane**: XY, XZ, YZ, a [reference plane](reference-planes.md), or a flat face.
4. Click **OK**.

Mirrored bodies and components follow their originals: change the original and the copy changes
with it.

!!! tip
    Model half of a symmetric part and mirror its features. Changes to the half you modeled show up
    on both sides.

Double-click a pattern or mirror in the browser to change it.
