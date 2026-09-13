---
id: arrays/reducing-an-array
title: Reducing an Array
type: arrays
description: Collapse an array down to a single value — a sum, an object, a count — with reduce() and an accumulator.
status: draft
sources:
  - resource: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce
    title: "Array.prototype.reduce() - MDN Web Docs"
tags:
  - javascript
  - arrays
  - collections
  - fundamentals
---

# Reducing an Array

Where [`map`](./mapping-an-array.md) produces one output per input and [`filter`](./filtering-an-array.md) produces a subset, `reduce()` collapses the whole array down into a **single value** — a sum, a count, an object, anything you build up as you go.

```js
const numbers = [1, 2, 3, 4];

const sum = numbers.reduce((accumulator, current) => accumulator + current, 0);

sum; // 10
```

## How the accumulator works

`reduce` calls the callback once per element, passing it the **accumulator** — the value carried over from the previous call — and the current element. Whatever the callback returns becomes the accumulator for the *next* call:

```
accumulator: 0, current: 1 -> returns 1
accumulator: 1, current: 2 -> returns 3
accumulator: 3, current: 3 -> returns 6
accumulator: 6, current: 4 -> returns 10
```

The second argument to `reduce` — `0` above — is the **initial value** of the accumulator, used for that very first call.

## Omitting the initial value

If you leave out the initial value, `reduce` uses the array's first element as the starting accumulator and begins calling the callback from the second element instead:

```js
numbers.reduce((accumulator, current) => accumulator + current);
// same result (10), but skips explicitly passing 0
```

This works, but it has a sharp edge: calling `reduce` **without an initial value on an empty array** throws a `TypeError`, since there's no first element to start from. Passing an explicit initial value avoids that case entirely and is usually the safer habit.

## Building something other than a number

The accumulator can be any value — an array, an object, a string. Here it counts how many times each name appears:

```js
const names = ['Alice', 'Bob', 'Alice'];

const counts = names.reduce((allNames, name) => {
  allNames[name] = (allNames[name] ?? 0) + 1;
  return allNames;
}, {});

counts; // { Alice: 2, Bob: 1 }
```

Notice the accumulator here starts as `{}`, not `0` — `reduce` doesn't care what shape you're building, as long as each call returns the next version of it.

## Related concepts

- [Mapping an Array](./mapping-an-array.md)
- [Filtering an Array](./filtering-an-array.md)
- [Iterating Elements](./iterating-elements.md)
