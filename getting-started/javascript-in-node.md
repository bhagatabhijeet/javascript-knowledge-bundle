---
id: getting-started/javascript-in-node
title: JavaScript in Node
type: Concept
description: Install Node.js and run JavaScript outside the browser, including modules, globals, and npm basics.
status: draft
tags:
  - javascript
  - getting-started
  - node.js
  - runtime
  - fundamentals
  - tooling
---

# JavaScript in Node

Node.js runs JavaScript outside the browser using Google Chrome's V8 engine plus a set of C++ APIs for files, networking, and system processes. It enables JavaScript for command-line tools, build tooling, backend APIs, and servers.

## Install Node.js

### Option 1: Official installer

Download an installer for Windows or macOS from the official [Node.js website](https://nodejs.org/) and run it. This installs both `node` and `npm`.

### Option 2: A version manager (recommended for multiple projects)

A version manager lets you switch Node.js versions per project instead of relying on a single system-wide install.

macOS and Linux, using `nvm`:

```sh
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.1/install.sh | bash
nvm install --lts
nvm use --lts
```

Windows, using `nvm-windows`:

```powershell
winget install CoreyButler.NVMforWindows
nvm install lts
nvm use lts
```

### Option 3: A system package manager

```sh
# macOS (Homebrew)
brew install node

# Windows (winget)
winget install OpenJS.NodeJS.LTS

# Debian/Ubuntu
sudo apt install nodejs npm
```

### Verify the installation

```sh
node --version
npm --version
```

Prefer an even-numbered LTS (Long Term Support) release for new projects.

## Running JavaScript with Node

Run a file directly from the terminal:

```sh
node app.js
```

Or start the interactive REPL (Read-Eval-Print Loop):

```sh
node
> 1 + 2
3
```

## Modules in Node

Node supports two module systems. CommonJS is the traditional format:

```js
// math.js
module.exports.add = (a, b) => a + b;

// app.js
const { add } = require('./math.js');
console.log(add(2, 3));
```

ES modules use `import`/`export` syntax. Enable them either by naming files `.mjs` or by adding `"type": "module"` to `package.json`:

```js
// math.mjs
export const add = (a, b) => a + b;

// app.mjs
import { add } from './math.mjs';
console.log(add(2, 3));
```

## Node-specific globals

- `process` — environment variables (`process.env`), command arguments (`process.argv`), and exit control (`process.exit()`).
- `Buffer` — fixed-size binary data chunks used when reading files or handling network streams.
- `__dirname` and `__filename` — available in CommonJS modules (ES modules use `import.meta.url` instead).
- `global` — the Node equivalent of the browser's `window` object.

## npm and package.json

`npm` installs and manages dependencies, and `package.json` records project dependencies and scripts:

```sh
npm init -y
npm install express
```

```json
{
  "name": "my-app",
  "version": "1.0.0",
  "dependencies": {
    "express": "^4.19.0"
  }
}
```

Commit `package.json` and `package-lock.json` to source control; never commit `node_modules/`.

## Related concepts

- [What is JavaScript](./what-is-javascript.md)
- [Setting up the Development Environment](./setting-up-the-development-environment.md)
- [JavaScript in Browsers](./javascript-in-browsers.md)
- [Separation of Concerns](./separation-of-concerns.md)
- [ES modules](../advanced/modules.md)
- [Async JavaScript](../advanced/async.md)
