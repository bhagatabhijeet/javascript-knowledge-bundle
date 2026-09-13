---
id: arrays/emptying-an-array
title: Emptying an Array
type: arrays
description: Remove every element from an array with array.length = 0 or splice, and understand why reassigning to a new [] doesn't affect other references to the original array.
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

# Emptying an Array

There's more than one way to remove every element from an array, and they aren't quite interchangeable — the difference comes down to whether other code still holds a reference to the same array.

```js
let numbers = [1, 2, 3, 4];
```

## Setting `length` to `0`

The simplest and fastest way — [`length` is writable](./introduction-to-arrays.md), and truncating it to `0` removes every element:

```js
numbers.length = 0;
numbers; // []
```

This **mutates** the existing array in place, so anything else still holding a reference to it — a variable, a function parameter, a property on some object — sees it become empty too.

## `splice(0, length)`

Removes the same elements, and additionally hands them back if you need them:

```js
const numbers = [1, 2, 3, 4];
const removed = numbers.splice(0, numbers.length);

numbers;  // []
removed;  // [1, 2, 3, 4]
```

Like setting `length`, this mutates the original array in place.

## The `array = []` gotcha

Reassigning the variable to a brand-new empty array *looks* like it empties the array, but it doesn't — because [arrays are reference types](../objects/value-vs-reference-types.md), this only points the variable at a different array. It does nothing to the original:

```js
let numbers = [1, 2, 3, 4];
const alias = numbers; // `alias` points at the same array

numbers = []; // `numbers` now points at a new, empty array
alias; // [1, 2, 3, 4] — completely unaffected!
```

If nothing else references the original array, this works fine and is perfectly idiomatic. But if the array was passed into a function, stored on an object, or assigned to another variable first, those other references keep pointing at the original, now-stale array — which is rarely what you want.

## Which to use

- Prefer `array.length = 0` when you want every existing reference to see the array become empty.
- Use `array.splice(0, array.length)` if you also need the removed elements.
- Only use `array = []` when you're certain nothing else holds a reference to the original array.

## Related concepts

- [Value vs Reference Types](../objects/value-vs-reference-types.md)
- [Removing Elements](./removing-elements.md)
- [Introduction to Arrays](./introduction-to-arrays.md)
