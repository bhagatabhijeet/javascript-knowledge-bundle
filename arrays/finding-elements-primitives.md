---
id: arrays/finding-elements-primitives
title: Finding Elements (Primitives)
type: arrays
description: Search an array of primitive values with indexOf, lastIndexOf, and includes.
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

# Finding Elements (Primitives)

When an array holds primitive values (numbers, strings, booleans), you can search it directly by **value**, using `===` comparison under the hood.

## `indexOf()` and `lastIndexOf()`

```js
const numbers = [1, 2, 3, 2];

numbers.indexOf(2);     // 1 — index of the first match
numbers.lastIndexOf(2); // 3 — index of the last match
numbers.indexOf(9);     // -1 — not found
```

Because `-1` is a valid array index in some other languages but not in JavaScript, checking `=== -1` is the correct way to test "not found":

```js
if (numbers.indexOf(9) === -1) {
  console.log('not in the array');
}
```

## `includes()`

When you only care *whether* a value is present — not where — `includes()` reads more clearly:

```js
numbers.includes(2); // true
numbers.includes(9); // false
```

`includes()` also correctly finds `NaN`, which `indexOf` cannot (`indexOf` uses `===`, and `NaN === NaN` is `false`):

```js
const values = [1, NaN, 3];

values.indexOf(NaN);  // -1 — never finds NaN
values.includes(NaN); // true
```

## Why these don't work for objects

All three methods compare with `===`, which for objects checks *reference* identity, not the contents. Searching an array of objects for one with matching data needs a different approach — see [Finding Elements (References)](./finding-elements-references.md).

```js
const users = [{ id: 1 }, { id: 2 }];

users.includes({ id: 1 }); // false — different object, even with the same shape
```

## Related concepts

- [Finding Elements (References)](./finding-elements-references.md)
- [Introduction to Arrays](./introduction-to-arrays.md)
- [Value vs Reference Types](../objects/value-vs-reference-types.md)
