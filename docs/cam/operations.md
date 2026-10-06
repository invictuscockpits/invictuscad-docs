# Operations

Each operation is one toolpath with one tool. Add them under a setup in the order the machine will
run them.

## Add an operation

1. Select the setup in the browser (or one of its operations). Without a selection, the last setup
   is used.
2. Click a **MILL 2D** tool: **Facing**, **Adaptive Clearing**, **Pocket**, **Contour** or
   **Drilling**. (Only four are shown at once; click the panel name **MILL 2D** for the rest.)
3. Fill in the card. The toolpath previews as you change values. If it can't be made, the card
   says why and **OK** stays disabled.
4. Click **OK**.

Double-click an operation in the browser to change it later.

!!! note
    You need a setup and a tool library first. If either is missing, InvictusCAD says so and opens
    the setup card or the Tool Library.

## Every operation: tool and speeds

| Field | |
|---|---|
| **Tool** | From your [libraries](tool-libraries.md). Drilling lists every tool; the others list milling tools only |
| **Preset** | **The tool's first**, or a named preset |
| **Coolant** | **The preset's**, or Off, Flood, Mist, Air |
| **Speed (rpm)**, **Feed (per min)**, **Plunge (per min)** | **0** uses the preset. A value here overrides it for this operation |

## Every operation: heights

Open the **Heights** section to change where the cut starts and stops.

- **Top** and **Bottom** each come from **Stock top**, **Stock bottom**, **Model top**,
  **Model bottom**, **Selection** (the geometry you picked) or **Work zero**, plus an **offset**
  (negative goes deeper).
- **Clearance**: the safe height for moves between areas (default 15 mm above the stock).
- **Retract**: where the tool lifts to between passes (default 5 mm above the top).

Unless you change them, facing cuts from the stock top down to the model top; pockets and adaptive
clearing down to the floor you picked; contours to the model bottom; drilling each hole from its
top to its bottom.

## Facing

Flattens the top of the stock. It needs no geometry: it covers the stock's outline.

| Field | |
|---|---|
| **Pattern** | **Spiral** (one continuous path from the outside in, the default), **Zigzag** or **One way** |
| **Angle** | Direction of the passes (zigzag and one way) |
| **Start in the middle** | Spiral outward instead (spiral only) |
| **Stepover** | 0: the preset's, otherwise 70% of the diameter |
| **Stepdown** | 0: the preset's, otherwise everything in one pass |
| **Direction** | **Climb** or **Conventional** |

## Pocket

Clears the material inside a closed outline down to a floor.

1. Click the **Floor or region** field, then a flat floor face, a closed sketch region, or the
   outline's edges or sketch curves. A click takes the whole loop; **Shift**+click takes one edge.
2. Set the passes:

    | Field | |
    |---|---|
    | **Stepover** | 0: the preset's, otherwise 40% of the diameter |
    | **Stepdown** | Depth per level |
    | **Wall stock**, **Floor stock** | Material to leave for a finishing pass |
    | **Finish the walls** | A last pass along the walls at full depth (on by default) |
    | **Direction** | Climb or conventional |

3. Under **Linking**, choose the **Entry**: **Helix** (default), **Ramp** or **Plunge**, with its
   **Ramp angle** and **Helix radius**. **Stay down between rings** avoids lifting between passes.

The floors you pick must all be at one depth.

## Adaptive Clearing

Roughs out a pocket with a constant, light engagement, so you can take deep cuts at high feed
without overloading the tool. Pick geometry as for a pocket.

| Field | |
|---|---|
| **Optimal load** | How much of the tool engages sideways. 0: 15% of the diameter. At most half the diameter |
| **Stepdown**, **Wall stock**, **Floor stock**, **Direction** | As for a pocket |
| **Helix angle**, **Helix radius** | How it enters the material (under **Linking**) |

Follow it with a pocket or contour to finish the walls and floor.

## Contour

Cuts along an outline: around the outside of a part, inside a hole, or along a line.

1. Click the **Outline** field, then faces (their outer edge), sketch regions, or edges and sketch
   curves. Closed outlines are cut on the chosen side; open ones along their center.
2. Set the passes:

    | Field | |
    |---|---|
    | **Side** | **Outside** (default), **Inside**, or **On** the line |
    | **Stepdown**, **Wall stock** | |
    | **Finishing pass** | Roughing leaves this much more, then one pass at full depth |
    | **Tabs**, **Tab width**, **Tab height** | Bridges that hold the part to the stock (up to 24) |
    | **Direction** | Climb or conventional |

3. Under **Linking**, a **Lead-in radius** arcs on and off the wall (not used with **Side: On**).

## Drilling

Drills, pecks, bores or taps holes.

1. Click the **Holes** field, then hole walls, circles or arcs (their center is used), or points.
   The two walls of a counterbored hole count as one hole. Holes are drilled in the shortest order.
2. Choose the **Cycle**:

    | Cycle | G-code |
    |---|---|
    | **Drill** | G81 |
    | **Peck (full retract)** | G83 |
    | **Chip break** | G73 |
    | **Drill, dwell** | G82 |
    | **Bore (feed out)** | G85 |
    | **Bore, dwell** | G89 |
    | **Tap** | G84 (feed from the tap's pitch) |

3. Set **Peck depth** (peck and chip break), **Dwell (s)**, and **Full diameter at the bottom** to
   drill deep enough that the tip's cone clears the hole bottom.

Drilling feeds at the plunge rate. GRBL has no canned cycles, so its post writes the moves out.
