# Drive InvictusCAD from Claude (MCP)

InvictusCAD includes a [Model Context Protocol](https://modelcontextprotocol.io) server, so an AI
assistant such as Claude Desktop, Claude Code or Cursor can model for you: sketch and constrain,
extrude, add holes and fillets, measure, export flat parts, set up CAM and post programs.

The assistant works **in your open window**: you watch each change happen, it shows in the
Command Log, and **Undo** takes back the assistant's steps like your own. Each request it makes is
one undo step.

## Set it up

The assistant runs `invictuscad-mcp.exe`, which is installed next to `invictuscad.exe`. The paths
below assume the default install folder, `C:\Program Files\InvictusCAD`.

**Claude Code:**

```bash
claude mcp add invictuscad -- "C:\Program Files\InvictusCAD\invictuscad-mcp.exe" --launch-app
```

**Claude Desktop:** go to **Settings › Developer › Edit Config**, add this to
`claude_desktop_config.json`, and restart Claude Desktop:

```json
{
  "mcpServers": {
    "invictuscad": {
      "command": "C:\\Program Files\\InvictusCAD\\invictuscad-mcp.exe",
      "args": ["--launch-app"]
    }
  }
}
```

**Cursor:** add the same `mcpServers` entry to `%USERPROFILE%\.cursor\mcp.json`.

## Modes

| Argument | |
|---|---|
| (none) | Works in the open InvictusCAD window. If it isn't open, the assistant is told to open it; the next request finds it, with nothing to restart |
| `--launch-app` | The same, but starts InvictusCAD when it isn't open |
| `--headless` | Never touches the app: the server keeps its own document, for scripts and batch jobs |

Set the environment variable `INVICTUSCAD_MCP=0` to stop InvictusCAD listening for assistants.

## Try it

> Make a 4 × 2 inch plate, 1/4 inch thick, with a 10 mm hole 15 mm in from each corner, fully
> constrained.

> Round the vertical edges 1/8 inch, then export it flat as DXF to my desktop.

> Set up the plate on the Tormach 770 with the zero at the top front left corner of the stock, face
> it with tool 1, contour the outside with tool 4 and four tabs, and post it.

## What the assistant can do

Every command in InvictusCAD is available to it, plus:

| | Tools |
|---|---|
| Look at the model | `get_document`, `get_sketch`, `get_body`, `measure`, `screenshot`, `set_view` |
| Files | `new_document`, `open_project`, `save_project` |
| History | `undo`, `redo` |
| 2D output | `export_sketch`, `export_flat`, `nest_parts` (with a quantity per part) |
| Footprints | `list_footprints`, `save_footprint`, `delete_footprint` |
| Patterns | `pattern_rectangular`, `pattern_circular`, `pattern_path` (features), `pattern_bodies`, `pattern_instances` |
| CAM | `add_setup`, `add_operation`, `post_setup`, `get_operation`, `list_tools`, `import_tool_library`, `list_machines` |
| Scan to CAD | `import_scan`, `repair_scan`, `scan_regions`, `extract_scan`, `align_scan`, `move_scan`, `section_scan`, `outline_scan`, `scan_to_body`, `add_deviation`, `edit_deviation`, `export_scan` |

Lengths are millimeters unless given with units (`"0.5in"`, `"1/4\""`, `"10 + 2mm"`). When a
request can't be done, such as a conflicting constraint or an open profile, the assistant gets the
reason and the model is left unchanged.

The assistant won't throw away your unsaved work: opening or starting a project with unsaved
changes is refused until you save or discard them.
