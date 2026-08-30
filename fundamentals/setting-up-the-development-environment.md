---
id: fundamentals/setting-up-the-development-environment
title: Setting up the Development Environment
type: Concept
description: Prepare a practical JavaScript workspace with Node.js, a code editor, a project folder, and a local development server.
status: draft
tags:
  - javascript
  - fundamentals
  - setup
  - tooling
  - node.js
sources:
  - resource: 'C:\Users\bhaga\Downloads\af06931e-92c4-467b-8aba-e1af0a8ca76f.mp4'
    title: Local source video
  - resource: https://nodejs.org/
  - resource: https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Overview
---

# Setting up the Development Environment

A consistent development environment makes it easier to write, run, and inspect JavaScript. Start with a runtime, choose an editor, create a project folder, and use a local server when browser behavior depends on modules or fetched resources.

## Install a JavaScript runtime

Install Node.js from the official Node.js website. Node.js provides a JavaScript runtime outside the browser and includes npm, the package manager used by many JavaScript projects.

Verify the installation in a terminal:

```sh
node --version
npm --version
```

Keep the runtime version consistent across a project when possible. A project may document its supported version with an `.nvmrc` file, an `engines` field, or a version manager configuration.

## Choose an editor

Use an editor that supports JavaScript syntax highlighting, search, a terminal, and useful diagnostics. The video shows Visual Studio Code, Sublime Text, and Atom as examples. The specific editor matters less than being able to navigate files, run commands, and understand errors.

Recommended editor capabilities include:

- JavaScript and JSON syntax highlighting
- integrated terminal access
- format-on-save or a formatter
- linting and error diagnostics
- source control integration
- extensions for browser development

## Create a project folder

Create one folder for each learning exercise or application. For example:

```text
js-basics/
  index.html
  app.js
  styles.css
```

Open the project folder itself in the editor rather than opening individual files. This keeps relative paths, search, and source-control operations consistent.

A minimal `index.html` can load a JavaScript module:

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>JavaScript Basics</title>
  </head>
  <body>
    <h1>JavaScript Basics</h1>
    <script type="module" src="./app.js"></script>
  </body>
</html>
```

## Preview in a local server

For simple pages, opening `index.html` directly may be enough. Use a local development server when the project uses JavaScript modules, fetch requests, or browser APIs that require an HTTP origin.

In Visual Studio Code, an extension such as Live Server can launch a local URL and refresh the page while files change. Treat extensions as development tools: inspect their permissions and use trusted projects.

A command-line server is another option. For example, after installing a suitable development-server package, run it from the project folder and open the displayed local URL in a browser.

## A reliable first-run checklist

1. Confirm `node --version` and `npm --version` work.
2. Create and open a dedicated project folder.
3. Add `index.html` and a JavaScript entry file.
4. Load the script with `type="module"` when using imports.
5. Open the project through a local server when required.
6. Check the browser console and terminal for errors.
7. Add a README describing how to run the project.

## Related concepts

- [JavaScript introduction](./introduction.md)
- [ES modules](./modules.md)
- [Function declarations and expressions](./functions.md)
- [JavaScript in Node.js](./node.md)

This draft was derived from visible content in the source video listed in frontmatter and should receive human review before its status is promoted or a `verified` entry is added.
