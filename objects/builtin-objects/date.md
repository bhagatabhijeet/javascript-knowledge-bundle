---
id: objects/builtin-objects/date
title: Date
type: objects
description: Represent and work with points in time using JavaScript's built-in Date object.
status: draft
sources:
  - resource: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date
    title: "Date - MDN Web Docs"
tags:
  - javascript
  - objects
  - fundamentals
  - date
  - builtin-objects
---

# Date

A `Date` object represents a single point in time, internally stored as the number of milliseconds since January 1, 1970 UTC (the "epoch"). Create one with the `new Date()` constructor:

```js
const now = new Date();               // current date and time
const specific = new Date(2024, 0, 1); // January 1, 2024
const fromTimestamp = new Date(628021800000); // from milliseconds since the epoch
const fromString = new Date('2024-01-01T00:00:00'); // from an ISO 8601 string
```

⚠️ **Months are zero-based**: `0` is January and `11` is December, so `new Date(2024, 0, 1)` is January 1st, not February.

## Reading parts of a date

All of these read in the browser's **local** time zone:

```js
const now = new Date();

now.getFullYear();       // e.g. 2026
now.getMonth();          // 0-11 (zero-based)
now.getDate();           // day of the month, 1-31
now.getDay();            // day of the week, 0 (Sunday) - 6 (Saturday)
now.getHours();          // 0-23
now.getMinutes();        // 0-59
now.getTime();           // milliseconds since the epoch
```

Prefix any of these with `UTC` (e.g. `getUTCFullYear()`) to read the value in UTC instead of the local time zone.

## Dates are mutable

Unlike strings, `Date` objects are mutable — the `set...` methods change the object **in place** rather than returning a new one:

```js
const date = new Date(2000, 0, 1);
date.setFullYear(2025);
date.setMonth(11); // December — still zero-based
date.setDate(25);

date; // now represents December 25, 2025 — the same object, mutated
```

If you need to keep the original untouched, construct a new `Date` instead of mutating an existing one.

## Getting the current timestamp

`Date.now()` returns the current time in milliseconds since the epoch without creating a `Date` instance — useful for measuring elapsed time:

```js
const start = Date.now();
// ... some work ...
const elapsedMs = Date.now() - start;
```

## Formatting for display

```js
const date = new Date('2020-05-12T23:50:21.817Z');

date.toLocaleDateString(); // '5/12/2020' — formatted per the user's locale
date.toLocaleTimeString(); // '6:50:21 PM'
date.toDateString();       // 'Tue May 12 2020'
date.toISOString();        // '2020-05-12T23:50:21.817Z' — standard, unambiguous, UTC
```

When parsing a date from a string, prefer the standardized ISO 8601 format (`YYYY-MM-DDTHH:mm:ss`) — other formats are parsed inconsistently across browsers.

## Related concepts

- [Constructor Functions](../constructor-functions.md)
- [Math](./math.md)
- [String](./string.md)
