---
id: getting-started/separation-of-concerns
title: Separation of Concerns
type: Concept
description: Organize web applications by separating HTML content from JavaScript behavior using external script files.
status: draft
tags:
  - javascript
  - getting-started
  - architecture
  - best-practices
  - html
  - dom
    title: 'Separation of Concerns (the instructor, example.com)'
  - resource: https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/What_is_JavaScript#where_does_javascript_fit_into_your_page
---

# Separation of Concerns

**Separation of concerns** is a fundamental software engineering principle stating that different parts of an application should manage distinct responsibilities.

In web development, we separate:
- **HTML**: all about **content** and structure.
- **JavaScript**: all about **behavior** (what should happen when a user interacts with the page, hovers over an element, or submits data).

```text
HTML  ──>  Content & Structure
JS    ──>  Behavior & Interactivity
```

![Separation of concerns in web design: HTML for structure, CSS for styling, JavaScript for interactivity](../assets/images/separation-of-concerns.jpg)

*Image courtesy: Gemini 3.8 Flash. CSS (styling) is shown here for completeness as the third pillar of front-end separation of concerns; this document focuses specifically on the HTML/JavaScript split.*

## The bedroom and kitchen metaphor

Think of your home:
- In your **bedroom**, you have your bed and your clothes.
- You do not store your clothes in the **kitchen**.

Each room has a distinct purpose and concern. Mixing them causes clutter and confusion. The same principle applies directly to web development: HTML should not be cluttered with inline JavaScript logic.

## Why separate HTML and JavaScript?

While writing JavaScript inline between `<script>` tags inside `index.html` works for a single line of code, real-world applications have thousands or even millions of lines of code.

Writing all that logic inline creates several problems:
1. **Cluttered markup**: HTML files become bloated, difficult to navigate, and hard to read.
2. **Poor maintainability**: Updating page layout can accidentally break application logic, and vice versa.
3. **No code reuse**: Logic written inline in one HTML file cannot be shared across other pages.
4. **Production bundling**: In real-world projects with hundreds of JavaScript files, build tools bundle and optimize `.js` files into bundles served efficiently to clients.

## Extracting JavaScript into an external file

To separate concerns, extract script logic into a dedicated JavaScript file (e.g., `index.js`).

### Step 1: Create `index.js`

In your project folder, create a standalone file named `index.js` and place your JavaScript code inside it:

```js
// index.js
// This is my first JavaScript code!
console.log('Hello World');
```

### Step 2: Reference `index.js` in `index.html`

In `index.html`, cut the inline code out of the `<script>` tag. Then, use the `src` attribute (short for **source**) to tell the browser where your JavaScript file is located:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Document</title>
</head>
<body>
  <h1>Hello World</h1>

  <!-- Reference external script via src attribute -->
  <script src="index.js"></script>
</body>
</html>
```

### Step 3: Verify in browser DevTools

When you open `index.html` in a browser (e.g. using Live Server at `http://127.0.0.1:5500/index.html`) and open Chrome Developer Tools (**Inspect** -> **Console**), you will see:

```text
Hello World        index.js:2
```

Notice that the DevTools console explicitly attributes the log to `index.js:2`, confirming that the browser successfully downloaded and executed the external JavaScript file.

## Related concepts

- [What is JavaScript](./what-is-javascript.md)
- [Setting up the Development Environment](./setting-up-the-development-environment.md)
- [JavaScript in Browsers](./javascript-in-browsers.md)
- [JavaScript in Node](./javascript-in-node.md)

