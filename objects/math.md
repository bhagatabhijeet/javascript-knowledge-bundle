---
id: objects/math
title: Math
type: objects
description: Use the built-in Math object for constants and functions like rounding, random numbers, and min/max.
status: draft
tags:
  - javascript
  - objects
  - fundamentals
  - math
---

# Math

`Math` is a built-in global object that groups mathematical constants and functions. Unlike `Object` or `Array`, it is not a constructor — you never write `new Math()`; you call its members directly.

```js
Math.PI;          // 3.141592653589793
Math.round(2.5);  // 3
Math.floor(2.9);  // 2
Math.ceil(2.1);   // 3
Math.max(1, 2, 3); // 3
Math.min(1, 2, 3); // 1
```

## Generating a random number

`Math.random()` returns a floating-point number between `0` (inclusive) and `1` (exclusive). Combine it with `Math.floor` to generate a random integer in a range:

```js
function getRandomInteger(min, max) {
  return Math.floor(Math.random() * (max - min + 1)) + min;
}

getRandomInteger(1, 10); // an integer from 1 to 10
```

## Related concepts

- [Basics](./basics.md)
- [Functions are Objects](./functions-are-objects.md)
