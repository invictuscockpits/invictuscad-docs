# CAM: From Model to G-code

The **CAM workspace** turns your bodies into G-code for a CNC mill or router. You pick a machine,
describe the stock and where zero is, add operations that each use one tool, then post a program
for your controller.

The pieces, in the order you use them:

| Piece | What it is | Page |
|---|---|---|
| **Machine** | Travels, feeds, spindle ranges, coolant and the post (controller) it uses | [Machines](machines.md) |
| **Tool library** | Your cutters and their cutting presets (speeds and feeds) | [Tool libraries](tool-libraries.md) |
| **Setup** | Which bodies, the stock around them, and the work zero | [Setups](setups.md) |
| **Operation** | One toolpath: facing, pocket, adaptive clearing, contour or drilling | [Operations](operations.md) |
| **Post** | The G-code file for your controller, after checks | [Check and post](post.md) |

InvictusCAD currently makes **2D milling** toolpaths (2.5-axis: flat floors, vertical walls,
holes) for three-axis mills and routers. Posts are included for **Tormach PathPilot**,
**LinuxCNC** and **GRBL**.

## Your first program

This walks through facing and profiling a simple plate. You need a body to machine; if you don't
have one, follow [Your first part](../getting-started/first-part.md) first.

1. **Switch to CAM.** In the top bar, click **CAM** (next to **DESIGN**). The toolbar changes to
   **SETUP**, **MILL 2D**, **ACTIONS** and **MANAGE**.
2. **Import your tools** (once). Click **MANAGE › Tool Library**, then **Import...**, and choose a
   tool library exported from Fusion (`.json`), or click **New...** and add tools by hand. See
   [Tool libraries](tool-libraries.md).
3. **Add a setup.** Click **SETUP › New Setup**. Pick your **Machine**, check that **Bodies** lists
   your part, leave **Stock** on **Box** with a little extra on the **Sides** and **Top**, and pick
   the work zero **Point** (for example the top front left corner of the stock). Click **OK**.
4. **Face the top.** Click **MILL 2D › Facing**. Choose a **Tool** (a face mill or large end
   mill). The toolpath appears as you go. Click **OK**.
5. **Cut the outline.** Click **MILL 2D › Contour**. Choose a tool, click the **Outline** field and
   then the part's bottom face (or its top face) in the view. Leave **Side** on **Outside**. Add
   **Tabs** if the part is held from below. Click **OK**.
6. **Look at the result.** With **ACTIONS › Show Stock** on, the stock shows what's left after the
   operations. Select an operation in the browser to see the stock before it, with what it removes
   in teal.
7. **Post.** Click **ACTIONS › Post**. Read the issues list, turn on **Show Backplot** to see the
   program drawn back from the G-code, then click **Save...**.

!!! warning "Always prove a program out"
    InvictusCAD checks feeds, spindle speeds, rapids through the stock and travel limits, but it
    doesn't simulate the tool holder or check for collisions with your vise or fixtures. Air-cut
    new programs and keep a hand near the feed hold.

## Working with CAM

- **The browser** has a **Setups** folder. Each setup holds its operations. Double-click a setup or
  operation to change it; right-click a setup for **Post...**. An item turns red when it can't be
  calculated; hover it to see why.
- **Toolpaths** draw in the CAM workspace only: feeds solid blue, rapids dashed yellow. The selected
  operation is drawn bold. Hide one with its eye in the browser.
- **Model changes flow through.** Edit the part in DESIGN and its operations recalculate.
- **Switch back** with **DESIGN** in the top bar. Opening a sketch also returns you to DESIGN.
