# Holes and Threads

## Add holes

1. Choose **CREATE › Hole** (++h++).
2. Click a flat face where the hole goes (the card starts on **Place**). Near the cursor the hole
   snaps to:
    - a **Corner** of the part;
    - the **Center** of a round edge or arc (a boss, another hole), or of a circle in a sketch;
    - an edge's **Midpoint**;
    - anywhere **On edge**;
    - a point in a sketch.

    A green ring shows where it will go and a label says what it snapped to. Away from all of
    these, it goes where you click.

    Each click adds another hole. All the holes in one Hole feature go on the same face, or faces in
    the same plane.
3. To move a hole, choose **Move** (once there's a hole) and drag its dot. The hole follows as you
   drag and snaps the same way; clicks in **Move** don't add holes. Choose **Place** to add more.
4. Set the card:

    | Field | |
    |---|---|
    | **Type** | **Simple**, **Counterbore** or **Countersink** |
    | **Standard** | **Metric** or **Inch** sizes, in any document. It starts on the document's units, or on the one chosen in [Preferences](../getting-started/preferences.md) |
    | **Size** | A standard size (ISO metric M1–M64 and fine pitches, or UNC #1–2" and UNF #0–1-1/2") or **Custom diameter** |
    | **Fit** | For standard sizes: **Tapped** (tap drill size), **Close**, **Normal** or **Loose** clearance |
    | **Diameter** | For a custom size |
    | **Extent** | **Through**, or **Blind** with a **Depth** (drag the arrow, or type) |
    | **Thread** | For tapped holes: **Cosmetic** (drawn, not modeled) or **Modeled**. A modeled thread has the standard's profile (60° flanks with flats at the crests and roots), and the hole is drilled to the thread's minor diameter rather than the tap drill. In a blind hole it stops half a turn short of the bottom |

5. Click **OK**.

![A hole](../assets/images/hole.png)

The holes are placed by a sketch on that face, which is created for you and hidden afterwards.
To position them exactly, double-click that sketch in the browser and dimension its points, like
any other sketch.

!!! tip "Holes at sketch points"
    Already have a sketch on the face with points (or circles) where the holes go? Select it in
    the browser, then choose **Hole**: a hole goes at each point.

Counterbore and countersink sizes come from the standard for the screw size, so choose a standard
**Size** for those.

## Threads

Add a thread to a bolt, boss or hole.

1. Choose **CREATE › Thread**.
2. Click a cylindrical face: the outside of a shaft for an external thread, the inside of a hole
   for an internal one.
3. Set the card:

    | Field | |
    |---|---|
    | **Size** | **Auto (from the face)** picks the size matching the diameter, or choose one |
    | **Length** | The first option threads the full length; the second lets you type a **Length** |
    | **Thread** | **Cosmetic** or **Modeled** |

4. Click **OK**.

## Change holes and threads

Double-click the Hole or Thread in the [History panel](history.md#the-history-panel), change its settings and click **Update**.
