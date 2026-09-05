---
id: operators/bitwise-operators
title: Bitwise operators
type: operators
description: Manipulate numbers at the bit level with JavaScript's bitwise AND, OR, XOR, NOT, and shift operators.
status: draft
tags:
  - javascript
  - fundamentals
  - operators
  - bitwise
---

# Bitwise operators

JavaScript bitwise operators convert numeric operands into 32-bit binary integers, perform operations on individual bits, and return a standard JavaScript numerical value.

## 1. Bitwise logical operators

- **Bitwise AND (`&`)**: Returns `1` if both corresponding bits are `1`:
  ```js
  // 1 = 00000001
  // 2 = 00000010
  console.log(1 & 2); // 0 (00000000)
  ```
- **Bitwise OR (`|`)**: Returns `1` if at least one corresponding bit is `1`:
  ```js
  console.log(1 | 2); // 3 (00000011)
  ```
- **Bitwise XOR (`^`)**: Returns `1` if exactly one corresponding bit is `1`:
  ```js
  console.log(5 ^ 3); // 6 (0101 ^ 0011 = 0110)
  ```
- **Bitwise NOT (`~`)**: Inverts all bits (flips 0s to 1s and 1s to 0s):
  ```js
  console.log(~5); // -6
  ```

## 2. Bitwise shifts

- `5 << 1` — Left shift (multiplies by 2): `10`
- `5 >> 1` — Sign-preserving right shift (divides by 2): `2`
- `5 >>> 1` — Zero-fill right shift

## Practical use case: Permissions system

Bitwise operators are commonly used in access control systems to pack multiple boolean flags into a single integer:

```js
// Read, Write, Execute flags
const readPermission = 4;   // 0100
const writePermission = 2;  // 0010
const executePermission = 1;// 0001

let myPermission = 0;
// Add Read and Write permission using bitwise OR
myPermission = myPermission | readPermission | writePermission;

// Check permission using bitwise AND
let message = (myPermission & readPermission) ? 'yes' : 'no';
console.log('Can read:', message); // 'yes'
```

## Related concepts

- [JavaScript Operators](./javascript-operators.md)
- [Logical operators](./logical-operators.md)
- [Operator precedence](./operator-precedence.md)
