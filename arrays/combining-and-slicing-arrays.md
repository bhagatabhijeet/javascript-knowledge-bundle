---
id: arrays/combining-and-slicing-arrays
title: Combining and Slicing Arrays
type: arrays
description: Combine two arrays with concat, extract a portion of one with slice, and understand how both copy primitives by value but objects by reference.
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

# Combining and Slicing Arrays

`concat` and `slice` are opposites: one **combines** two arrays into a new one, the other **extracts** a portion out of one. Neither of them mutates the array it's called on.

## Combining two arrays: `concat()`

```js
const first = [1, 2, 3];
const second = [4, 5, 6];

const combined = first.concat(second);

combined; // [1, 2, 3, 4, 5, 6]
first;    // [1, 2, 3] — unchanged
second;   // [4, 5, 6] — unchanged
```

`concat` doesn't touch either original array — it **returns a brand-new array** that is the combination of the two.

## Slicing part of an array: `slice()`

`slice` is the opposite: instead of combining, it extracts a portion of an array into a new one, without touching the original. It's flexible depending on which arguments you give it.

### 1. Start and end index

`slice(start, end)` extracts elements from `start` up to (but not including) `end`:

```js
const slice = combined.slice(2, 4);

slice; // [3, 4] — index 2 up to (not including) index 4
```

### 2. Just a start index

Omit `end` to get everything from `start` to the end of the array:

```js
combined.slice(2); // [3, 4, 5, 6] — from index 2 to the end
```

### 3. No arguments at all

Omit both, and `slice()` returns a full **shallow copy** of the entire array:

```js
combined.slice(); // [1, 2, 3, 4, 5, 6] — a full copy
```

## Primitives are copied by value, objects by reference

Both `concat` and `slice` copy each element into the new array — but what "copy" means depends on the element's type, exactly as with [cloning an object](../objects/cloning-an-object.md). Primitives (numbers, strings, booleans) are copied by their **value**. Objects are copied by their **reference** — the new array gets a pointer to the *same* object, not a duplicate of it:

```js
const first = [{ id: 1 }];
const second = [4, 5, 6];

const combined = first.concat(second);

first[0].id = 10; // mutate the object through the original array

combined[0].id; // 10 — combined[0] is the exact same object as first[0]
```

Because `first[0]` and `combined[0]` reference the *same* object in memory, mutating it through one array is visible through the other. The same rule applies to `slice`: slicing an array of objects copies the references, not the objects themselves. If you need independent copies of the objects too — not just of the array — see [Cloning an Object](../objects/cloning-an-object.md).

## Related concepts

- [The Spread Operator](./spread-operator.md)
- [Adding Elements](./adding-elements.md)
- [Emptying an Array](./emptying-an-array.md)
- [Value vs Reference Types](../objects/value-vs-reference-types.md)
- [Cloning an Object](../objects/cloning-an-object.md)
