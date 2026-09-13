---
id: arrays/filtering-an-array
title: Filtering an Array
type: arrays
description: Build a new array containing only the elements that pass a test, using filter().
status: draft
sources:
  - resource: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter
    title: "Array.prototype.filter() - MDN Web Docs"
tags:
  - javascript
  - arrays
  - collections
  - fundamentals
---

# Filtering an Array

`filter()` builds a **new array** containing only the elements for which a test function returns a truthy value — the elements that don't pass are left out entirely.

```js
const numbers = [1, 2, 3, 4, 5, 6];

const evens = numbers.filter(n => n % 2 === 0);

evens;   // [2, 4, 6]
numbers; // [1, 2, 3, 4, 5, 6] — the original array is untouched
```

## `filter()` vs. `find()`

Both take the same kind of test function, but they answer different questions:

- [`find`](./finding-elements-references.md) returns the **first** matching element (or `undefined`) — use it when you expect at most one match.
- `filter` returns **every** matching element, as an array — use it when there could be several, including zero.

```js
const users = [
  { id: 1, name: 'Alice', active: true },
  { id: 2, name: 'Bob', active: false },
  { id: 3, name: 'Charlie', active: true }
];

users.find(user => user.active);   // { id: 1, name: 'Alice', active: true } — just the first
users.filter(user => user.active); // [{ id: 1, ... }, { id: 3, ... }] — all of them
```

## No matches means an empty array, not `undefined`

If nothing passes the test, `filter` still returns an array — just an empty one:

```js
numbers.filter(n => n > 100); // []
```

That makes its result safe to keep using with array methods like `.length`, `.map`, or another `.filter`, without needing to check for `undefined` first the way you would after `find`.

## Related concepts

- [Finding Elements (References)](./finding-elements-references.md)
- [Testing the Elements of an Array](./testing-elements.md)
- [Iterating Elements](./iterating-elements.md)
