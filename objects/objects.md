---
id: objects/objects
title: Objects
type: objects
description: Understand object literals, property access, methods, and reference semantics in JavaScript.
status: draft
tags:
  - javascript
  - objects
  - fundamentals
---

# Objects

Objects are foundational to JavaScript. An object is a collection of related properties and methods that model real-world entities and manage application state.

```js
const circle = {
  radius: 1,
  location: {
    x: 1,
    y: 1
  },
  isVisible: true,
  draw: function() {
    console.log('draw circle');
  }
};

circle.draw(); // Method call
```

## Property access

JavaScript provides two ways to access object members:
1. **Dot notation**: `circle.radius` (clean, preferred for known static keys).
2. **Bracket notation**: `circle['radius']` (flexible for dynamic keys evaluated at runtime).

## Dynamic nature of objects

JavaScript objects are dynamic: once created, you can add, modify, or delete properties at any time:

```js
const circle = { radius: 1 };

// Adding properties
circle.color = 'yellow';
circle.draw = function() {};

// Deleting properties
delete circle.color;
```

## Related concepts

- [Variables](../basics/variables.md)
- [Constants](../basics/constants.md)
- [Arrays](../arrays/arrays.md)
- [Functions](../functions/functions.md)
