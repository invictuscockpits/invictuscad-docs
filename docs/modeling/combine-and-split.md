# Combine and Split Bodies

## Combine

**MODIFY › Combine** joins bodies together, cuts one with others, or keeps only where they overlap.

1. Choose **MODIFY › Combine**.
2. Pick the **Body** that changes.
3. Pick the **Tools**: the other bodies. Click them in the view or in the browser.
4. Choose the **Operation**: **Join**, **Cut** or **Intersect**.
5. For a cut, you can leave room around the tools, so a part modeled at its exact size fits
   the pocket it makes:
    - **Radial clearance**: room around the tools' sides (a pin's hole this much bigger all round).
    - **Axial clearance**: room at the tools' ends, along their axis (how much deeper a blind
      pocket goes than the pin).
    - **Axis**: which way "axial" is. Leave it empty to use the tool's own axis (a cylinder's),
      or Z when it has none; or pick an edge, axis or plane.
6. Turn on **Keep tools** to leave the tool bodies in the design. Otherwise the combine uses them
   up: they leave the browser and the view, but their steps stay in the
   [History panel](history.md#the-history-panel), where you can still edit them and the combine
   follows. Delete, suppress or roll back the combine and they come back.
7. Click **OK**.

The combine follows its tools: move or change a tool body and the result updates.

## Split

**MODIFY › Split Body** cuts a body into pieces along a plane or a face.

1. Choose **MODIFY › Split Body**.
2. Pick the **Body** to split.
3. Pick the **Tool**: an origin plane, a [reference plane](reference-planes.md), or a face of
   another body. A curved face works too.
4. Leave **Extend** on to grow the tool across its whole surface, so it cuts right through like a
   plane. Turn it off to cut only where the face itself reaches, or set **Extend by** to grow it
   just that far past its edges.
5. Click **OK**.

The largest piece stays in the body you split. Every other piece becomes a body of its own, which
follows the split if the body or the tool changes.
