---
id: operators/logical-operators
title: Logical operators
type: operators
description: Combine and short-circuit expressions with logical AND, logical OR, logical NOT, and the nullish coalescing operator.
status: draft
tags:
  - javascript
  - fundamentals
  - operators
  - logical
---

# Logical operators

In JavaScript, logical operators are used to make decisions based on multiple conditions.

JavaScript provides three core logical operators:
- **Logical AND (`&&`)**: Returns `true` if **both** operands are `true`.
- **Logical OR (`||`)**: Returns `true` if **at least one** operand is `true`.
- **Logical NOT (`!`)**: Inverts the boolean value (`!true` becomes `false`).

```js
// Logical AND (&&)
console.log(true && true);   // true
console.log(true && false);  // false

// Logical OR (||)
console.log(true || false);  // true
console.log(false || false); // false

// Logical NOT (!)
console.log(!true);          // false
console.log(!false);         // true
```

## Practical example: Loan approval

```js
let highIncome = true;
let goodCreditScore = true;
let eligibleForLoan = highIncome && goodCreditScore;

console.log('Eligible:', eligibleForLoan); // Eligible: true

let applicationRefused = !eligibleForLoan;
console.log('Application Refused:', applicationRefused); // false
```

## Logical operators with non-booleans

In JavaScript, the result of a logical expression is not necessarily a boolean (`true` or `false`). Operands are evaluated based on whether they are **truthy** or **falsy**.

Falsy values:
- `undefined`
- `null`
- `0`
- `false`
- `''` (empty string)
- `NaN`

Anything that is not falsy is **truthy**.

### Short-circuit evaluation

JavaScript evaluates logical operators from left to right and stops as soon as the result is determined:

- **`||` (OR)**: Returns the first truthy operand, or the last operand if none are truthy:
  ```js
  let userColor = 'red';
  let defaultColor = 'blue';
  let currentColor = userColor || defaultColor;

  console.log(currentColor); // 'red'
  ```
- **`&&` (AND)**: Returns the first falsy operand, or the last operand if all are truthy.

## Nullish coalescing operator (`??`)

Unlike `||` (which treats `0` and `''` as falsy fallbacks), `??` falls back only when the value is `null` or `undefined`:

```js
let speed = 0;
console.log(speed || 30); // 30 (0 is falsy)
console.log(speed ?? 30); // 0 (0 is defined)
```

## Related concepts

- [JavaScript Operators](./javascript-operators.md)
- [The ternary operator](./ternary-operator.md)
- [Comparison operators](./comparison-operators.md)
- [Dynamic Types](../basics/dynamic-typing.md)
