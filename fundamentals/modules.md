---
id: fundamentals/modules
title: ES modules
type: Concept
description: Organize code with imports and exports using the module system.
status: stable
trust: human-reviewed
stale: false
tags:
  - javascript
  - modules
  - fundamentals
---

# ES modules

JavaScript modules let you split code into reusable units with explicit boundaries.

```js
// add.js
export function add(a, b) {
  return a + b
}
```

```js
// main.js
import { add } from './add.js'

console.log(add(2, 3))
```

## Benefits

- Clear dependency boundaries
- Better reuse and testing
- Easier code organization at scale

## Related concepts

- [Objects and object literal patterns](./objects.md)
- [Function declarations and expressions](./functions.md)
- [Async JavaScript](./async.md)
