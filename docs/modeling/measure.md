# Measure

1. Choose **INSPECT › Measure** (++m++).
2. Click a face, edge or vertex. The card shows what applies:
    - a face's **Area** and **Perimeter**;
    - a circle's **Diameter**, **Radius** and **Circumference**, or an arc's **Radius** and **Arc
      length**;
    - an edge's **Length**;
    - a vertex's **Position**, or a round item's **Center**.
3. Click a second item to measure between them. A dashed line joins the closest points, with the
   distance written beside it, and the card adds:
    - **Distance** (the shortest);
    - **ΔX**, **ΔY**, **ΔZ**;
    - **Angle**, where one is defined;
    - **Center distance** between round items, such as hole spacing.
4. Click a third time to start over. ++esc++ clears the picks; press it again to close Measure.

![Measuring between two items](../assets/images/measure.png)

## Whole bodies

Switch the card's first list from **Faces, edges, vertices** to **Bodies**, then click a body. The
card shows its **Volume**, **Area** and **Center of mass**, which is also marked in the view. Give
the body a [physical material](materials-and-appearances.md) to see its **Mass** too. Click a
second body to get the shortest distance between the two.

## Precision

The second list sets how many decimal places the results show. **Auto** uses the document unit's
usual precision and drops trailing zeros. The choice is remembered.

You can select the values in the card and copy them. The **SELECT** buttons in the top bar limit
what clicks pick, which helps when faces and edges are close together.

For a quick look, just select one item: its size shows at the bottom of the view. Select a body in
the browser to see its volume.

To see inside a part, use [Section Analysis](section-analysis.md).
