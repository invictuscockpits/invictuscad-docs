# Machines

A machine tells Cahaba Studio what your mill can do: how far each axis travels, how fast it can
feed, its spindle speed ranges, which coolant it has, and which **post** writes its G-code. Every
setup uses one machine.

## Machines that come with Cahaba Studio

| Machine | Travel | Spindle | Post | Program in |
|---|---|---|---|---|
| Tormach PCNC 770 | X 14 in, Y 7.5 in, Z 13.25 in | Low belt 175–3250, high belt 525–10000 rpm (belts changed by hand) | PathPilot | inches |
| Tormach PCNC 770 + 4th axis | as above, plus an A axis | as above | PathPilot | inches |
| Generic 3-axis mill (LinuxCNC) | X 20, Y 12, Z 12 in | 100–10000 rpm | LinuxCNC | mm |
| Generic router (GRBL) | X 30, Y 30, Z 4 in | 5000–24000 rpm | GRBL | mm |

A Tormach 8L lathe is listed too, but turning isn't available yet.

## Make your own machine

Start from the machine closest to yours and change what differs.

1. In CAM, click **MANAGE › Machines**.
2. Select a machine in the list and click **New from This...**.
3. Type a name and click **OK**. Your copy is saved straight away and marked **(yours)** in the
   list.
4. Change the fields (below) and click **Save**.

You can also edit a shipped machine directly: saving keeps **your** version, and the shipped one
stays available under the same name if you delete yours.

### Fields

| Field | What it means |
|---|---|
| **Name** | What the machine is called in setups |
| **Post** | The controller dialect: PathPilot, LinuxCNC or GRBL |
| **Program in** | **Inches (G20)** or **Millimeters (G21)**, the unit the G-code is written in |
| **Tool changer** | Number of pockets; **0** means tools are changed by hand |
| **Spindle** | Tick **The program stops to change the range** if changing belts or gears is manual. The program then stops with a message when the range must change |
| **Coolant** | Which of **Flood**, **Mist** and **Air** the machine has. Asking for coolant it doesn't have gives a warning when posting |
| **Axes** | For each axis: **Min**, **Max**, **Max feed** and **Rapid**. Lengths are in your document's unit, rotary axes in degrees |
| **Spindle ranges** | Each range's **Name**, **Min rpm** and **Max rpm**. **Add Range** / **Remove Range**. At least one is needed |

!!! note
    You can't add or remove axes in the dialog. For a fourth axis, start from **Tormach PCNC 770 + 4th
    axis**.

Setups keep their own copy of the machine. After editing a machine, pick it again in a setup to use
the new values.

## Posts

| Post | Files | Notes |
|---|---|---|
| **PathPilot** (Tormach mills) | `.nc` | Tool changes via G53 Z0, `T# M6 G43 H#`. Belt changes stop with a message and M0. Drilling, pecking, boring and tapping cycles (G81, G82, G83, G73, G84, G85, G89) |
| **LinuxCNC mill** | `.nc` | Like PathPilot without the `%` lines; no G84, so tapping is refused |
| **GRBL** | `.gcode` | No canned cycles: drilling is written out as moves. Tool changes stop with a message and M0. Air coolant uses M8 |

All posts write arcs as G2/G3 with I/J and use M8 (flood), M7 (mist) and M9 (off).
