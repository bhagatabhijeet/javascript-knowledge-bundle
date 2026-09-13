---
id: arrays/finding-elements-references
title: Finding Elements (References)
type: arrays
description: Search an array of objects by testing their contents with find and findIndex, since reference types can't be matched by value.
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

# Finding Elements (References)

## Why `includes()` doesn't work for objects

[`indexOf` and `includes`](./finding-elements-primitives.md) compare with `===`. For primitives that means comparing the actual value, but for objects `===` checks **reference identity** — whether it's literally the same object in memory, not whether its properties look the same:

```js
const users = [
  { id: 1, name: 'Alice' },
  { id: 2, name: 'Bob' }
];

users.includes({ id: 1, name: 'Alice' }); // false!
```

Even though `{ id: 1, name: 'Alice' }` looks identical to the first element, it's a brand-new object literal — a different location in memory — so `===` says they don't match. `includes()` (and `indexOf`) has no way to compare properties for you; it only ever asks "is this the exact same object?" So searching an array of objects by their *contents* needs a **test function** instead of a value to compare against — which is what `find` and `findIndex` are for.

## `find()`

`find()` returns the **first element** for which the callback returns a truthy value, or `undefined` if none match:

```js
const users = [
  { id: 1, name: 'Alice' },
  { id: 2, name: 'Bob' }
];

users.find(user => user.id === 2); // { id: 2, name: 'Bob' }
users.find(user => user.id === 9); // undefined
```

## `findIndex()`

Same idea, but returns the matching element's **index** (or `-1` if nothing matches) instead of the element itself — useful when you need the position, e.g. to pass to [`splice`](./adding-elements.md):

```js
users.findIndex(user => user.name === 'Alice'); // 0
users.findIndex(user => user.name === 'Zoe');   // -1
```

## Searching from the end: `findLast()` and `findLastIndex()`

These work the same way as `find`/`findIndex`, but search from the end of the array backward instead of the start:

```js
const logs = [
  { level: 'info', message: 'started' },
  { level: 'error', message: 'failed once' },
  { level: 'info', message: 'retried' },
  { level: 'error', message: 'failed again' }
];

logs.findLast(log => log.level === 'error');
// { level: 'error', message: 'failed again' } — the most recent error
```

## Related concepts

- [Finding Elements (Primitives)](./finding-elements-primitives.md)
- [Value vs Reference Types](../objects/value-vs-reference-types.md)
- [Adding Elements](./adding-elements.md)
