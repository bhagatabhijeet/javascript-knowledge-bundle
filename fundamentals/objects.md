---
id: fundamentals/objects
title: Objects and object literal patterns
type: js-basics
description: Understand object literals, property access, and shared state in JavaScript.
status: stable
verified: { by: human:bhagatabhijeet, at: 2026-08-29T00:00:00Z }
tags:
  - javascript
  - fundamentals
  - objects
---

# Objects and object literal patterns

Objects are the core data structure for JavaScript programs. They can store data, methods, and nested structures.

```js
const user = {
  name: 'Ada',
  role: 'Engineer',
  greet() {
    return `Hi ${this.name}`
  },
}
```

## Access patterns

Use dot notation for static keys and bracket notation for computed keys.

```js
user.name
user['role']
```

## In practice

Objects are central to configuration, data transfer, and module exports.

## Related concepts

- [Variables and declarations](./variables.md)
- [Function declarations and expressions](./functions.md)
- [ES modules](./modules.md)
- [Arrays](./arrays.md)
- [Primitive data types](./primitive-types.md)
