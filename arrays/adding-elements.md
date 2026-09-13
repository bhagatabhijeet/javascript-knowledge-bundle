---
id: arrays/adding-elements
title: Adding Elements
type: arrays
description: Add elements to the end, beginning, or middle of an array using push, unshift, and splice.
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

# Adding Elements

JavaScript arrays have three built-in methods for inserting elements, depending on where they need to go. All three **mutate** the original array in place, rather than returning a new one.

## Adding to the end: `push()`

```js
const numbers = [1, 2, 3];
numbers.push(4, 5); // returns the new length: 5

numbers; // [1, 2, 3, 4, 5]
```

`push` can take any number of arguments and appends them all, in order. It's the fastest of the three — adding to the end doesn't require shifting any other elements.

## Adding to the beginning: `unshift()`

```js
const numbers = [3, 4, 5];
numbers.unshift(1, 2); // returns the new length: 5

numbers; // [1, 2, 3, 4, 5]
```

`unshift` works like `push`, but at the front. It's slower than `push` on large arrays, because every existing element has to shift over to make room.

## Adding in the middle: `splice()`

`splice(start, deleteCount, ...itemsToInsert)` can insert (and simultaneously remove) elements at any index. To insert without removing anything, pass `0` as the `deleteCount`:

```js
const numbers = [1, 2, 5];
numbers.splice(2, 0, 3, 4); // insert 3 and 4 at index 2, delete nothing

numbers; // [1, 2, 3, 4, 5]
```

`splice` returns an array of the elements it removed (empty here, since `deleteCount` was `0`) — see [Removing Elements](./removing-elements.md) for its removal side.

## Related concepts

- [Introduction to Arrays](./introduction-to-arrays.md)
- [Removing Elements](./removing-elements.md)
- [Finding Elements (Primitives)](./finding-elements-primitives.md)
