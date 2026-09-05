---
id: control-flow/switch-case
title: Switch...case
type: control-flow
description: Compare an expression against multiple matching case clauses using strict equality.
status: draft
tags:
  - javascript
  - control-flow
  - conditionals
  - switch
---

# Switch...case

The `switch...case` statement evaluates an expression and matches the expression's value against multiple `case` clauses. When a match is found, the statements following that `case` clause are executed.

`switch` compares using **strict equality (`===`)**.

## Syntax

```js
switch (variable) {
  case value1:
    // statements
    break;
  case value2:
    // statements
    break;
  default:
    // fallback statements
}
```

## Example: User role authorization

```js
let role = 'guest';

switch (role) {
  case 'guest':
    console.log('Guest User');
    break;

  case 'moderator':
    console.log('Moderator User');
    break;

  case 'admin':
    console.log('Admin User');
    break;

  default:
    console.log('Unknown User');
}
```

## The `break` statement and fall-through

- The `break` statement stops execution of more code and case testing inside the block.
- If you omit `break`, execution **falls through** to the next `case` clause regardless of whether that case matches:

```js
let tier = 'silver';

switch (tier) {
  case 'silver':
  case 'gold':
    console.log('Premium customer discount applies');
    break;
  default:
    console.log('Standard pricing');
}
```

## When to use `switch` vs. `if...else`

- Use `if...else` for boolean checks, relational comparisons (`>`, `<`), or ranges of numbers.
- Use `switch...case` when checking a single variable against multiple discrete static values (strings or numbers).

## Related concepts

- [If...else](./if-else.md)
- [Equality operators](../operators/equality-operators.md)
- [Break and continue](./break-and-continue.md)
