# Units and Expressions

InvictusCAD stores geometry in millimeters, and each document has a **display unit** (millimeters
or inches) that sets how values are shown and what a plain number means.

## Typing lengths

Anywhere a length goes, you can type a number, a number with units, or an expression:

| You type | Means |
|---|---|
| `25` | 25 in the document's display unit |
| `1/4"` or `0.25in` | a quarter inch |
| `6mm` | 6 millimeters |
| `1/4" + 2mm` | units can be mixed |
| `wall * 2` | twice the [named parameter](../modeling/parameters.md) `wall` |

Angles are in degrees.

## Values remember what you typed

If you type `1/4"`, the value keeps that expression, so it reads back as `1/4"` when you edit it,
even in a millimeter document. Values that use named parameters update when the parameter changes.
