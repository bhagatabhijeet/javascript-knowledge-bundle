---
id: operators/equality-operators
title: Equality operators
type: operators
description: Compare values for equality with == and ===, and understand why strict equality is preferred.
status: draft
tags:
  - javascript
  - fundamentals
  - operators
  - equality
---

# Equality operators

JavaScript has two sets of equality operators:
- **Strict equality (`===` and `!==`)**: Checks that both the type and value are identical.
- **Loose equality (`==` and `!=`)**: Coerces values to matching types before comparing.

```js
// Strict equality (ensures same type and same value)
console.log(1 === 1);   // true
console.log('1' === 1); // false

// Loose equality (coerces operands)
console.log(1 == 1);    // true
console.log('1' == 1);  // true (string '1' coerced to number 1)
console.log(true == 1); // true (boolean true coerced to number 1)
```

## Why strict equality is preferred

Loose equality's implicit coercion rules often cause unexpected behavior:

```js
0 == false;        // true
0 == '';           // true
null == undefined; // true
null == 0;         // false
```

Always prefer **strict equality (`===`)** and **strict inequality (`!==`)** to write clean, predictable, and bug-free code.

## `NaN` and `Object.is`

`NaN` ("Not a Number") is the only value in JavaScript that is not equal to itself under either `==` or `===`:

```js
NaN === NaN;        // false
Number.isNaN(NaN);  // true
Object.is(NaN, NaN);// true
```

## Related concepts

- [JavaScript Operators](./javascript-operators.md)
- [Comparison operators](./comparison-operators.md)
- [Dynamic Types](../basics/dynamic-typing.md)
- [Primitive Types](../basics/primitive-types.md)
