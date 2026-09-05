# JavaScript Operators Quiz: Answers & Explanations

Here are the answers and detailed explanations for the 10 quiz questions.

---

### Question 1
**Question**: What is the result of `true && false`?  
**Correct Answer**: **b) `false`**  
**Explanation**: The logical AND operator (`&&`) returns `true` only if both operands are `true`. Since the right operand is `false`, the expression evaluates to `false`.

---

### Question 2
**Question**: What is the result of `(true && false) || true`?  
**Correct Answer**: **a) `true`**  
**Explanation**: 
1. Inside parentheses: `true && false` evaluates to `false`.
2. The remaining expression is `false || true`.
3. Logical OR (`||`) returns `true` if at least one operand is `true`. Therefore, the overall expression evaluates to `true`.

---

### Question 3
**Question**: What is the value of `y`?
```js
let x = 10;
let y = (x > 10) ? 1 : 0;
```
**Correct Answer**: **c) `0`**  
**Explanation**: The condition `x > 10` evaluates to `10 > 10`, which is `false`. The ternary operator returns the falsy branch (the value after `:`), which is `0`.

---

### Question 4
**Question**: What is the value of `x`?
```js
let x = (2 + 3) * (4 + 5);
```
**Correct Answer**: **a) `45`**  
**Explanation**: 
Parentheses override standard operator precedence:
1. `(2 + 3)` evaluates to `5`.
2. `(4 + 5)` evaluates to `9`.
3. `5 * 9` evaluates to `45`.

---

### Question 5
**Question**: Which expression returns `true`?  
**Correct Answer**: **d) `b and c`**  
**Explanation**: 
- **a) `'1' === 1`**: Returns `false` because strict equality requires both operands to be of the same type (string vs number).
- **b) `1 == 1`**: Returns `true` (loose equality with identical numbers).
- **c) `1 === 1`**: Returns `true` (strict equality with identical types and values).  
Both **b** and **c** evaluate to `true`, making **d** the correct answer.

---

### Question 6
**Question**: What is the value of `x`?
```js
let x = (1 == true);
```
**Correct Answer**: **b) `true`**  
**Explanation**: The loose equality operator `==` coerces boolean `true` into the number `1`. Then `1 == 1` evaluates to the boolean value `true`, which is assigned to `x`.

---

### Question 7
**Question**: What is the value of `y`?
```js
let x = 10;
let y = (x > 5) && (x < 15);
```
**Correct Answer**: **d) `true`**  
**Explanation**: 
1. `(x > 5)` -> `10 > 5` is `true`.
2. `(x < 15)` -> `10 < 15` is `true`.
3. `true && true` evaluates to `true`. Thus, `y` holds boolean `true`.

---

### Question 8
**Question**: What is the value of `x`?
```js
let x = 5;
x += 3;
```
**Correct Answer**: **b) `8`**  
**Explanation**: The compound assignment operator `+=` adds the right operand to the variable and assigns the result back: `x = x + 3`, which is `5 + 3 = 8`.

---

### Question 9
**Question**: What is the value of `y`?
```js
let x = 10;
let y = x++;
```
**Correct Answer**: **a) `10`**  
**Explanation**: `x++` is the **postfix** increment operator. It evaluates to the *current* value of `x` (`10`) before incrementing `x` to `11`. Therefore, `y` receives `10`. (If prefix `++x` had been used, `y` would be `11`).

---

### Question 10
**Question**: What is the value of `y`?
```js
let x = 1;
let y = x !== 2;
```
**Correct Answer**: **d) `true`**  
**Explanation**: The strict inequality operator `!==` checks whether two operands are not equal in value or type. Since `1` is not equal to `2`, the comparison evaluates to `true`.

---

👉 Back to [Quiz Questions](./questions.md) or [Root Index](../index.md).
