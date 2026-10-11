# Editing Your Model

## Features remember their inputs

Every feature keeps what you gave it: its sketch, its values, the edges and faces it uses.
Change any of them and the model rebuilds from that point on.

- **Change a sketch:** double-click it in the browser, edit it, finish it.
- **Change a feature:** double-click it in the [History panel](#the-history-panel), change its
  values, click **Update** (or **OK**).

Later features keep working because faces and edges are named after the features that made them.
A fillet stays on "the edge between Extrude1's end and its side" even when Extrude1 gets longer.

## The History panel

The **History** panel down the right of the view, under the view cube, lists every step of the
design in the order it's built: sketches, reference planes, features and patterns of bodies or
components (one step each, however many copies). Collapsed, it shows
each step's icon (hover for its name); click the button at its bottom to expand it and see the
names too. Your choice is remembered.

- **Edit a step:** double-click it.
- **Rename a step:** right-click it and choose **Rename**, or select it and press ++f2++. Type the
  name and press ++enter++ (++esc++ keeps the old one).
- **Pick a step into a card:** while a card waits for features (a pattern's, say), click them in
  the History panel.
- **Roll back:** drag the orange marker up the list. Steps below it dim and are left out of the
  model, as if not made yet, and anything you make now goes in at the marker. Drag it back down
  (or right-click a step and choose **Build Everything**) to build the rest again. Right-click a
  step and choose **Build Up to Here** to put the marker just below it.
- **Suppress:** right-click a feature and choose **Suppress** to leave it out without deleting
  it. Suppressed steps are struck through; choose **Unsuppress** to bring one back.
- **Reorder:** drag a step to another place. A step can't go above something it uses (an
  extrude above its sketch, for example); Cahaba Studio says why and leaves it where it was.
- **Delete:** right-click a step and choose **Delete**.

The marker's place and suppressed steps are saved with the project.

### How was this made?

Click a face, edge or vertex in the view. The History panel lights up the steps that made it in
orange (the sketch and the feature that created it) and the steps that changed it afterwards in
blue (a fillet that rounded its edge, a cut through it). Double-click one to edit it.

## When something no longer builds

If a change makes a later feature impossible, such as a fillet too big for a shortened edge, that
feature turns **red** in the History panel. Hover it to see why. Fix it by editing the feature, or
undo the change.

## Undo and redo

++ctrl+z++ undoes one step; ++ctrl+y++ redoes it. Hover the undo button to see what it would undo.
Each tool's result is one step, including everything an [AI assistant](../automation/mcp.md) does in
one go.

## Delete

Select what to delete in the browser (or click a body in the view) and press ++delete++, choose
**MODIFY › Delete**, or right-click it in the browser and choose **Delete**. Features and patterns
are deleted from the History panel: right-click the step and choose **Delete**. You can delete bodies,
features, sketches, planes, components, instances, connections and section analyses.

- A body takes its features with it.
- A feature leaves its body, which rebuilds without it. Deleting the feature that made a body
  deletes the body too.
- A component takes its instances with it, and an instance its connections.
- A pattern of bodies or components takes its copies with it.
- If other things use what you're deleting, such as a sketch on a body's face, Cahaba Studio names
  them and asks. **Delete All** deletes them too; **Cancel** keeps everything.

Deleting several things at once is one step to undo.

## Box

**CREATE › Box** adds a 100 × 50 × 25 mm box: a quick body to try things on.
