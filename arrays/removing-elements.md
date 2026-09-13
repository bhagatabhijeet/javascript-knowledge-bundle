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

Just like [adding elements](./adding-elements.md), removing them depends on where they are — from the end, the beginning, or the middle — and all three methods below **mutate** the original array.

```js
const numbers = [1, 2, 3, 4];
```

## Removing from the end: `pop()`

Instead of `push`, use `pop` — it removes the **last** element and returns it:

```js
const last = numbers.pop();

numbers; // [1, 2, 3]
last;    // 4
```

## Removing from the beginning: `shift()`

Similarly, instead of `unshift`, use `shift` — it removes the **first** element and returns it:

```js
const first = numbers.shift();

numbers; // [2, 3] — continuing from the array left after pop()
first;   // 1
```

`shift` is slower than `pop` on large arrays, since every remaining element has to move down by one index.

## Removing from the middle: `splice()`

To remove an element somewhere in the middle, pass `splice` the **index** of that element and, as the second argument, **how many** elements to delete from there:

```js
const numbers = [1, 2, 3, 4]; // starting fresh again

numbers.splice(2, 1); // remove 1 element starting at index 2
numbers; // [1, 2, 4] — the 3 is gone
```

Passing a `deleteCount` greater than `1` removes multiple elements starting at that index:

```js
const numbers = [1, 2, 3, 4];

numbers.splice(2, 2); // remove 2 elements starting at index 2
numbers; // [1, 2] — both 3 and 4 are gone
```

To recap: `pop` for the last element, `shift` for the first, and `splice` for one (or more) somewhere in the middle.

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
