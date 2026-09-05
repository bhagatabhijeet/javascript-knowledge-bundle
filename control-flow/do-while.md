---
id: control-flow/do-while
title: Do...while loop
type: control-flow
description: Execute a code block at least once before evaluating the loop condition.
status: draft
tags:
  - javascript
  - control-flow
  - loops
  - do-while
---

# Do...while loop

A `do...while` loop is a variant of the `while` loop with one crucial difference: it evaluates the condition **after** executing the block of code.

As a result, a `do...while` loop is guaranteed to execute **at least once**, even if the condition is `false` from the start.

## Syntax

```js
do {
  // statement to execute at least once
  // increment/step
} while (condition);
```

Notice the required semicolon `;` at the end of the `while (condition);` line.

## Example

```js
let i = 9;

do {
  if (i % 2 !== 0) {
    console.log(i);
  }
  i++;
} while (i <= 5);

// Output: 9
// Even though 9 is not <= 5, the block ran once!
```

## Related concepts

- [While loop](./while.md)
- [For loop](./for.md)
- [Infinite loops](./infinite-loops.md)
