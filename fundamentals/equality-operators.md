---
id: fundamentals/equality-operators
title: Equality operators
type: operators
description: Compare values for equality with == and ===, and understand why strict equality is preferred.
status: draft
tags:
  - javascript
  - fundamentals
  - operators
  - equality
generated: { by: claude/sonnet-5, at: 2026-08-30T00:00:00Z }
sources:
  - resource: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Equality_comparisons_and_sameness
  - resource: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#equality_operators
---

# Equality operators

`===` (strict equality) compares value and type with no coercion. `==` (loose equality) coerces operands first. See [Dynamic typing and type coercion](./dynamic-typing.md) for the coercion rules `==` relies on.

```js
5 === 5     // true
5 === '5'   // false, different types
5 == '5'    // true, '5' is coerced to 5
```

## Prefer `===`

Loose equality's coercion rules produce results that are easy to get wrong.

```js
0 == false        // true
0 == ''           // true
null == undefined // true
null == 0         // false, this one is NOT coerced
```

`!==` and `!=` are the strict and loose inequality counterparts.

## `NaN` and `Object.is`

`NaN` is never equal to itself under `==` or `===`. Use `Number.isNaN()` to test for it, or `Object.is()` for the rare cases needing true sameness semantics (including distinguishing `+0` from `-0`).

```js
NaN === NaN        // false
Number.isNaN(NaN)  // true
Object.is(NaN, NaN) // true
Object.is(0, -0)    // false
```

## Related concepts

- [Comparison operators](./comparison-operators.md)
- [Dynamic typing and type coercion](./dynamic-typing.md)
- [Primitive data types](./primitive-types.md)

This draft was generated from general knowledge of MDN's JavaScript operator reference and has not been checked against a live source. It should receive human review before its status is promoted or a `verified` entry is added.
