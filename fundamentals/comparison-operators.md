---
id: fundamentals/comparison-operators
title: Comparison operators
type: operators
description: Compare values with relational operators and understand how JavaScript coerces operands during comparison.
status: draft
tags:
  - javascript
  - fundamentals
  - operators
  - comparison
generated: { by: claude/sonnet-5, at: 2026-08-30T00:00:00Z }
sources:
  - resource: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#relational_operators
---

# Comparison operators

`<`, `>`, `<=`, and `>=` compare two values and return a boolean.

```js
5 > 2    // true
5 < 2    // false
5 >= 5   // true
5 <= 4   // false
```

## String comparison

Strings compare lexicographically (character by character, by code point).

```js
'apple' < 'banana'  // true
'Zebra' < 'apple'   // true, uppercase letters sort before lowercase
```

## Mixed-type comparison

Relational operators coerce operands toward numbers when they aren't both strings. See [Dynamic typing and type coercion](./dynamic-typing.md) for the full coercion model.

```js
'10' > 9    // true, '10' is coerced to 10
'10' > '9'  // false, compared as strings: '1' < '9'
```

## `NaN` is never ordered

Any comparison involving `NaN` returns `false`, including `NaN < NaN` and `NaN > NaN`.

```js
NaN < 1   // false
NaN > 1   // false
```

## Related concepts

- [Equality operators](./equality-operators.md)
- [Dynamic typing and type coercion](./dynamic-typing.md)
- [Operator precedence](./operator-precedence.md)

This draft was generated from general knowledge of MDN's JavaScript operator reference and has not been checked against a live source. It should receive human review before its status is promoted or a `verified` entry is added.
