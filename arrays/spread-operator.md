---
id: arrays/spread-operator
title: The Spread Operator
type: arrays
description: Combine or copy arrays with the ES6 spread operator (...), a cleaner and more flexible alternative to concat and slice.
status: draft
sources:
  - resource: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array
    title: "Array - MDN Web Docs"
tags:
  - javascript
  - arrays
  - collections
  - es6
  - fundamentals
---

# The Spread Operator

[`concat` and `slice`](./combining-and-slicing-arrays.md) aren't the only way to combine or copy arrays. ES6's **spread operator** (`...`) does the same things, often more clearly and more flexibly.

## Combining arrays

Spreading an array inside an array literal "unpacks" its elements individually, right there in place:

```js
const first = [1, 2, 3];
const second = [4, 5, 6];

const combined = [...first, ...second];

combined; // [1, 2, 3, 4, 5, 6]
```

This does exactly what `first.concat(second)` does — but written this way, you can *see* the shape of the resulting array directly in the code: "an array containing everything in `first`, followed by everything in `second`."

## More flexible than `concat()`

Because the spread happens inside a normal array literal, you're free to mix in extra elements or additional spreads anywhere you like:

```js
const combined = [...first, 'a', ...second]; // insert an element between the two arrays
combined; // [1, 2, 3, 'a', 4, 5, 6]

const combined2 = [...first, 'a', ...second, 'b']; // and add one at the end too
combined2; // [1, 2, 3, 'a', 4, 5, 6, 'b']
```

Doing either of these with `concat` alone is far more awkward — you'd need extra arrays just to wrap the inserted values. The spread operator lets you describe the exact final shape of the array in one line.

## Copying an array

Just like [`slice()` with no arguments](./combining-and-slicing-arrays.md), spreading an array into a new array literal produces a full copy:

```js
const copy = [...combined];
```

As with `slice` and `concat`, this is a **shallow** copy: primitives inside the array are copied by value, but any objects are still copied by reference — see [Combining and Slicing Arrays](./combining-and-slicing-arrays.md) for what that means in practice.

The spread operator works the same way on object literals too — see [Cloning an Object](../objects/cloning-an-object.md).

## Related concepts

- [Combining and Slicing Arrays](./combining-and-slicing-arrays.md)
- [Cloning an Object](../objects/cloning-an-object.md)
- [Value vs Reference Types](../objects/value-vs-reference-types.md)
- [Rest Operator](../functions/rest-operator.md)
