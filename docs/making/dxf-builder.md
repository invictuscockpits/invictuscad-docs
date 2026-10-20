# DXF Builder

A **DXF Builder** puts several sketches into one DXF, each on a layer of its own named after the
sketch and in a color of its own. LightBurn, and software like it, opens the file with a layer
for each color, so the job is set up already: choose cut or fill for each layer and go.

It's handy when one design is made several ways. Keep each part of a panel in its own sketch:
the outline, the mounting holes, the switch holes, the LED cutouts, the PCB pocket and the
legend. Then make a builder for each way to make it, say one for each plate of an acrylic stack
and one for the engraving. The builders are saved with the project, so anyone who opens the file
can export the plate they need, or change a builder to suit their own.

## Make a builder

1. Choose **MAKE › DXF Builder** (on the Solid or Sheet Metal tab). Sketches selected in the
   browser are already picked.
2. Give it a **Name**, for example "Face plate": it's what the browser shows and what the DXF is
   called.
3. Click the sketches in the view or the browser, in the order you want the layers. Click one
   again to take it out. Sketches whose eye is off can be picked in the browser.
4. Each sketch gets a color, in this order: red, blue, green, magenta, cyan, orange, yellow,
   gray, then purple, teal, pink and sky blue. Change one under **Layer colors** if you like; it
   stays with its sketch if you change the order.
5. Click **Export...** and choose where to save.

The builder is listed under **DXF Builders** in the browser. You can rename it there too (++f2++).

## Export again

Right-click the builder › **Export DXF...**, or double-click it to change its sketches or colors
and export.

## What's in the file

- Each sketch's curves on its layer, outlines only, in the layer's color. Each curve also
  carries the color, for software that goes by that rather than the layer.
- Construction curves, reference layers and hidden layers are left out.
- Text is exported as its outlines. Filled shapes (lettering you've filled) go as closed
  outlines, holes included, so LightBurn can fill them.
- The sketches are laid out as the first one sees them. They should be on the same or parallel
  planes, as a panel's are.
- Sizes are in the document's unit, and the file is DXF R12, which nearly everything reads.
