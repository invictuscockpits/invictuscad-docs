# Tool Libraries

A tool library holds your cutters and, for each one, **cutting presets**: the speeds and feeds to
use in a material. Operations pick a tool and a preset from a library.

Open it with **MANAGE › Tool Library** in the CAM workspace.

## Import a library from Fusion

If you already keep your tools in Fusion, bring them across rather than typing them in.

1. In Fusion, export the library as **JSON**.
2. In InvictusCAD, click **Import...** and choose the file.
3. InvictusCAD copies it into your libraries and reports how many tools came in, plus anything it
   had to guess at (an unknown tool type, a repeated tool number).

What comes across: tool types, diameters, corner radii, flutes and lengths (metric tools in an inch
library stay correct), tool numbers and offsets, holders, and every preset's surface speed or rpm,
chip load or feed, plunge and other feeds, step-over, step-down and coolant.

## Make a library by hand

1. Click **New...** and name the library.
2. Click **Add Tool**. A new end mill appears with the next free tool number.
3. Fill in the row: **T#**, **Description**, **Type**, **Diameter**, **Corner** radius, **Flutes**
   and **Flute length**.
4. With the tool selected, edit its presets underneath (see below).
5. Click **Save**.

**Copy** duplicates the selected tool with the next free number; **Delete** removes it.

## Cutting presets

Each tool can have several presets, for example one for aluminum and one for steel. The presets
table shows the selected tool's:

| Column | Meaning |
|---|---|
| **Name**, **Material** | How you'll recognise it when choosing it in an operation |
| **RPM** | Spindle speed. Leave 0 to work it out from the surface speed |
| **Surface** | Surface speed (ft/min or m/min, following your document's unit) |
| **Chip load** | Per tooth. Used to work out the feed when **Feed** is 0 |
| **Feed**, **Plunge** | Per minute |
| **Stepover**, **Stepdown** | Defaults for operations that use this preset |
| **Coolant** | Off, Flood, Mist, Air or Through tool |

**Add Preset** copies the last preset; **Delete Preset** removes the selected one.

## How speeds and feeds are worked out

When an operation runs, InvictusCAD takes:

- **Spindle speed:** the preset's rpm, or surface speed ÷ (π × diameter). It's held inside the
  machine's spindle range, and the first range that fits is chosen.
- **Feed:** the preset's feed, or chip load × flutes × rpm.
- **Plunge:** the preset's plunge feed, or a third of the feed.
- No feed exceeds the machine's slowest axis. When anything is adjusted, the operation says so.

Any of these can be overridden in an individual operation.
