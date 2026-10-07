# Operations

Each operation is one toolpath with one tool. Add them under a setup in the order the machine will
run them.

## Add an operation

1. Select the setup in the browser (or one of its operations). Without a selection, the last setup
   is used.
2. Click a **MILL 2D** tool: **Facing**, **Adaptive Clearing**, **Pocket**, **Contour**,
   **Drilling**, **Chamfer**, **Trace**, **Bore**, **Thread Mill** or **V-Carve**. (Only four are
   shown at once; click the panel name **MILL 2D** for the rest.) **Program Stop** is under
   **ACTIONS**.
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
    | **Rest machining after** | An earlier operation with a bigger tool: cut only what it couldn't reach (corners narrower than it, gaps) |
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
| **Feed up for chip thinning** | A light sideways cut makes thin chips: feed faster so they're full thickness again (never past the machine's limit). The card says how much |
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
    | **Finishing pass** | Roughing leaves this much more, then finishing passes at full depth |
    | **Finishing passes** | Take that stock off in this many passes |
    | **Spring pass** | The last pass again, to take off what the tool sprang away from |
    | **Tabs**, **Tab width**, **Tab height** | Bridges that hold the part to the stock (up to 24) |
    | **Tab spacing** | One tab every this far round each outline, instead of a count |
    | **Tab shape** | **Flat** (square steps) or **Triangle** (up a slope and down: easier to break off) |
    | **Direction** | Climb or conventional |

3. Under **Linking**:

    | Field | |
    |---|---|
    | **Entry** | **Ramp along the wall** (down to each depth at the ramp angle, never straight down into material) or **Plunge** |
    | **Lead-in radius** | Arcs on and off the wall |
    | **Lead-in length** | A straight lead on and off: square to the wall, or onto the arc |
    | **Compensation** | Who offsets the tool from the wall (below) |

    Leads aren't used with **Side: On**.

### Cutter compensation

- **Computer** (default): InvictusCAD offsets the path by the tool's radius. The program is the
  tool's center.
- **Control**: the program follows the wall itself and turns on G41/G42 with the tool's diameter
  offset, so the controller offsets it by the radius in its tool table. The toolpath shown is the
  wall, not the tool's center.
- **Wear**: the computer's path, with compensation on as well, so you can enter small wear
  corrections at the machine (a part a little big: a little more wear).

With **Control** and **Wear**, the lead-in gets a straight part at least the tool's radius long:
the controller needs it to switch compensation on. GRBL has no cutter compensation; its post
reports an error.

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

3. Set the options:

    | Field | |
    |---|---|
    | **Peck depth** | Peck and chip break. 0: the drill's diameter |
    | **Peck decrease**, **Shortest peck** | Each peck shorter than the last, down to the shortest (deep holes) |
    | **Dwell (s)** | Seconds at the bottom (dwell cycles) |
    | **Full diameter at the bottom** | Deeper by the point's length, so the full diameter reaches the bottom |
    | **Spot diameter** | Spot drills and countersinks: as deep as makes this diameter at the top |
    | **Break-through**, **Break-through feed** | The last stretch of each hole at a gentler feed, so the drill doesn't grab as it breaks out |

Drilling feeds at the plunge rate. GRBL has no canned cycles, so its post writes the moves out.
Shorter pecks and break-through feeds aren't part of any canned cycle either: with those, every
post writes the moves.

## Chamfer

Breaks edges with a pointed tool: a chamfer mill, spot drill, countersink or V-bit. Only pointed
tools are offered.

1. Click the **Edges** field, then edges, or a face: its outline is chamfered on the side you
   choose and the holes and pockets in it from the other side.
2. Set **Side** (**Outside** a part's outline, **Inside** a hole or pocket, or **On** a line for a
   V-groove), **Chamfer width** (across the top face) and **Tip offset** (how far the point goes
   below the chamfer, so it cuts with the cone and not the tip).

The tool's cone cuts the chamfer in one pass. A chamfer wider than the cone can reach is refused.
Leads work as for a contour.

## Trace

Follows curves with the tool's center: engraving lines and lettering, slots, grooves.

1. Click the **Curves** field, then sketch curves, text, edges or faces (every curve of a face,
   letters' insides too).
2. Set the **Depth** below the curves, or with a V-bit or engraver a **Line width** (the groove's
   width at the top, which sets the depth). **Stepdown** splits it into passes.
3. **Ramp into each depth** (on by default) reaches each depth along the curve at the ramp angle
   instead of plunging. Closed curves are cut in the cutting direction, open ones back and forth.

## V-Carve

Carves lettering, logos or any region with a V-bit, so the walls are the bit's cone: wide parts
deep, thin parts shallow, sharp into corners.

1. Click the **Floor or region** field, then sketch lettering, a sketch region or a flat face.
2. Set a **Maximum depth** to keep wide parts flat at that depth (0: as deep as they are wide), and
   the **Ring spacing** (0: a tenth of the bit's radius).

The bit cuts rings in from the outline, each at the depth that puts the cone's edge on the
outline. A region wider than the bit can reach needs a maximum depth or a bigger bit; a bit whose
flat tip is wider than a stroke can't carve that stroke.

## Bore

Mills holes by circling down a helix: holes bigger than the drills you have, or exact sizes.

1. Click the **Holes** field, then hole walls or circles.
2. Set the passes:

    | Field | |
    |---|---|
    | **Side** | **Inside a hole** (default), or **Outside a boss** |
    | **Stepover** | Between rings: big holes are cleared ring by ring from the middle out, so no pillar is left |
    | **Down per turn** | The helix's pitch. 0: from the ramp angle |
    | **Wall stock** | Left on the wall |
    | **Rings** | Bosses: rings the stepover apart, ending at the size |
    | **Spring pass** | A second circle at the bottom |

Each ring ends with a full circle at the bottom. Feeds are adjusted so the cutting edge, not the
tool's center, moves at the feed.

## Thread Mill

Cuts threads with a thread mill: inside holes (drilled to the minor diameter) or outside bosses.
Only thread mills are offered.

1. Click the **Holes** field, then hole walls or circles.
2. Set the thread:

    | Field | |
    |---|---|
    | **Side** | **Inside a hole** or **Outside a boss** |
    | **Pitch** | 0: the tool's |
    | **Major diameter** | 0: a boss's own size, or a hole's plus the thread (ISO: 1.0825 × pitch) |
    | **Hand** | **Right** or **Left** |
    | **Radial passes** | The thread's depth taken in this many passes |
    | **Thread depth** | Across. 0: 0.5413 × pitch inside, 0.6134 × pitch outside |
    | **Spring pass** | The last pass again |

The tool arcs on from the hole's center (or from outside a boss), climbs the helix one pitch a
turn and arcs off. Climb milling: inside, a right-hand thread is cut from the bottom up; outside,
from the top down.

## Program Stop

Stops the program between operations: to flip the part, clear chips, or check a size. The spindle
and coolant stop, your **Message** shows on the controller, and the machine waits for Cycle Start.
**Only on optional stop (M1)** stops only when the controller's optional stop switch is on. The
next operation starts the spindle again.
