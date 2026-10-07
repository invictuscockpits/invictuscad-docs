# Canvases

A canvas is a picture on a plane to trace over: a photo of a part, a scanned drawing, a logo. It
isn't geometry: nothing is built from it, sketches just draw over it. The picture goes into the
project, so it opens without the original file.

## Insert a canvas

1. Choose **CREATE › Canvas**.
2. Pick the picture (PNG, JPEG, GIF or BMP).
3. Click where it goes: an origin plane, a reference plane, or a flat face.

The **Canvas** card opens. The picture starts at 96 pixels per inch, so calibrate it before you
trace.

## Calibrate it

Calibrating sets the picture's true size from something on it whose length you know: a dimension
on a drawing, a ruler in a photo, a part's known width.

1. On the **Canvas** card, click **Calibrate...**.
2. Click where the known length starts on the picture, then where it ends.
3. Type how long it really is (units and arithmetic work: `2.5in`, `63.5`) and press ++enter++.

The picture is scaled about the first point, which stays put.

!!! tip
    Use the longest known length you can find on the picture: a small error in where you click
    matters less over a long distance.

## Place, fade and flip it

| Field | |
|---|---|
| **Width** | The height follows the picture's proportions |
| **Center X**, **Center Y** | Where its center is on the plane |
| **Angle** | Turn it to line up with the plane's axes |
| **Opacity** | Fade it so your sketch stands out |
| **Flip** | **Horizontal** or **Vertical**: mirror it (a photo of the back of a part) |

Each change is a step you can undo. Double-click a canvas in the browser to open its card again;
hide it with its eye in the **Canvases** folder, or delete it like anything else.

Over MCP, `insert_canvas`, `edit_canvas` and `calibrate_canvas` do the same.
