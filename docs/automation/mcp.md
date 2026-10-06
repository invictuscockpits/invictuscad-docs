# Drive InvictusCAD from Claude (MCP)

InvictusCAD includes a [Model Context Protocol](https://modelcontextprotocol.io) server, so an AI
assistant such as Claude Desktop, Claude Code or Cursor can model for you: create sketches, draw and
constrain geometry, extrude, measure and save.

The assistant launches `invictuscad-mcp.exe`, installed next to `invictuscad.exe`, which works in
one of two modes:

- **Live.** If InvictusCAD is open, the assistant works in your window and you see each change.
  Every tool call is one step in Edit > Undo, and each appears in the Command Log. It can also take
  screenshots of the 3D view and change the view.
- **Headless.** If InvictusCAD isn't open, the server keeps its own document and opens or saves
  `.ivc` files.

The mode is chosen when the assistant starts the server. If you open InvictusCAD afterwards, restart
the MCP server in the assistant, or use `--launch-app` (below).

## Set up your assistant

The paths below assume the default install folder, `C:\Program Files\InvictusCAD`.

**Claude Code:**

```bash
claude mcp add invictuscad -- "C:\Program Files\InvictusCAD\invictuscad-mcp.exe"
```

**Claude Desktop:** go to Settings > Developer > Edit Config, add this to
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

### Options

| Argument | Effect |
|---|---|
| (none) | Live if the app is open, otherwise headless |
| `--launch-app` | Starts InvictusCAD if it isn't open, then works live |
| `--headless` | Never touches the app |

| Environment variable | Effect |
|---|---|
| `INVICTUSCAD_MCP=0` | Stops the app from listening for assistants |

## What it can do

Every command in InvictusCAD is available as a tool, plus tools to read the model (`get_document`,
`get_sketch`, `get_body`), `measure`, the footprint library, `rename_object`, `undo` and `redo`,
and opening and saving projects.

Lengths are millimeters unless given with units (`"0.5in"`, `"1/4\""`, `"10 + 2mm"`). If a request
doesn't work, such as a conflicting constraint or a profile that isn't closed, the assistant gets
an error and your model is left unchanged.

## Try it

> Make a 4 x 2 inch plate, 1/4 inch thick, with a 10 mm hole 15 mm in from each corner, fully
> constrained.
