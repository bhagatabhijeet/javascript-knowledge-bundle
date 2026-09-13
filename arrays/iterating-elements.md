---
id: arrays/iterating-elements
title: Iterating Elements
type: arrays
description: Loop over an array's elements with for...of and forEach, and transform them with map, filter, and reduce.
status: draft
sources:
  - resource: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array
    title: "Array - MDN Web Docs"
tags:
  - javascript
  - arrays
  - collections
  - fundamentals
---

# Iterating Elements

## `for...of`

The most general way to visit every element in order:

```js
const numbers = [1, 2, 3];

for (const number of numbers) {
  console.log(number);
}
```

`for...of` supports `break` and `continue`, which makes it a good default when you might need to stop early.

## `forEach()`

`forEach` calls a function once per element, passing the element, its index, and the array itself:

```js
numbers.forEach((number, index) => console.log(index, number));
```

Unlike `for...of`, `forEach` cannot be stopped early with `break` — if you need to exit partway through, use `for...of` or a plain loop instead.

## Transforming while iterating: `map`, `filter`, `reduce`

These don't just visit elements — they build something new from them, without mutating the original array:

```js
const numbers = [1, 2, 3, 4];

numbers.map(n => n * 2);          // [2, 4, 6, 8] — a new array, same length
numbers.filter(n => n % 2 === 0); // [2, 4] — a new array, matching elements only
numbers.reduce((sum, n) => sum + n, 0); // 10 — a single accumulated value
```

Reach for `map`/`filter`/`reduce` when the goal is to produce a new array or value from the original; reach for `for...of`/`forEach` when the goal is a side effect, like logging or updating something outside the array.

## Related concepts

- [Removing Elements](./removing-elements.md)
- [Introduction to Arrays](./introduction-to-arrays.md)
- [For...of loop](../control-flow/for-of.md)
