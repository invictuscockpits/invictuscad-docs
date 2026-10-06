# Named Parameters

Give a value a name, such as `wall = 3mm` or `bolt = 1/4"`, and use the name anywhere a length or
value goes: sketch dimensions, extrude distances, feature values.

- Expressions can combine parameters: `wall * 2 + 1mm`.
- Change the parameter and everything that uses it updates.
- Values keep the expression you typed, so they read back as `wall * 2`, not as a number.

The **Parameters** table lists every parameter with its expression and current value. A driven
(reference) dimension shows `fx:` when its value comes from an expression.
