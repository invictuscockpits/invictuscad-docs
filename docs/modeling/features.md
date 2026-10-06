# Features

Features turn sketches into solid bodies and then refine them. Each one keeps its inputs, so you
can edit it later and everything after it rebuilds.

| Feature | What it does |
|---|---|
| Extrude | Pushes a profile along a direction |
| Revolve | Spins a profile around a line: full, partial or symmetric |
| Sweep | Moves a profile along a chain of curves, following the path or keeping its orientation |
| Loft | Blends between sketches, faces or end points, smooth or ruled |
| Fillet | Rounds edges |
| Chamfer | Bevels edges (equal distance) |
| Shell | Hollows a body to a wall thickness, leaving chosen faces open |
| Hole | Drilled, counterbored or countersunk holes; see [Holes and threads](holes-and-threads.md) |

Most features can create a **new body**, or **join**, **cut** or **intersect** with an existing one.

## Editing history

Change any feature's values, or the sketch it uses, and the model recomputes from that point. Edges
and faces used by later features are tracked by name, so a fillet stays on its edge when an earlier
dimension changes.

## Measure

**Inspect > Measure** gives areas, lengths, radii and volumes, or between two items: the minimum
distance, the X/Y/Z offsets, the angle, and center or axis spacing.
