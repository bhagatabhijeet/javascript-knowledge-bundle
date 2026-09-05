---
id: control-flow/for-of
title: For...of
type: control-flow
description: Iterate directly over the values of iterable collections such as arrays, strings, maps, and sets.
status: draft
tags:
  - javascript
  - control-flow
  - loops
  - arrays
  - for-of
---

# For...of

Introduced in ECMAScript 2015 (ES6), the `for...of` statement creates a loop iterating over **iterable objects** (including `Array`, `String`, `Map`, `Set`, and arguments).

Unlike `for...in` which iterates over property *keys*, `for...of` iterates over property *values*.

## Syntax

```js
for (let element of iterable) {
  // statement using element directly
}
```

## Example: Iterating over an array

```js
const colors = ['red', 'green', 'blue'];

for (let color of colors) {
  console.log(color);
}
// Output:
// red
// green
// blue
```

## Example: Iterating over a string

```js
const word = 'JavaScript';

for (let char of word) {
  console.log(char);
}
```

## Comparison: `for...in` vs `for...of`

- **`for...in`**: Used primarily to inspect keys/properties of an **Object**:
  ```js
  for (let key in person) { ... }
  ```
- **`for...of`**: Used to iterate over items/values of an **Array** or other iterables:
  ```js
  for (let item of array) { ... }
  ```

## Related concepts

- [For...in](./for-in.md)
- [For loop](./for.md)
- [Arrays](../basics/arrays.md)
