---
id: objects/cloning-an-object
title: Cloning an Object
type: objects
description: Copy an object's properties into a new object using Object.assign, the spread operator, or structuredClone.
status: draft
tags:
  - javascript
  - objects
  - fundamentals
  - reference-types
---

# Cloning an Object

Because objects are [reference types](./value-vs-reference-types.md), assigning one variable to another does not create a copy. To get an independent copy, you need to clone it explicitly.

## Object.assign()

`Object.assign(target, ...sources)` copies the own enumerable properties of one or more **source** objects onto a **target** object, and returns that same target:

```js
const circle = { radius: 1, color: 'yellow' };
const clone = Object.assign({}, circle);

clone.radius; // 1
clone === circle; // false — a new, independent object
```

### Why the first argument is `{}`

The first argument is the object being *written to*. Passing an empty object literal `{}` means "create a brand-new object and copy `circle`'s properties into it" — that new object is also what `Object.assign` returns, which is why it can be assigned straight to `clone`.

If you pass an existing object as the target instead, `Object.assign` **mutates** it in place rather than cloning:

```js
const target = { color: 'red' };
Object.assign(target, circle);

target; // { color: 'yellow', radius: 1 } — target itself was changed
```

### Merging multiple sources

Any number of source objects can follow the target. Later sources overwrite matching keys from earlier ones:

```js
const defaults = { radius: 1, color: 'yellow' };
const overrides = { color: 'red' };

const merged = Object.assign({}, defaults, overrides);
merged; // { radius: 1, color: 'red' }
```

## Spread operator

The spread operator (`...`) is a more concise, modern way to do the same thing. Inside an object literal, `...circle` expands `circle`'s own enumerable properties in place, as if you'd typed them out individually:

```js
const circle = { radius: 1, color: 'yellow' };
const clone = { ...circle };

clone; // { radius: 1, color: 'yellow' }
clone === circle; // false — a new, independent object
```

Unlike `Object.assign`, there's no separate "target" argument to get confused about — spreading only ever builds a brand-new object literal, so it can never accidentally mutate `circle`.

### Overriding properties while cloning

Because `{ ...circle }` is just a normal object literal, you can add or override properties in the same expression by listing them after the spread — later keys win:

```js
const bigCircle = { ...circle, radius: 10 };
bigCircle; // { radius: 10, color: 'yellow' }
```

### Merging multiple objects

Spreading more than one object merges them, with later spreads overwriting matching keys from earlier ones — the same "last one wins" rule as `Object.assign`:

```js
const defaults = { radius: 1, color: 'yellow' };
const overrides = { color: 'red' };

const merged = { ...defaults, ...overrides };
merged; // { radius: 1, color: 'red' }
```

Both `Object.assign` and the spread operator perform a **shallow** clone: nested objects are still shared by reference between the original and the clone.

## Deep cloning

To copy nested objects as well, use `structuredClone`, available in modern JavaScript runtimes:

```js
const deepClone = structuredClone(circle);
```

An older workaround using `JSON.parse(JSON.stringify(circle))` also produces a deep clone, but silently drops values `JSON` cannot represent, such as functions, `undefined`, and `Date` objects (which are converted to strings).

## Related concepts

- [Value vs Reference Types](./value-vs-reference-types.md)
- [Enumerating Properties of an Object](./enumerating-properties-of-an-object.md)
