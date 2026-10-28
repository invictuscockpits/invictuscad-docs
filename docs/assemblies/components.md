# Components and Instances

A **component** holds the bodies and sketches of one part. Each place the part is used is a
**copy** of it (an instance): change the component and every copy changes. Use components for
anything that appears more than once, or to keep an assembly's parts separate.

## Start a new component

Choose **ASSEMBLE › New Component**, or right-click empty space in the browser › **New
Component**. It's empty, placed at the origin, and you're editing it straight away: the sketches,
features and bodies you make next go into it. Click **Finish Component** when you're done.

To make one body its own component as you create it, choose **New component** as the operation on
the Extrude, Revolve, Sweep or Loft card.

## Make a component

1. Select the bodies that make up the part (in the browser or the view).
2. Choose **ASSEMBLE › Make Component**, or right-click a body in the browser › **Make
   Component**.

The bodies, their features, and any sketches and planes only they use move into the new
component. Its first copy stays where the bodies were. Rename the component in the browser
(++f2++) and its copies follow: **Base (2)**, **Base (3)**.

## In the browser

Each component is listed once, holding what it's made of: **Bodies**, **Sketches** and **Planes**
folders, and **Components** for other parts placed inside it. Its row stands for its first copy,
and sits where that copy is placed (inside the component it's placed in, for a subassembly).

Every other copy is a row of its own beside it, **Base (2)**, **Base (3)**, with nothing under it:
it's the same part. A copy placed inside another component is listed in that component's
**Components** folder.

## Hide and show

Each row's eye shows and hides what it says: a component's eye its first copy, a copy's eye that
copy. A body's eye inside a component hides that body in every copy. When a whole component is
hidden, every one of its eyes shows closed, and clicking any of them brings it back.

## Add more copies

Right-click the component (or one of its copies) in the browser › **Add Copy**. The copy appears
beside the others.

## Move a copy

1. Double-click the copy in the browser, or select it and choose **ASSEMBLE › Move Instance**.
2. Drag it in the view: the straight arrows move it along X (red), Y (green) or Z (blue), and the
   curved arrows turn it about those axes, through the middle of the part. Hold ++shift++ for
   finer steps. An arrow pointing straight at you is left out.
3. Or type the values: **Move X**, **Move Y**, **Move Z**, and **Turn X**, **Turn Y**, **Turn Z**
   (turned about X, then Y, then Z). Moves are relative to where it is now.
4. Click **Move**. The whole move is one undo step.

### Move several at once

Select several copies (Ctrl+click them in the browser or the view) and choose **ASSEMBLE ›
Move Instance**, or click more copies while the card is open. They move together as one, turning
about the middle of them all, so they keep their places to each other. If any of them is grounded,
none moves.

To place parts against each other exactly, use [connections](connections.md) instead.

## Ground an instance

Right-click a copy › **Ground** to fix it in place: connections never move it, and Move
Instance refuses to. Grounded copies show **⚓** (on the component's row, for its first copy).
**Release** undoes it.

## Edit a component in place

1. Double-click the component in the browser (or right-click › **Edit Component**). To edit it
   where a particular copy is, right-click that copy › **Edit Component Here**.
2. The component stays where that copy is in the assembly, with everything else around it as it
   was: nothing moves on screen. A banner shows you're editing it, and **Finish Component**
   appears in the top bar. New sketches, features and bodies now go into the component, and you
   can sketch on the faces of other parts and use them for reference.
3. Click **Finish Component** (or double-click the component again) to return.

Every copy updates as you work.

## Work on a part from the assembly

You don't have to edit a component to change it. From the top level, every tool works on a placed
copy: click a face or edge of any copy, moved, turned or inside a subassembly, and Fillet, Chamfer,
Shell, Hole, Extrude, Revolve, Combine, Split, Mirror, Pattern, Project and Measure reach that
part's body where the copy is.

- A sketch goes into the component you're editing, or the top level when you aren't, even when
  it's drawn on a copy's face.
- A cut or join made from that sketch belongs to the part's own body. It's made against the copy
  you clicked, and every copy shows it.
- A new body made from a top-level sketch stays at the top level. Choose **New component** to make
  it a part of its own.

![Editing a component in place](../assets/images/editing-component.png)

## Subassemblies

A component can hold instances of other components, such as an axle with its two wheels. Place the
subassembly as many times as you need, and each copy moves as one.

To make one from parts already placed:

1. Select the instances, and any loose bodies that belong with them (Ctrl+click or Shift+click in
   the view or the browser).
2. Choose **ASSEMBLE › Make Component**, or right-click one › **Make Component**.

They go into the new component exactly where they are, and its first instance is placed so that
nothing moves. Connections between them go in with them. A connection from one of them to a part
that isn't going in is refused: select that part too, or delete the connection first.

To build one from the inside, edit the component (above) and add instances of other components
while you're in it. A component can't hold itself, or a component that already holds it.

In the browser, a copy inside a subassembly is listed in that subassembly's **Components** folder.
Parts lists count every part inside, however deep.

## Linked parts

A component can live in its own `.cb3` file and be used by several projects: a standard bracket,
a motor, a common enclosure.

- **Link a component to a file:** right-click it › **Link to File...** and choose where to save
  it. The component is now read from that file (its name shows **↗**).
- **Use a part that's already a file:** drag it from the [Projects panel](../getting-started/projects.md)
  onto the view, or right-click it there › **Insert into This Project**.
- **Use the changes:** after the part's file changes, choose **ASSEMBLE › Update Links**. When
  you open a project whose linked files changed or went missing, Cahaba Studio tells you. The
  project still opens with the last shape it had.
- **Bring it back into the project:** right-click › **Embed**.

A linked component can't be edited in place: open its own file to change it.

A project remembers where each linked part is from its own folder, so a folder holding a project
and its parts can be moved, zipped or copied to another computer whole. Renaming or moving a
linked part in the Projects panel updates the projects that use it.
