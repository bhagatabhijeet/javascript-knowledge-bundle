---
id: arrays/mapping-an-array
title: Mapping an Array
type: arrays
description: Transform every element of an array into a new one with map(), producing a new array of the same length.
status: draft
sources:
  - resource: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map
    title: "Array.prototype.map() - MDN Web Docs"
tags:
  - javascript
  - arrays
  - collections
  - fundamentals
---

# Mapping an Array

`map()` builds a **new array** by running every element through a function and collecting the results — one output element for every input element, always the same length as the original.

```js
const numbers = [1, 4, 9];

const roots = numbers.map(n => Math.sqrt(n));

roots;   // [1, 2, 3]
numbers; // [1, 4, 9] — unchanged
```

## `map()` vs. `forEach()`

They look similar — both call a function once per element — but they answer different needs:

- `forEach` returns `undefined`. Use it for a **side effect**: logging, pushing into some other array, updating something outside the loop.
- `map` **returns a new array** built from the callback's return values. Use it whenever the goal is a transformed version of the array itself.

```js
const prices = [10, 20, 30];

// map: I want a new array of the transformed values
const withTax = prices.map(price => price * 1.1);

// forEach: I just want to do something with each value, not collect results
prices.forEach(price => console.log(`$${price}`));
```

Calling `map` and then throwing away its result (using it like `forEach`) is a common code smell — if you're not using the returned array, reach for [`forEach` or `for...of`](./iterating-elements.md) instead.

## `map()` on an array of objects

`map` is especially useful for reshaping a list of objects into a list of specific values:

```js
const users = [
  { id: 1, name: 'Alice' },
  { id: 2, name: 'Bob' }
];

const names = users.map(user => user.name);

names; // ['Alice', 'Bob']
```

## Related concepts

- [Iterating Elements](./iterating-elements.md)
- [Filtering an Array](./filtering-an-array.md)
- [Reducing an Array](./reducing-an-array.md)
