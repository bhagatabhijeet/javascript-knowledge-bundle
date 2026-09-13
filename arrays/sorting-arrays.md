---
id: arrays/sorting-arrays
title: Sorting Arrays
type: arrays
description: Sort an array in place with sort(), reverse it with reverse(), and write a compare function to sort arrays of objects correctly.
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

# Sorting Arrays

## `sort()`

`sort()` reorders the elements of an array **in place** (it mutates the original array, unlike `slice` or `concat`):

```js
const numbers = [2, 3, 1];
numbers.sort();

numbers; // [1, 2, 3]
```

## `reverse()`

`reverse()` is `sort`'s frequent companion — it flips the order of the elements currently in the array, also in place:

```js
numbers.reverse();

numbers; // [3, 2, 1]
```

## Why `sort()` "doesn't work" on objects

`sort()` works by converting each element to a **string** and comparing those strings. That happens to give the right answer for a simple array of single-digit numbers, but it silently breaks down for anything else — including an array of objects, where every element converts to the same unhelpful string:

```js
const courses = [
  { id: 1, name: 'Node.js' },
  { id: 2, name: 'javaScript' }
];

courses.sort();
console.log(courses); // unchanged — sort has no idea how to compare two objects
```

## Fixing it with a compare function

`sort()` optionally takes a **compare function**. For every pair of elements `a` and `b` it needs to compare, `sort` calls this function and uses its return value to decide their order:

- return a negative number (conventionally `-1`) if `a` should come **before** `b`
- return a positive number (conventionally `1`) if `a` should come **after** `b`
- return `0` if they're equal — leave their order alone

```js
courses.sort(function (a, b) {
  // a < b => -1
  // a > b => 1
  // a === b => 0
  if (a.name < b.name) return -1;
  if (a.name > b.name) return 1;
  return 0;
});
```

Note there's no `else` anywhere here — as soon as one `return` runs, the function exits immediately, so a later condition can never contradict an earlier one. Adding `else` would only add noise.

## The case-sensitivity gotcha

Even with a compare function, `'javaScript' < 'Node.js'` is `false` — because each character compares by its underlying numeric code, and every lowercase letter's code is *higher* than every uppercase letter's. On the [ASCII table](https://en.wikipedia.org/wiki/ASCII), lowercase `j` is `106` while uppercase `N` is `78`, so `'N'` sorts before `'j'` even though "javaScript" would naturally come first alphabetically:

```js
courses.sort(function (a, b) {
  if (a.name < b.name) return -1; // 'N' (78) looks "smaller" than 'j' (106)
  if (a.name > b.name) return 1;
  return 0;
});
// 'Node.js' incorrectly sorts before 'javaScript'
```

The fix is to normalize both names to the same case — either `.toLowerCase()` or `.toUpperCase()` works, as long as **both** sides use the same one — before comparing:

```js
courses.sort(function (a, b) {
  const nameA = a.name.toLowerCase();
  const nameB = b.name.toLowerCase();

  if (nameA < nameB) return -1;
  if (nameA > nameB) return 1;
  return 0;
});
// 'javaScript' now correctly comes before 'Node.js'
```

## Related concepts

- [Finding Elements (References)](./finding-elements-references.md)
- [String](../objects/builtin-objects/string.md)
- [call, apply, and bind](../functions/call-apply-bind.md)
