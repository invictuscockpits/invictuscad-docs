# Editing Your Model

## Features remember their inputs

Every feature keeps what you gave it: its sketch, its values, the edges and faces it uses.
Change any of them and the model rebuilds from that point on.

- **Change a sketch:** double-click it in the browser, edit it, finish it.
- **Change a feature:** double-click it under **Features** in the browser, change its values,
  click **Update** (or **OK**).

Later features keep working because faces and edges are named after the features that made them.
A fillet stays on "the edge between Extrude1's end and its side" even when Extrude1 gets longer.

## When something no longer builds

If a change makes a later feature impossible, such as a fillet too big for a shortened edge, that
feature turns **red** in the browser. Hover it to see why. Fix it by editing the feature, or
undo the change.

## Undo and redo

++ctrl+z++ undoes one step; ++ctrl+y++ redoes it. Hover the undo button to see what it would undo.
Each tool's result is one step, including everything an [AI assistant](../automation/mcp.md) does in
one go.

## Delete

Select bodies, sketches or planes in the browser (or click a body in the view) and press
++delete++, or choose **MODIFY › Delete**. A body takes its features with it. Something still used
by another feature can't be deleted; the message says what uses it.

!!! note
    Single features can't be deleted yet. Undo them, or delete the body.

## Box

**CREATE › Box** adds a 100 × 50 × 25 mm box: a quick body to try things on.
