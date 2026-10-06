# Check and Post

**Posting** writes the setup's operations as a G-code program for your controller, after checking
it.

## See the result first

- **Toolpaths:** feeds are solid blue, rapids dashed yellow. Select an operation in the browser to
  draw it bold.
- **ACTIONS › Show Stock** (on by default) shows the stock after every visible operation, so you
  can see what's left. Select an operation to see the stock **before** it, with what that operation
  removes in teal. Turn it off to see the plain stock.

## Post a program

1. Click **ACTIONS › Post** (posts the selected setup), or right-click a setup in the browser and
   choose **Post...**.
2. The Post window shows:
    - a summary: the number of lines, and whether there are errors or warnings;
    - the **issues** list: errors in red, warnings in amber, each naming its operation;
    - the program itself.
3. Tick **Show Backplot** to draw the program in the view as the machine will read it: the G-code
   is read back, so this shows what was actually written.
4. Click **Save...**. The file is named after the setup (or its program name) with the post's
   extension, in your project's folder.

Fix errors before running a program. InvictusCAD still lets you save one with errors, for checking.

## What's checked

| Check | |
|---|---|
| Failed operations | Listed as errors and left out of the program |
| Spindle speed | Missing, or outside the machine's spindle ranges |
| Feeds | A cutting move with no feed, or faster than the machine's slowest axis |
| Coolant | The machine doesn't have it, or the post can't switch it (warning) |
| Rapids | A rapid move through the stock (the first per operation, with its position) |
| Travel | The program's extent compared with the machine's travel |
| Tapping | Refused on posts without a tapping cycle (LinuxCNC) |
| Speed and feed notes | Any value an operation had to adjust (warning) |

Manual spindle-range changes are written into the program as a message and an M0 stop.

!!! warning
    These checks don't cover holders, fixtures or tool stick-out. Prove out every new program.
