---
id: fundamentals/node
title: JavaScript in Node.js
type: Concept
description: Install Node.js and run JavaScript outside the browser, including modules, globals, and npm basics.
status: draft
tags:
  - javascript
  - node.js
  - runtime
  - fundamentals
  - tooling
  - setup
generated: { by: claude/sonnet-5, at: 2026-08-29T00:00:00Z }
sources:
  - resource: https://nodejs.org/
  - resource: https://docs.npmjs.com/
  - resource: https://github.com/nvm-sh/nvm
  - resource: https://github.com/coreybutler/nvm-windows
---

# JavaScript in Node.js

Node.js runs JavaScript outside the browser using the V8 engine plus a set of APIs for files, networking, and processes. It is used for command-line tools, build tooling, servers, and scripts that do not need a DOM.

## Install Node.js

### Option 1: official installer

Download an installer for Windows or macOS from the official Node.js website and run it. This installs both `node` and `npm`.

### Option 2: a version manager (recommended for multiple projects)

A version manager lets you switch Node.js versions per project instead of relying on one system-wide install.

macOS and Linux, using nvm:

```sh
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.1/install.sh | bash
nvm install --lts
nvm use --lts
```

Windows, using nvm-windows:

```powershell
winget install CoreyButler.NVMforWindows
nvm install lts
nvm use lts
```

### Option 3: a system package manager

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

Prefer an even-numbered LTS release for new projects unless a specific version is required.

## Running JavaScript with Node

Run a file directly:

```sh
node app.js
```

Or start the REPL for quick, interactive experiments:

```sh
node
> 1 + 2
3
```

## Modules in Node

Node supports two module systems. CommonJS is the historical default:

```js
// math.js
module.exports.add = (a, b) => a + b

// app.js
const { add } = require('./math.js')
console.log(add(2, 3))
```

ES modules use `import`/`export` syntax. Enable them either by naming files `.mjs` or by adding `"type": "module"` to `package.json`:

```js
// math.mjs
export const add = (a, b) => a + b

// app.mjs
import { add } from './math.mjs'
console.log(add(2, 3))
```

## Node-specific globals

- `process` — environment variables (`process.env`), arguments (`process.argv`), and exit control (`process.exit()`).
- `Buffer` — fixed-size binary data, used when reading files or handling network data.
- `__dirname` and `__filename` — available in CommonJS modules; ES modules use `import.meta.url` instead.
- `global` — the Node equivalent of the browser's `window`, rarely used directly.

## npm and package.json

`npm` installs and manages dependencies, and `package.json` records them.

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

Commit `package.json` and a lockfile (`package-lock.json`); do not commit `node_modules/`.

## Related concepts

- [JavaScript introduction](./introduction.md)
- [Setting up the Development Environment](./setting-up-the-development-environment.md)
- [ES modules](./modules.md)
- [Async JavaScript](./async.md)

This draft was generated from general knowledge of official Node.js and npm documentation and has not been checked against a live source. It should receive human review before its status is promoted or a `verified` entry is added.
