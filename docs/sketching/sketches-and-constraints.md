# Sketches and Constraints

Most parts start as a **sketch**: 2D geometry on a plane (XY, XZ, YZ, a
[reference plane](../modeling/reference-planes.md), or a flat face) that you then extrude,
revolve, sweep or loft.

## Drawing tools

Lines, rectangles, circles, arcs (3-point and center), polygons, slots, splines and points. Any
of them can be **construction geometry**: it guides constraints but isn't part of the profile.

Editing tools: sketch fillet and chamfer, trim, extend, offset, mirror, explode, and patterns
(rectangular, circular, along a path).

## Constraints and dimensions

Geometric constraints (coincident, horizontal, vertical, parallel, perpendicular, tangent, equal,
symmetric, and more) and dimensions are solved live as you drag.

- The sketch shows how many **degrees of freedom** remain. A fully constrained sketch can't move
  by accident.
- A constraint that conflicts with existing ones, or adds nothing, is **refused with a reason**
  instead of breaking the sketch.
- Dimensions accept [expressions and parameters](../getting-started/units-and-expressions.md).

## Profiles

Closed regions become profiles you can extrude. A shape inside another is a hole: a circle inside
a rectangle extrudes as a plate with a hole.

## Projecting geometry

**Project** brings body edges, faces, vertices or another sketch's geometry onto the sketch plane
as linked, fixed geometry. It follows its source when the source changes.
