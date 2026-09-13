---
id: arrays/removing-elements
title: Removing Elements
type: arrays
description: Remove elements from the end, beginning, or middle of an array using pop, shift, and splice.
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

# Removing Elements

Just like [adding elements](./adding-elements.md), removing them depends on where they are — and all three methods below **mutate** the original array.

## Removing from the end: `pop()`

```js
const numbers = [1, 2, 3];
numbers.pop(); // returns 3, the removed element

numbers; // [1, 2]
```

## Removing from the beginning: `shift()`

```js
const numbers = [1, 2, 3];
numbers.shift(); // returns 1, the removed element

numbers; // [2, 3]
```

Like `unshift`, `shift` is slower than `pop` on large arrays, since every remaining element has to shift down by one index.

## Removing from the middle: `splice()`

`splice(start, deleteCount)` removes `deleteCount` elements starting at index `start`, and returns them as an array:

```js
const numbers = [1, 2, 3, 4, 5];
numbers.splice(1, 2); // removes 2 elements starting at index 1, returns [2, 3]

numbers; // [1, 4, 5]
```

Combine `splice` with [`findIndex`](./finding-elements-references.md) to remove an element you found rather than one at a known position:

```js
const users = [{ id: 1 }, { id: 2 }, { id: 3 }];
const index = users.findIndex(user => user.id === 2);

if (index !== -1) {
  users.splice(index, 1);
}

users; // [{ id: 1 }, { id: 3 }]
```

## Related concepts

- [Adding Elements](./adding-elements.md)
- [Finding Elements (References)](./finding-elements-references.md)
- [Iterating Elements](./iterating-elements.md)
