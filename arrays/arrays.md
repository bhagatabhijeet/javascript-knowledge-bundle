---
id: arrays/arrays
title: Arrays
type: arrays
description: Create, access, and transform ordered collections with JavaScript arrays and built-in methods.
status: draft
tags:
  - javascript
  - arrays
  - collections
  - fundamentals
---

# Arrays

An array is an ordered list of items. In JavaScript, arrays are dynamic, zero-indexed, and can hold items of any type.

```js
const numbers = [3, 4];
console.log(numbers);
```

## Adding elements

- **End**: `numbers.push(5, 6)`
- **Beginning**: `numbers.unshift(1, 2)`
- **Middle**: `numbers.splice(2, 0, 'a', 'b')`

## Finding elements

- **Primitives**: `numbers.indexOf(3)`, `numbers.includes(4)`
- **Reference types**: `users.find(u => u.id === 1)`, `users.findIndex(u => u.id === 1)`

## Removing elements

- **End**: `numbers.pop()`
- **Beginning**: `numbers.shift()`
- **Middle**: `numbers.splice(index, count)`

## Iterating elements

```js
const numbers = [1, 2, 3];

// for...of loop
for (let number of numbers) {
  console.log(number);
}

// forEach method
numbers.forEach((number, index) => console.log(index, number));
```

## Related concepts

- [Objects](../objects/objects.md)
- [For...of loop](../control-flow/for-of.md)
- [Functions](../functions/functions.md)
