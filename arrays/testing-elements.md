---
id: arrays/testing-elements
title: Testing the Elements of an Array
type: arrays
description: Ask a yes/no question about an array's contents with every() and some(), instead of manually looping to check.
status: draft
sources:
  - resource: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/every
    title: "Array.prototype.every() - MDN Web Docs"
  - resource: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/some
    title: "Array.prototype.some() - MDN Web Docs"
tags:
  - javascript
  - arrays
  - collections
  - fundamentals
---

# Testing the Elements of an Array

Sometimes you don't need to *find* an element — you just need a yes/no answer about the array as a whole: "does every element satisfy this?" or "does at least one?" `every()` and `some()` answer exactly those two questions, each taking the same kind of test function as [`find`](./finding-elements-references.md).

## `every()` — do **all** elements pass?

```js
const numbers = [1, 2, 3, 4, 5];

numbers.every(n => n > 0); // true — every number is positive
numbers.every(n => n > 2); // false — 1 and 2 aren't
```

`every` stops as soon as it finds one element that fails the test — it doesn't check the rest once the answer is already `false`.

## `some()` — does **at least one** element pass?

```js
numbers.some(n => n > 4); // true — 5 satisfies it
numbers.some(n => n > 9); // false — none do
```

Just like `every`, `some` stops early — as soon as one element passes, it doesn't bother checking the rest.

## The empty array cases

These two behave in a way that surprises people at first, but follows from how "for all" and "there exists" work logically:

```js
[].every(n => n > 0); // true — vacuously true, there's nothing to disprove it
[].some(n => n > 0);  // false — there's nothing that satisfies it either
```

## Neither one mutates, and neither returns the elements

`every` and `some` both return a plain `true`/`false` — never a new array or the matching element itself. If you need the actual matching elements, reach for [`filter`](./filtering-an-array.md) or [`find`](./finding-elements-references.md) instead.

## Related concepts

- [Finding Elements (References)](./finding-elements-references.md)
- [Filtering an Array](./filtering-an-array.md)
- [Arrow Functions](../functions/arrow-functions.md)
