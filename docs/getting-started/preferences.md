# Preferences

**☰ Menu › Edit › Preferences...** (++ctrl+comma++) keeps what you like between sessions.

| Preference | What it does |
|---|---|
| **Theme** | **Dark** (the default) or **Light**: the whole app, the 3D view too. It takes effect the next time Cahaba Studio starts |
| **Units** | The units a new document starts in. Each document keeps its own; change one with the **mm ▾** button |
| **Physical material** | What bodies in a new document are made of until you give them a material: their mass, their look and, for sheet metal, their K-factor and relief size. It's saved with the document |
| **Hide a sketch once a feature uses it** | On (the default), making an Extrude, Revolve, Sweep, Loft, Flange or another feature from a sketch turns the sketch's eye off in the browser. One undo brings both back; click the eye to show it again |
| **Sizes to start on** | Which hole and thread sizes the Hole card starts on: **Metric**, **Inch**, or **The document's units**. The card's **Standard** switch changes it for one hole |
| **Thickness**, **Bend radius** | The sheet a new sheet metal Flange starts at. Bend radius 0 uses the material's typical radius for the thickness |
| **SpaceMouse** | **Speed**, and **Reverse panning**, **zooming** or **turning** for a 3Dconnexion SpaceMouse |

Preferences apply to documents you start afterwards. An empty, untouched document also takes them
straight away.

## Drawings

What goes in the title block of every [drawing](../drawings/index.md#the-sheet), for whoever makes
them:

| Preference | Where it goes |
|---|---|
| **Company** | Over the drawing's title |
| **Copyright** | In bold at the foot of the title block: `Copyright 2026 Invictus Machine LLC` |
| **Notice** | Under the copyright, a line each: a license, say. Blank lines are left out |
| **Logo** | At the left of the title block's top row, fitted to it. **Choose...** a PNG, JPG or SVG; **Remove** takes it off |

Leave any of them empty and the title block goes without it; with no copyright or notice, it is
shorter. A picture wider than 1200 pixels is made smaller when it's chosen; an SVG is drawn as its
shapes, sharp at any size. They apply to every drawing at once, open ones too, and to drawings
exported by an assistant.

## Keyboard shortcuts

**Keyboard Shortcuts…** in Preferences lists every command with its key. Use the search box to
find one.

- Click a shortcut and press the keys you want for it. ++backspace++ clears it.
- **Reset All** puts every shortcut back to what Cahaba Studio starts with.
- A key can belong to only one command: if you give a command a key another one has, the list
  names both so you can clear one.

Changes are saved when you click **OK** and take effect at once. Tooltips show the new keys. The
keys for switching workspaces (++ctrl+1++, ++ctrl+2++, ++ctrl+3++) and for the Projects panel
aren't in the list.
