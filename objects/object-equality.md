---
id: objects/object-equality
title: Object Equality
type: objects
description: Compare objects by reference with areSame, or by matching key/value pairs with areEqual, since === only ever checks reference identity.
status: draft
tags:
  - javascript
  - objects
  - equality
  - fundamentals
---

# Object Equality

Because objects are [reference types](./value-vs-reference-types.md), `===` compares *identity*, not content — two objects with identical properties are still "different" to `===` unless they're literally the same object in memory:

```js
const circle1 = { radius: 1 };
const circle2 = { radius: 1 };

circle1 === circle2; // false — two separate objects, even though they look the same
```

This is worth naming explicitly with two small helper functions: `areSame`, for when you mean reference identity, and `areEqual`, for when you mean "do these have the same key/value pairs."

## `areSame()` — reference equality

`areSame` doesn't add any new behavior — it just gives `===` a clearer name for the case where reference identity really is what you want to check (for example, "is this the exact object I stored earlier?"):

```js
function areSame(a, b) {
  return a === b;
}

areSame(circle1, circle2); // false — different objects
areSame(circle1, circle1); // true — same object
```

## `areEqual()` — structural equality

`areEqual` instead checks that both objects have the same keys, and that every key holds the same value:

```js
function areEqual(a, b) {
  const aKeys = Object.keys(a);
  const bKeys = Object.keys(b);

  if (aKeys.length !== bKeys.length) {
    return false; // different number of properties can't be equal
  }

  return aKeys.every(key => a[key] === b[key]);
}

areEqual(circle1, circle2); // true — same keys, same values
```

Walking through it: [`Object.keys`](./enumerating-properties-of-an-object.md) lists each object's own property names; if the two objects don't even have the same *number* of keys they can't match, so that's checked first as a cheap early exit; then `every` confirms that for each of `a`'s keys, `a`'s value and `b`'s value are `===`.

## This is a *shallow* comparison

`areEqual` only compares one level deep. If a property's value is itself an object, that nested value is still compared with `===` — meaning two nested objects with identical contents still count as different:

```js
const shape1 = { center: { x: 1, y: 1 } };
const shape2 = { center: { x: 1, y: 1 } };

areEqual(shape1, shape2); // false! shape1.center and shape2.center are different objects
```

Making `areEqual` compare nested objects too — a **deep** equality check — means calling `areEqual` recursively whenever a property's value is itself an object, rather than comparing it with `===` directly.

## Related concepts

- [Value vs Reference Types](./value-vs-reference-types.md)
- [Enumerating Properties of an Object](./enumerating-properties-of-an-object.md)
- [Cloning an Object](./cloning-an-object.md)
