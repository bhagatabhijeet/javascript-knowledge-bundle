---
id: advanced/async
title: Async JavaScript
type: Concept
description: Learn the event loop, promises, and async/await for working with asynchronous tasks in JavaScript.
status: stable
verified: { by: human:bhagatabhijeet, at: 2026-08-29T00:00:00Z }
tags:
  - javascript
  - async
  - advanced
---

# Async JavaScript

Modern JavaScript programs frequently rely on asynchronous work such as API calls, timers, and I/O operations.

## Promises

A promise represents the eventual completion or failure of an asynchronous operation.

```js
const task = new Promise((resolve, reject) => {
  setTimeout(() => resolve('done'), 100);
});

task.then(result => console.log(result));
```

## async / await

`async` and `await` syntax makes asynchronous code read and behave more like synchronous logic:

```js
async function loadUser() {
  const response = await fetch('/api/user');
  return response.json();
}
```

## Why this matters

Asynchronous patterns prevent blocking the single JavaScript execution thread and keep applications responsive to user interaction.

## Related concepts

- [ES modules](./modules.md)
- [Functions](../basics/functions.md)
- [Types of Functions](../basics/function-types.md)
