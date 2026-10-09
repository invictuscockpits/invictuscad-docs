# Patterns and Mirror

Copy features, whole bodies or components in a row or grid, around an axis, along a path, or
across a plane. The copies follow the original when you change it.

To repeat geometry inside a sketch instead, see [sketch patterns](../sketching/editing.md#patterns).

## Make a pattern

1. Choose **MODIFY › Rectangular Pattern**, **Circular Pattern** or **Path Pattern**.
2. Choose what to pattern:
    - **Features:** click a face of each feature to copy (extrudes, revolves, sweeps, lofts,
      holes): clicking a face picks the feature that made it. The copies are made in the same
      body, as more of its features.
    - **Bodies:** pick bodies. Each copy becomes a body of its own, named after the original
      (*Bracket (2)*, *Bracket (3)*...).
    - **Components:** click placed components. Each copy becomes another instance of the
      component, so every copy changes when you edit it.
3. Fill in the rest:

    | Pattern | Fields |
    |---|---|
    | **Rectangular** | **Direction** (a line, edge or axis), **Count**, **Spacing** (negative goes the other way). Open **Second direction** for a grid |
    | **Circular** | **Axis**, **Count**, **Angle** (360° spreads them evenly around) |
    | **Path** | **Path** (edges or sketch curves), **Count**, **Spacing** (0 spreads them over the whole path), **Follow path** |

    For bodies and components, the copies show in green where they'll go.

4. Click **OK**. All the copies are one undo step.

Patterned bodies follow their original: change it and every copy changes with it. Each copy is its
own body in the browser, which you can hide, color or delete on its own.

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

Double-click a pattern or mirror in the [History panel](history.md#the-history-panel) to change it. A pattern of bodies or components is one step there: change its count or spacing and copies are added, removed or moved to match. Deleting it deletes its copies.
