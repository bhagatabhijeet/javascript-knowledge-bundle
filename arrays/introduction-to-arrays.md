---
id: arrays/introduction-to-arrays
title: Introduction to Arrays
type: arrays
description: Create arrays with literals or the Array constructor, understand indexing, length, and sparse arrays, and check for arrays with Array.isArray.
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

# Introduction to Arrays

An array is an ordered, zero-indexed list that can hold items of any type — building on [the basics](../basics/arrays.md), this concept looks at how arrays are actually constructed under the hood and a few behaviors worth knowing before using them seriously.

## Array literal vs. the `Array` constructor

Prefer the array literal syntax:

```js
const numbers = [1, 2, 3];
```

`new Array(...)` does the same thing with two or more arguments, but has a surprising gotcha with exactly one **numeric** argument:

```js
new Array(1, 2, 3); // [1, 2, 3] — fine, behaves as expected

new Array(3); // [ <3 empty items> ] — a sparse array with length 3, NOT [3]!
[3];          // [3] — the literal always means "one element, the number 3"
```

Because of this gotcha, always prefer array literals (`[]`) — reach for `new Array()` only when you specifically want to preallocate a sparse array of a given length.

## Sparse arrays

An array can have "holes" — indices that were never assigned:

```js
const sparse = [];
sparse[5] = 'value';

sparse.length; // 6 — indices 0-4 are empty slots, not `undefined`
```

Older iteration methods like `forEach` and `map` skip empty slots entirely, while newer ones like `find` treat them as `undefined`. In practice, avoid creating sparse arrays — build arrays by pushing values in, rather than assigning to arbitrary indices.

## Length is writable

The `length` property isn't just informational — assigning to it truncates or extends the array:

```js
const letters = ['a', 'b', 'c'];
letters.length = 2;
letters; // ['a', 'b'] — truncated

letters.length = 4;
letters; // ['a', 'b', <2 empty items>] — extended with empty slots
```

## Checking whether a value is an array

Because arrays are objects (`typeof [] === 'object'`), `typeof` can't tell an array apart from a plain object. Use `Array.isArray()` instead:

```js
Array.isArray([1, 2, 3]); // true
Array.isArray('hello');   // false
Array.isArray({});        // false
```

## Related concepts

- [Arrays (basics)](../basics/arrays.md)
- [Adding Elements](./adding-elements.md)
- [Value vs Reference Types](../objects/value-vs-reference-types.md)
