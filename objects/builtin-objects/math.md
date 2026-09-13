---
id: objects/builtin-objects/math
title: Math
type: objects
description: Use the built-in Math object for constants and functions like rounding, random numbers, and min/max.
status: draft
sources:
  - resource: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math
    title: "Math - MDN Web Docs"
tags:
  - javascript
  - objects
  - fundamentals
  - math
  - builtin-objects
---

# Math

`Math` is a built-in **namespace object** that groups mathematical constants and functions. Unlike `Object` or `Array`, it is not a constructor — you never write `new Math()`, and you never call `Math()` as a function either. Every property and method is **static**, meaning you access it directly on `Math` itself:

```js
Math.PI;           // 3.141592653589793
Math.round(2.5);   // 3
Math.floor(2.9);   // 2
Math.ceil(2.1);    // 3
Math.max(1, 2, 3); // 3
Math.min(1, 2, 3); // 1
```

`Math` only works with the `Number` type, not `BigInt` — passing a `BigInt` to a `Math` method throws a `TypeError`.

## Constants

| Property | Approximate value | What it is |
| --- | --- | --- |
| `Math.PI` | 3.14159 | Ratio of a circle's circumference to its diameter |
| `Math.E` | 2.71828 | Euler's number, the base of natural logarithms |
| `Math.SQRT2` | 1.41421 | The square root of 2 |
| `Math.LN2` | 0.69315 | The natural logarithm of 2 |
| `Math.LN10` | 2.30259 | The natural logarithm of 10 |

## Rounding

```js
Math.floor(4.7); // 4 — rounds down to the nearest integer
Math.ceil(4.2);  // 5 — rounds up to the nearest integer
Math.round(4.5); // 5 — rounds to the nearest integer
Math.trunc(4.9); // 4 — removes the fractional part entirely (no rounding)
```

## Min, max, and power

```js
Math.max(1, 5, 3); // 5
Math.min(1, 5, 3); // 1
Math.pow(2, 3);    // 8 — 2 to the power of 3

// Modern equivalent of Math.pow, using the exponentiation operator:
2 ** 3; // 8
```

## Roots, logarithms, and absolute value

```js
Math.sqrt(16);  // 4 — positive square root
Math.cbrt(27);  // 3 — cube root
Math.abs(-5);   // 5 — absolute value
Math.sign(-5);  // -1 — is the number negative, zero, or positive?
```

## Generating a random number

`Math.random()` returns a pseudo-random floating-point number between `0` (inclusive) and `1` (exclusive). Combine it with `Math.floor` to generate a random integer in a range:

```js
function getRandomInteger(min, max) {
  return Math.floor(Math.random() * (max - min + 1)) + min;
}

getRandomInteger(1, 10); // an integer from 1 to 10
```

## Trigonometric functions

`Math` also provides the standard trigonometric functions (`Math.sin`, `Math.cos`, `Math.tan`, and their inverses `Math.asin`, `Math.acos`, `Math.atan`) — all of them work in **radians**, not degrees.

## Related concepts

- [Basics](../basics.md)
- [Functions are Objects](../functions-are-objects.md)
- [String](./string.md)
