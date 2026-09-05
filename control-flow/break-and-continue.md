---
id: control-flow/break-and-continue
title: Break and continue
type: control-flow
description: Alter standard loop execution by breaking out early or jumping to the next iteration.
status: draft
tags:
  - javascript
  - control-flow
  - loops
  - break
  - continue
---

# Break and continue

JavaScript provides two control keywords to jump or alter the normal execution of loops: `break` and `continue`.

## The `break` statement

The `break` statement **jumps out** of a loop completely, immediately terminating the loop and continuing execution at the statement following the loop.

```js
let i = 0;

while (i <= 10) {
  if (i === 5) {
    break; // exit loop when i reaches 5
  }
  console.log(i);
  i++;
}

// Output: 0, 1, 2, 3, 4
```

## The `continue` statement

The `continue` statement **skips the current iteration** and jumps directly to the loop's next iteration (evaluating the increment expression and condition).

```js
let i = 0;

while (i <= 10) {
  if (i % 2 === 0) {
    i++;
    continue; // skip even numbers
  }
  console.log(i);
  i++;
}

// Output: 1, 3, 5, 7, 9
```

## Summary comparison

| Keyword | Action |
| :--- | :--- |
| `break` | Immediately terminates the loop and jumps past the loop block. |
| `continue` | Terminates the current step and jumps to the next iteration. |

## Related concepts

- [For loop](./for.md)
- [While loop](./while.md)
- [Do...while loop](./do-while.md)
- [Switch...case](./switch-case.md)
