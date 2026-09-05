---
id: operators/javascript-operators
title: JavaScript Operators
type: operators
description: An introduction to operators in JavaScript, how operands and operators interact, and categories of operators.
status: draft
tags:
  - javascript
  - fundamentals
  - operators
---

# JavaScript Operators

In JavaScript, an **operator** is a special symbol used to perform operations on values and variables. The values acted upon by operators are called **operands**.

```js
let x = 10;
let y = 5;

// '+' is the operator, 'x' and 'y' are operands
let sum = x + y;
```

We use operators alongside variables and constants to create expressions and implement application logic.

## Categories of JavaScript operators

JavaScript provides several types of operators, categorized by the operations they perform:

1. **Arithmetic operators**: Perform mathematical calculations (`+`, `-`, `*`, `/`, `%`, `**`, `++`, `--`).
2. **Assignment operators**: Assign or update values in variables (`=`, `+=`, `-=`, `*=`, `/=`).
3. **Comparison operators**: Compare values and return a boolean result (`<`, `>`, `<=`, `>=`).
4. **Equality operators**: Determine whether two values are equal (`==`, `===`, `!=`, `!==`).
5. **Ternary operator**: A concise three-operand conditional operator (`condition ? a : b`).
6. **Logical operators**: Make decisions based on multiple conditions (`&&`, `||`, `!`, `??`).
7. **Bitwise operators**: Treat operands as 32-bit binary integers and manipulate individual bits (`&`, `|`, `^`, `~`, `<<`, `>>`).

## Operator arity

Operators can also be classified by the number of operands they require:
- **Unary**: Takes one operand (e.g. `++x`, `-x`, `typeof x`, `!x`).
- **Binary**: Takes two operands (e.g. `x + y`, `x > y`).
- **Ternary**: Takes three operands (e.g. `condition ? exprIfTrue : exprIfFalse`).

## Related concepts

- [Arithmetic operators](./arithmetic-operators.md)
- [Assignment operators](./assignment-operators.md)
- [Comparison operators](./comparison-operators.md)
- [Equality operators](./equality-operators.md)
- [The ternary operator](./ternary-operator.md)
- [Logical operators](./logical-operators.md)
- [Bitwise operators](./bitwise-operators.md)
- [Operator precedence](./operator-precedence.md)
- [Quiz: Questions](../quiz/questions.md)
