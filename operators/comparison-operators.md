---
id: operators/comparison-operators
title: Comparison operators
type: operators
description: Compare values with relational operators and understand how JavaScript coerces operands during comparison.
status: draft
tags:
  - javascript
  - fundamentals
  - operators
  - comparison
---

# Comparison operators

Relational operators (`<`, `>`, `<=`, `>=`) compare two values and return a boolean (`true` or `false`).

```js
let x = 1;

// Relational
console.log(x > 0);  // true
console.log(x >= 1); // true
console.log(x < 1);  // false
console.log(x <= 1); // true
```

## String comparison

Strings are compared character-by-character according to their Unicode / ASCII character codes (lexicographically):

```js
'apple' < 'banana'; // true
'Zebra' < 'apple';  // true, uppercase letters sort before lowercase
```

## Mixed-type comparison

When comparing operands of different types, JavaScript coerces values toward numbers:

```js
'10' > 9;   // true, '10' is coerced to number 10
'10' > '9'; // false, compared as strings: '1' comes before '9'
```

## `NaN` is never ordered

Any comparison involving `NaN` evaluates to `false`:

```js
NaN < 1;   // false
NaN > 1;   // false
NaN <= NaN; // false
```

## Related concepts

- [JavaScript Operators](./javascript-operators.md)
- [Equality operators](./equality-operators.md)
- [Operator precedence](./operator-precedence.md)
- [Dynamic Types](../basics/dynamic-typing.md)
