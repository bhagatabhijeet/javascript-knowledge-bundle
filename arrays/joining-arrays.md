---
id: arrays/joining-arrays
title: Joining Arrays
type: arrays
description: Turn an array into a single string with join(), controlling the separator between elements.
status: draft
sources:
  - resource: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join
    title: "Array.prototype.join() - MDN Web Docs"
tags:
  - javascript
  - arrays
  - collections
  - strings
  - fundamentals
---

# Joining Arrays

Don't confuse this with [combining arrays](./combining-and-slicing-arrays.md) — `join()` doesn't merge two arrays together. It turns **one** array into a single **string**, placing a separator between each element.

```js
const numbers = [1, 2, 3];

numbers.join(); // '1,2,3' — comma is the default separator
```

## Choosing a separator

Pass any string as the separator:

```js
numbers.join('-'); // '1-2-3'
numbers.join(' '); // '1 2 3'
numbers.join('');  // '123' — no separator at all
```

## `null` and `undefined` become empty strings

Unlike most conversions to string, `join()` treats `null` and `undefined` elements as empty strings rather than the literal text `"null"` or `"undefined"`:

```js
[1, undefined, null, 3].join(); // '1,,,3'
```

## Everything else is converted to a string

Numbers, booleans, and other values are converted the same way string concatenation would convert them. Nested arrays are flattened one level, always joined with commas internally regardless of the outer separator:

```js
const matrix = [[1, 2], [3, 4]];

matrix.join(';'); // '1,2;3,4' — the outer separator is `;`, the inner arrays always use `,`
```

## `join()` doesn't mutate

Like [`slice`](./combining-and-slicing-arrays.md), `join()` reads the array without changing it — it just returns a new string.

## Related concepts

- [Combining and Slicing Arrays](./combining-and-slicing-arrays.md)
- [Template Literal](../objects/template-literals.md)
- [Iterating Elements](./iterating-elements.md)
