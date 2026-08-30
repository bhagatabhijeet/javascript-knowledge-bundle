---
id: fundamentals/async
title: Async JavaScript
type: Concept
description: Learn the event loop, promises, and async/await for working with asynchronous work.
status: stable
verified: { by: human:bhagatabhijeet, at: 2026-08-29T00:00:00Z }
tags:
  - javascript
  - async
  - fundamentals
---

# Async JavaScript

Modern JavaScript programs frequently rely on asynchronous work such as API calls, timers, and I/O operations.

## Promise

A promise represents eventual completion or failure.

```js
const task = new Promise((resolve, reject) => {
  setTimeout(() => resolve('done'), 100)
})
```

## async / await

`async` and `await` make asynchronous code read more like synchronous logic.

```js
async function loadUser() {
  const response = await fetch('/api/user')
  return response.json()
}
```

## Why this matters

Asynchronous patterns help avoid blocking and keep apps responsive.

## Related concepts

- [Function declarations and expressions](./functions.md)
- [ES modules](./modules.md)
- [JavaScript introduction](./introduction.md)
- [Types of functions](./function-types.md)
