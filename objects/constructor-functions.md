---
id: objects/constructor-functions
title: Constructor Functions
type: objects
description: Create objects with the `new` operator using a constructor function and the `this` keyword.
status: draft
tags:
  - javascript
  - objects
  - fundamentals
  - constructor-functions
---

# Constructor Functions

A **constructor function** builds an object using the `new` operator. By convention its name is capitalized (PascalCase) to signal that it must be called with `new`.

```js
function Circle(radius) {
  this.radius = radius;
  this.draw = function () {
    console.log('draw');
  };
}

const circle = new Circle(1);
```

## What `new` does

When a function is invoked with `new`, JavaScript performs four steps automatically:

1. Creates a new, empty object.
2. Sets `this` inside the function to that new object.
3. Executes the function body, which typically assigns properties to `this`.
4. Returns the new object (unless the function explicitly returns a different object).

## Built-in constructors

JavaScript provides several built-in constructors, such as `String`, `Boolean`, `Number`, and `Object`:

```js
const color = new String('red');
typeof color; // 'object', not 'string'
```

Using `new` with these built-ins produces a wrapper object rather than a primitive, which is rarely what you want — prefer literals (`'red'`, `1`, `true`, `{}`) for everyday values.

## Related concepts

- [Factory Functions](./factory-functions.md)
- [Constructor Property](./constructor-property.md)
- [Basics](./basics.md)
