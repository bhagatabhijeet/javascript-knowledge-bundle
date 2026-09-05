---
id: basics/arrays
title: Arrays
type: js-basics
description: Store and manage ordered lists of items in JavaScript using arrays, index access, and length.
status: draft
tags:
  - javascript
  - basics
  - fundamentals
  - arrays
  - collections
---

# Arrays

When you need to store a collection or list of items (such as a list of colors, products, or users), use an **array**.

An array is an ordered data structure where each element has a numerical index starting at `0`.

## Creating an array

Use square brackets `[]` (array literal syntax) to initialize an array:

```js
let selectedColors = ['red', 'blue'];
console.log(selectedColors);
```

An empty array is declared as `let items = [];`.

## Accessing elements

Elements are accessed via zero-based indexing using bracket notation:

```js
console.log(selectedColors[0]); // 'red'
console.log(selectedColors[1]); // 'blue'
```

Accessing an index that does not exist returns `undefined`:

```js
console.log(selectedColors[2]); // undefined
```

## Dynamic length and mixed types

In JavaScript:
1. **Dynamic length**: Arrays can expand or shrink dynamically. You do not need to specify an array size beforehand:
   ```js
   selectedColors[2] = 'green';
   console.log(selectedColors); // ['red', 'blue', 'green']
   ```
2. **Mixed types**: The items in an array do not all have to share the same type. You can mix numbers, strings, booleans, or objects:
   ```js
   selectedColors[3] = 1;
   console.log(selectedColors); // ['red', 'blue', 'green', 1]
   ```

## The `length` property

Every array has a built-in `length` property returning the count of elements currently in the array:

```js
console.log(selectedColors.length); // 4
```

## Arrays are objects

In JavaScript, arrays are reference types and inherit from `Object`:

```js
console.log(typeof selectedColors); // "object"
```

To determine whether a value is specifically an array, use `Array.isArray()`:

```js
console.log(Array.isArray(selectedColors)); // true
```

## Related concepts

- [Variables](./variables.md)
- [Constants](./constants.md)
- [Primitive Types](./primitive-types.md)
- [Objects](./objects.md)
- [Functions](./functions.md)
