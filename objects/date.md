---
id: objects/date
title: Date
type: objects
description: Represent and work with points in time using JavaScript's built-in Date object.
status: draft
tags:
  - javascript
  - objects
  - fundamentals
  - date
---

# Date

The `Date` object represents a single point in time. Create one with the `new Date()` constructor:

```js
const now = new Date();          // current date and time
const specific = new Date(2024, 0, 1); // January 1, 2024 (months are zero-based)
```

## Reading parts of a date

```js
const now = new Date();

now.getFullYear(); // e.g. 2026
now.getMonth();    // 0-11 (zero-based)
now.getDate();      // day of the month, 1-31
now.getDay();       // day of the week, 0 (Sunday) - 6 (Saturday)
now.getTime();      // milliseconds since January 1, 1970 (the Unix epoch)
```

## Getting the current timestamp

`Date.now()` returns the current time in milliseconds since the epoch without creating a `Date` instance — useful for measuring elapsed time:

```js
const start = Date.now();
// ... some work ...
const elapsedMs = Date.now() - start;
```

## Formatting for display

```js
now.toLocaleDateString(); // e.g. '9/5/2026', formatted per the user's locale
```

## Related concepts

- [Constructor Functions](./constructor-functions.md)
- [Math](./math.md)
