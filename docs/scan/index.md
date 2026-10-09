# Scan to CAD

The **Scan to CAD** workspace turns a 3D scan of a real part into a model you can edit. You bring
in the scan, clean it up, and fit planes, cylinders and other shapes to it. Then you line it up
with the model's axes, cut sections through it into sketches, and model over it with the usual
tools. At the end you can check the model against the scan, point by point.

Click **Scan to CAD** in the sidebar on the left (++ctrl+3++). The toolbar changes to the
workspace's own panels:

| Panel | Tools |
|---|---|
| MESH | Import Scan, Clean Up, Fill Holes, Smooth, Reduce, Mesh Points, Fix Normals, Flip Normals, Convert to Body, Export Scan |
| REGIONS | Auto Regions, Show Regions |
| FIT | Fit Plane, Fit Cylinder, Fit Cone, Fit Sphere |
| ALIGN | Align, Move Scan |
| MODEL | Section Sketch, Outline Sketch, then Design's Sketch, Extrude, Revolve, Sweep, Loft, Reference Plane, Fillet, Chamfer, Combine and Hole |
| INSPECT | Deviation, Measure, Section Analysis |

## The steps

A typical scan becomes a model like this:

1. **Bring the scan in** and **clean it up**: remove loose bits, fill holes and smooth out noise
   (this page).
2. **Find its regions**, so you can see which areas are flat, round or freeform, and **fit**
   planes and axes to the important ones ([Fit and Align](fit-and-align.md)).
3. **Align** the scan to the model's axes using those fits, so the bottom sits on XY and the main
   bore runs along Z ([Fit and Align](fit-and-align.md)).
4. **Cut sections** into sketches of lines and arcs, then dimension and constrain them and
   extrude or revolve them ([Model and Compare](model-and-compare.md)).
5. **Compare** the model with the scan, and fix what's off ([Model and Compare](model-and-compare.md)).

## Bring in a scan

Choose **MESH › Import Scan** (also in **☰ › File**) and pick the file. InvictusCAD reads:

| Format | What it is |
|---|---|
| **STL** | Triangle mesh, text or binary. Every scanner exports it |
| **OBJ** | Triangle or polygon mesh |
| **PLY** | Mesh or point cloud, text or binary |
| **XYZ, ASC, TXT, CSV, PTS** | Point cloud: one point a line, `x y z`, optionally followed by its normal |

The scan goes into the browser's **Scans** folder, named after its file. It is reference
material, not a body: it doesn't join in features, and you can hide it with its eye. It is saved
inside the project, as cleaned up.

The scan's numbers are taken as millimeters. A scanner that works in other units (rare) can be
brought in through the [MCP command](../automation/mcp.md) `import_scan` with its `unit`.

!!! tip "Point clouds"
    A point cloud can be cleaned of stray points, thinned, aligned and compared as it is. Fits,
    regions and sections need a mesh: **MESH › Mesh Points** makes one (see below).

## Clean it up

Scans usually arrive with some mess: specks floating near the part, holes where the scanner
couldn't see, and noise on every surface. Each tool opens a card. The **Scan** field is filled in
with the scan selected in the browser, or the last one brought in. Each clean-up is one undo
step. On a big scan the work runs in the background with a busy cursor, and you can keep looking
around meanwhile.

| Tool | What it does |
|---|---|
| **Clean Up** | Removes loose bits smaller than **Keep pieces over** (a share of the largest piece). It also removes triangles with no area, repeats, and triangles past the second on an edge, and turns all the triangles to face outward |
| **Fill Holes** | Outlines in green the holes it will fill: those up to **Largest hole** across, measured at the widest. Every hole has a dot; click it to leave that hole out, or to add one that's larger. The card counts the holes and how many will be filled. Holes are filled with triangles the scan's own size, blended into the surface around. **Flat** closes each with one flat face in its own plane instead, and openings inside it in that plane stay open through it |
| **Smooth** | Evens out noise without shrinking the part or rounding its sharp edges. **Passes** says how many times, **Strength** how hard (0–100) |
| **Reduce** | Keeps **Keep** % of the triangles. Flat areas lose the most, curved ones keep their detail. A point cloud is thinned instead |
| **Fix Normals** | Turns every triangle to face outward (for a scan that shades dark in places) |
| **Flip Normals** | Turns every triangle the other way |

!!! tip "A scan with an open bottom"
    A part scanned standing on a table has no bottom: its scan is open there. To close it, open
    **Fill Holes**, set **Largest hole** to **0** so every opening has a dot, and leave only the
    bottom's dot chosen. Then tick **Flat** and click **Fill**. The bottom is closed with one flat
    face, and any holes going through the part stay open through it. To sit the scan on the floor
    when you align it, use [Rest on plane](fit-and-align.md#align-the-scan).

Clean-ups change the triangles, so a scan's [regions](fit-and-align.md#auto-regions) are cleared
by them. Run Auto Regions again afterwards. Fits you already made stay.

## Mesh a point cloud

**MESH › Mesh Points** turns a point cloud into a triangle mesh, so you can fit shapes to it,
find its regions and cut sections through it. It works out which way the surface faces at each
point from its neighbors, then traces the surface through the points. Where the scanner saw
nothing, the mesh has holes, as a scan from a mesh would. **Fill Holes** closes them.

| Value | What it does |
|---|---|
| **Detail** | The size of the mesh's triangles. **0** works it out from how closely the points are spaced; larger is coarser, smoother and quicker |

Clouds that came with normals (PLY files often carry them) use those.

## Convert a scan to a body

**MESH › Convert to Body** makes a body straight from the scan's triangles, where the scan is now.
A closed scan becomes a solid, with each flat area merged into a single face. An open scan becomes
a surface (fill its holes first for a solid). It's for scans you want to use as they are, such as
a sculpted shape to combine with modeled parts or to 3D-print. It works on scans of up to 150,000
triangles, so **Reduce** bigger ones first.

## Export a scan

**MESH › Export Scan** writes the scan as it is now (cleaned up and aligned, in the model's
coordinates) to STL, PLY, OBJ or XYZ points.
