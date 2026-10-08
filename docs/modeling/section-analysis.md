# Section Analysis

A section analysis shows the model cut open along a plane, so you can see walls, holes and
pockets from the inside. The cut faces are filled in the body's color and hatched. It changes
nothing in the model: hide it and the whole part is back.

1. Choose **INSPECT › Section Analysis**.
2. Click a plane or a flat face to cut along: an origin plane, a
   [reference plane](reference-planes.md) or a face of a body. The side the plane faces is cut
   away.
3. Set the card's values. A teal outline shows where the cut is while the card is open.

    | Value | What it does |
    |---|---|
    | **Distance** | Moves the cut along the plane's normal. Drag the arrow in the view, or type a value. |
    | **Tilt** | Leans the cut about the plane's own X direction, in degrees. |
    | **Turn** | Leans the cut about the plane's own Y direction, in degrees. |
    | **Flip** | Cuts away the other side. |

4. Click **OK**.

The section goes into the browser's **Analysis** folder. From there you can:

- click its eye to show or hide the cut;
- double-click it to change it;
- delete it.

Sections are saved with the project. If the plane or face it was made from moves, the section
follows. Several sections can be shown at once; the view then shows only what is on the kept side
of all of them.
