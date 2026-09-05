---
id: control-flow/infinite-loops
title: Infinite loops
type: control-flow
description: Understand what causes infinite loops, the danger of freezing browser tabs or crashing processes, and how to avoid them.
status: draft
tags:
  - javascript
  - control-flow
  - loops
  - bugs
---

# Infinite loops

An **infinite loop** occurs when a loop's termination condition is never reached or consistently evaluates to `true`. Because JavaScript runs on a single thread, an infinite loop will block the thread, freezing the browser tab or consuming 100% CPU on a Node.js process.

## Common causes

### 1. Forgetting to increment the loop variable

```js
// Danger: i is never incremented, so i < 5 remains true forever!
let i = 0;
while (i < 5) {
  console.log(i);
  // Missing: i++;
}
```

### 2. Condition that can never be met

```js
// Danger: i starts at 0 and decrements, moving further away from 10
for (let i = 0; i >= 0; i++) {
  console.log(i);
}
```

### 3. Explicit `while (true)` without a `break`

```js
// Danger: will run forever unless break is called
while (true) {
  // requires an explicit break condition!
}
```

## How to recover

- In a web browser: Close the unresponsive browser tab or open Chrome Task Manager (`Shift+Esc`) and terminate the tab.
- In Node.js / Terminal: Press `Ctrl + C` in your terminal to forcefully abort execution.

## Prevention tips

1. Always double-check your loop's increment or update expression.
2. Confirm the boundary condition eventually becomes `false`.
3. If using `while (true)` to poll or wait, ensure an explicit `break` condition exists.

## Related concepts

- [For loop](./for.md)
- [While loop](./while.md)
- [Break and continue](./break-and-continue.md)
