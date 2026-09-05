---
id: operators/logical-operators-with-non-booleans
title: Logical Operators with Non-Booleans
type: operators
description: Learn how JavaScript logical operators evaluate non-boolean operands using truthy and falsy values and short-circuit evaluation.
status: draft
tags:
  - javascript
  - operators
  - logical
  - truthy
  - falsy
  - short-circuit
---

# Logical Operators with Non-Booleans

In JavaScript, logical operators (`||` and `&&`) do not simply return `true` or `false`. When applied to non-boolean values, they return one of the operands itself.

## Falsy and truthy values

JavaScript evaluates operands based on whether they are **truthy** or **falsy**.

There are only six **falsy** values in JavaScript:
- `undefined`
- `null`
- `0`
- `false`
- `''` (empty string)
- `NaN`

**Anything that is not falsy is truthy** (including `'0'`, `'false'`, `[]`, `{}`, and any non-zero number).

## Logical OR (`||`) with non-booleans

The logical OR operator evaluates operands from left to right and returns the **first truthy operand** it encounters. If all operands are falsy, it returns the last operand.

This behavior is called **short-circuit evaluation**:

```js
false || 'Alice';        // 'Alice'
false || 1;              // 1
false || 1 || 2;         // 1 (short-circuits at 1, 2 is never evaluated)
undefined || null || 0;  // 0 (all falsy, returns last operand)
```

### Real-world use case: Default fallback values

A common pattern is providing fallback defaults for optional configurations or user preferences:

```js
let userColor = undefined;
let defaultColor = 'blue';

let currentColor = userColor || defaultColor;
console.log(currentColor); // 'blue'
```

If the user later selects a color:

```js
let userColor = 'red';
let defaultColor = 'blue';

let currentColor = userColor || defaultColor;
console.log(currentColor); // 'red'
```

## Logical AND (`&&`) with non-booleans

The logical AND operator evaluates operands from left to right and returns the **first falsy operand** it encounters. If all operands are truthy, it returns the **last operand**.

```js
true && 'Alice';       // 'Alice'
'Alice' && 'Bob';      // 'Bob' (both truthy, returns last operand)
'Alice' && '' && 'Bob';// '' (short-circuits at empty string)
```

### Real-world use case: Guarding property access

```js
const user = { name: 'Alice' };

// Only access user.name if user exists
const name = user && user.name;
console.log(name); // 'Alice'
```

## Related concepts

- [Logical operators](./logical-operators.md)
- [Ternary operator](./ternary-operator.md)
- [Dynamic Types](../basics/dynamic-typing.md)
