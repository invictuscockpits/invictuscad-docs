# Navigating and Selecting

## Move the view

| Action | Mouse |
|---|---|
| **Pan** | Middle-drag |
| **Orbit** | Right-drag, or ++shift++ + middle-drag |
| **Zoom** | Mouse wheel (zooms toward the cursor) |
| **Fit everything** | ++f++ or ++home++ (in a sketch, fits the sketch) |

Orbiting turns around the model's center and has no stop at the top or bottom, so you can roll
right over it.

## Standard views

- **View cube** (top right): click a face, edge or corner to look from there.
- **☰ › View**: **Front**, **Top**, **Right** and **Isometric**.

## Select

Left-click to select a face, edge or vertex. Hold ++ctrl++ or ++shift++ to add or remove.
++esc++ clears the selection.

The **SELECT** buttons in the top bar choose what clicks can pick. Turn off faces, for example,
to pick edges easily. Some tools set this for you: Fillet and Chamfer pick edges, Shell, Hole and
Thread pick faces.

When one thing is selected, its name and size appear at the bottom of the view: the face's area,
an edge's length or diameter, a vertex's coordinates. To measure between things, use
[Measure](../modeling/measure.md).

![A selected face](../assets/images/selected-face.png)

## How things are named

Bodies, sketches and features get names such as `Body1`, `Sketch2` and `Extrude1`. These names are
permanent; renaming in the browser only changes the label you see. Faces and edges are named after
the features that made them (`Body1/Extrude1.end` is the end face of Extrude1), which is how later
features keep finding them after you edit earlier ones.
