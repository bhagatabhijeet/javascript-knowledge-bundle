---
id: control-flow/while
title: While loop
type: control-flow
description: Repeat a statement while a condition evaluates to true, checking the condition before each iteration.
status: draft
tags:
  - javascript
  - control-flow
  - loops
  - while
---

# While loop

A `while` loop checks its condition **before** executing each iteration. If the condition is initially `false`, the loop body never runs.

## Syntax

```js
while (condition) {
  // statement to execute while condition is true
}
```

Unlike the `for` loop, you declare the loop counter variable outside the loop, and increment it inside the loop body.

## Example

```js
let i = 0;

while (i <= 5) {
  if (i % 2 !== 0) {
    console.log(i); // prints 1, 3, 5
  }
  i++;
}
```

## `for` vs. `while`

- Use a **`for` loop** when the number of iterations is known ahead of time.
- Use a **`while` loop** when the number of iterations depends on an external condition (such as reading lines until end of file, waiting for user input, or random conditions).

## Related concepts

- [For loop](./for.md)
- [Do...while loop](./do-while.md)
- [Infinite loops](./infinite-loops.md)
- [Break and continue](./break-and-continue.md)
