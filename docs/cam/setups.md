# Setups

A **setup** is one way the part is held on the machine: which machine, which bodies, the stock
around them, and where the program's zero (the work offset) is. Every operation belongs to a
setup. A part machined from two sides needs two setups.

## Add a setup

1. In CAM, select the bodies to machine in the browser (or select nothing to use every visible
   body).
2. Click **SETUP › New Setup**. A violet preview of the stock appears and follows your changes.
3. Fill in the card (below) and click **OK**.

To change a setup later, double-click it in the browser.

## The setup card

### Machine

| Field | |
|---|---|
| **Machine** | Which [machine](machines.md) runs this setup |
| **Post** | **The machine's**, or another post for this setup only |
| **Starting range** | The spindle range (belt) the machine is in when the program starts. **0** means unknown: the program stops and says which to use |

### Model

**Bodies** — the bodies being machined. Click the field, then bodies in the view or browser.

### Stock

| Stock | Fields | Shape |
|---|---|---|
| **Box** | **Sides**, **Top**, **Bottom** | A box around the bodies, with this much extra on each side, on top and below |
| **Round** | **Sides**, **Top**, **Bottom** | A round bar about Z, big enough for the bodies plus **Sides** |
| **Fixed size** | **Width (X)**, **Depth (Y)**, **Height (Z)**, **Top** | Your stock's actual size, centred on the part, with its top **Top** above the part |

### Work zero

| Field | |
|---|---|
| **Z from** | Optional. A flat face or plane whose normal becomes +Z, for example the bottom face to machine the part flipped. Empty: the model's Z |
| **Flip Z** | Turns Z over |
| **On** | Put the zero on the **Stock** or on the **Model** |
| **Point** | Click the field, then one of the points shown on the box: a corner, edge middle or center, at the top, middle or bottom |
| **Work offset** | **G54** to **G59** |

The zero is drawn in the view as short axes: X red, Y green, Z blue.

!!! tip "Touch off where you zero"
    Pick the point you'll actually touch off on the machine, such as the top front left corner of
    the stock, so the program and the machine agree.

## Machining both sides

Make a second setup for the second side. Set **Z from** to the face that will be down (or tick
**Flip Z**), and pick the zero point you'll use after flipping the part.
