# Units and Expressions

Each document has a **unit**: millimeters, centimeters, meters, inches or feet. It sets how values
are shown and what a plain number means. Change it with the unit button in the top bar
(**mm ▾**). Changing the unit never changes the geometry, only how it's shown, and you can change it
back with Undo.

New documents start in millimeters.

## Typing lengths

Anywhere a length goes, you can type a number, a number with a unit, or a calculation:

| You type | Means |
|---|---|
| `25` | 25 in the document's unit |
| `6mm`, `2.5 cm`, `1 m` | metric lengths |
| `0.25in`, `1/4"`, `1/4 in` | a quarter inch |
| `3 1/2` | three and a half (in the document's unit) |
| `2'` or `2 ft` | two feet |
| `2' + 6"` | two feet six inches |
| `1/4" + 2mm` | units can be mixed |
| `(40 - 2 * 3) / 2` | arithmetic: `+ - * /` and parentheses |
| `panel_width / 2 - margin` | [named parameters](../modeling/parameters.md) |

A number next to a length takes that length's unit: `10 + 2.5mm` is 12.5 mm.

!!! note
    Write feet and inches with a plus sign: `2' + 6"`. `2'6"` isn't understood yet.

If a value can't be used, the field turns red; hover it to see why (for example
*"Multiplying two lengths gives an area, not a length."*).

## Angles and counts

Angle fields are in degrees; type a plain number (`45`, or `45°`). Counts, such as a pattern's
number of copies, are whole numbers.

## Values remember what you typed

In sketch dimensions and feature values (extrude distances, fillet radii, plane offsets and the
like), the value keeps the expression you typed. `1/4"` reads back as `1/4"` when you edit it, even
in a millimeter document, and values that use parameters update when the parameter changes.
