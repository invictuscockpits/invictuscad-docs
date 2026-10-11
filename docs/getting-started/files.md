# Files, Autosave and Backups

## Projects

Cahaba Studio projects are `.cb3` files. Everything for a design is in one file: sketches, features,
parameters, components, CAM setups.

Projects made when Cahaba Studio was called InvictusCAD are `.ivc` files. They open as before;
**Save As** offers the new extension.

| To | Do |
|---|---|
| Start a new project | **☰ › File › New** (++ctrl+n++) |
| Open one | **☰ › File › Open** (++ctrl+o++), double-click the file in Windows, or drop it on the view |
| Save | ++ctrl+s++ |
| Save under a new name | ++ctrl+shift+s++ |

If the open project has unsaved changes, you're asked whether to **Save**, **Discard** or
**Cancel** first.

When a project opens, Cahaba Studio rebuilds it from its history. If something no longer builds,
for example a linked part has changed, it tells you, and the feature shows red in the [History panel](../modeling/history.md#the-history-panel).

A `.cb3` file is a zip of readable JSON (your design intent: sketches, constraints, feature
values) plus the shapes. Your work is never locked inside the program.

## Autosave and crash recovery

About a minute after you change something, Cahaba Studio saves a recovery copy in the background.
Saving the project clears it.

If Cahaba Studio closes unexpectedly, the next time it starts it asks **Restore your work?**:

- **Restore** opens the autosaved copy. It's marked as unsaved: save it to keep it.
- **Discard** deletes the copy.
- **Decide Later** asks again next time.

## Backups

Every time you save over a project, the previous version is kept. The last 10 versions of each
project are kept, named with the date and time they were saved.

To get one back, choose **☰ › File › Show Backups Folder**, find the project's folder, and open
the version you want.

## Where Cahaba Studio keeps its files

Everything other than your projects lives in `%LOCALAPPDATA%\CahabaStudio`: backups, autosaves,
footprints, tool libraries, your machines, and your license.
