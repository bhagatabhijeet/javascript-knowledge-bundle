---
id: advanced/modules
title: ES modules
type: Concept
description: Organize code with imports and exports using the JavaScript module system.
status: stable
verified: { by: human:bhagatabhijeet, at: 2026-08-29T00:00:00Z }
tags:
  - javascript
  - modules
  - advanced
---

# ES modules

JavaScript modules let you split code into reusable, isolated files with explicit boundaries.

```js
// add.js
export function add(a, b) {
  return a + b;
}
```

```js
// main.js
import { add } from './add.js';

console.log(add(2, 3));
```

## Benefits of modules

- **Maintainability**: Clear dependency boundaries between units of code.
- **Reusability**: Shared utility functions across multiple modules.
- **Encapsulation**: Internal implementation details are hidden unless explicitly exported.

## Related concepts

- [Async JavaScript](./async.md)
- [Objects](../basics/objects.md)
- [Functions](../basics/functions.md)
