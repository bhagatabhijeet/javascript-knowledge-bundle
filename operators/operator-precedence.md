---
id: operators/operator-precedence
title: Operator precedence
type: operators
description: Understand the order in which JavaScript evaluates operators in compound expressions and how to use parentheses to control evaluation.
status: draft
tags:
  - javascript
  - fundamentals
  - operators
  - precedence
---

# Operator precedence

Operator precedence determines the order in which different operators are evaluated in a compound expression. Operators with higher precedence are evaluated first.

```js
let x = 2 + 3 * 4;
console.log(x); // 14, because '*' has higher precedence than '+'
```

## Controlling evaluation with parentheses

Just like basic school mathematics, you can use parentheses `()` to explicitly define the order of operations:

```js
let x = (2 + 3) * 4;
console.log(x); // 20
```

Parentheses have the highest precedence in JavaScript.

## Precedence summary (high to low)

1. **Grouping**: `( ... )`
2. **Member access / call**: `obj.prop`, `arr[0]`, `func()`
3. **Postfix increment/decrement**: `x++`, `x--`
4. **Prefix increment/decrement / Unary**: `++x`, `--x`, `!x`, `typeof x`, `+x`, `-x`
5. **Exponentiation**: `**`
6. **Multiplication, Division, Remainder**: `*`, `/`, `%`
7. **Addition, Subtraction**: `+`, `-`
8. **Relational comparisons**: `<`, `<=`, `>`, `>=`
9. **Equality comparisons**: `===`, `!==`, `==`, `!=`
10. **Bitwise AND**: `&`
11. **Bitwise XOR**: `^`
12. **Bitwise OR**: `|`
13. **Logical AND**: `&&`
14. **Logical OR / Nullish**: `||`, `??`
15. **Conditional (Ternary)**: `? :`
16. **Assignment**: `=`, `+=`, `-=`, `*=`, etc.

## Best practice

Do not force readers to memorize the exact precedence table. When combining multiple operators, always use parentheses to make your intent crystal clear:

```js
// Less clear:
let result = a + b * c > d && e;

// Clear and unambiguous:
let result = ((a + (b * c)) > d) && e;
```

## Related concepts

- [JavaScript Operators](./javascript-operators.md)
- [Arithmetic operators](./arithmetic-operators.md)
- [Logical operators](./logical-operators.md)
- [The ternary operator](./ternary-operator.md)
