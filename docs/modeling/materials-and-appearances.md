# Materials and Appearances

A body's **physical material** is what it's made of: it gives the body a mass and a look. An
**appearance** is only how a face looks: paint, anodizing, a finish. An appearance painted over a
material changes the look, not the mass.

## Give a body a material

1. Choose **MODIFY › Physical Material**. The **Physical Material** card opens.
2. Pick a material from the list (type in **Search** to narrow it: *6061*, *stainless*, *walnut*).
3. Click the bodies to make of it. Each click is one step you can undo.
4. Press ++esc++ or click **Done**.

Set **Paint** to **Component** to give a whole component the material at once: every body in it
takes it (bodies that had their own lose it).

Or right-click a body or component in the browser and choose **Physical Material...**: the card
opens aimed at it, and the material you pick goes on it straight away.

The library has aluminum, steels, stainless, brass, bronze, copper, titanium and magnesium,
common plastics (ABS, acetal, acrylic, polycarbonate, nylon, HDPE, UHMW, PEEK, PLA, PETG...),
composites, woods and more. Each has its density and typical strengths (hover a material to see
them); the values are typical, not design allowables.

## Paint appearances

1. Choose **MODIFY › Appearance**. The **Appearance** card opens.
2. Pick an appearance: metals, anodized colors, paints, plastics, clear materials, woods. Or click
   **Custom Color...**, choose a color, and pick its finish (**Matte**, **Satin**, **Glossy**,
   **Polished**, **Rubber** or **Glass**) first.
3. Choose what a click paints:

    | Paint | |
    |---|---|
    | **Face** | The face you click |
    | **Body** | Every face of the body you click (its painted faces go back to the body's look) |
    | **Component** | Every body of the component you click |

4. Click as many faces, bodies or components as you like. The one under the cursor lights up
   before you click. Each click is one step you can undo.
5. Press ++esc++ or click **Done**.

Pick **None** to take appearances off what you click: the material's look shows again.

Right-click a body or component in the browser and choose **Appearance...** to paint all of it
with the pick.

!!! tip
    A painted face keeps its appearance when you change the model: it follows the face through
    edits, and the pieces it splits into keep it too.

## What wins

A face shows the first of: its own appearance, its body's, its component's, its material's look.
With none of those, it's the default gray.

## Mass and properties

Right-click a body in the browser and choose **Properties...** to see:

| | |
|---|---|
| **Material** and **Density** | Its own, or its component's |
| **Volume**, **Surface area** | |
| **Mass** | In kilograms and pounds (needs a material) |
| **Center of mass** | |
| **Size** | Its bounding box |
| **Appearance** | What it shows |

Materials and appearances are saved with the project. Over MCP, `set_material`,
`set_appearance` and `list_materials` do the same, and `get_body` reports the mass.
