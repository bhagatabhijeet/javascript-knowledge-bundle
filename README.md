# JavaScript Knowledge Bundle

![JavaScript Programming — the language of the web and beyond](assets/images/javascript-overview.jpg)

*Image courtesy: Gemini 3.8 Flash.*

## Would you care to learn JavaScript — for free?

This bundle attempts to take you from "what even is JavaScript?" to writing objects, loops, async code, and ES modules with confidence — using nothing but the markdown files in this repository. No paywall, no signup, no ads. Just concepts, code you can run, and diagrams for the parts that are easier to see than to read.

## What's inside

10 sections, 50+ concept documents, a 10-question quiz, runnable code snippets, and hand-built diagrams for the ideas that benefit from a picture (the event loop, value vs. reference semantics, the browser rendering pipeline, and more):

1. **[Getting Started](getting-started/)** — what JavaScript actually is, how it runs in browsers vs. Node.js, and setting up your environment.
2. **[Basics](basics/)** — variables, constants, primitive types, dynamic typing, objects, arrays, and functions.
3. **[Operators](operators/)** — arithmetic, assignment, comparison, equality, ternary, logical, and bitwise operators, plus precedence.
4. **[Control Flow](control-flow/)** — if/else, switch, and every loop shape JavaScript offers.
5. **[Objects](objects/)** — 14 concepts from object literals through factory/constructor functions, value vs. reference semantics, cloning, garbage collection, and the built-in `Math`, `String`, and `Date` objects.
6. **[Arrays](arrays/)** — ordered collections and how to search, mutate, and iterate over them.
7. **[Functions](functions/)** — declarations, expressions, getters/setters, and the different shapes a function can take.
8. **[Advanced](advanced/)** — the event loop, promises, `async`/`await`, and ES modules.
9. **[Quiz](quiz/)** — 10 multiple-choice questions with step-by-step explanations.
10. **[Assets](assets/)** — code snippets, exercises, and every diagram used above.

## How to use this bundle

There are two ways to learn from it:

1. **Browse it manually.** Start at [index.md](index.md) and follow the numbered sections in order — each section's own `index.md` links out to its concept files, in the order they build on each other.
2. **Point your LLM at it.** Open this repository in an AI-assisted IDE (VS Code, Antigravity, Cursor, or similar) and ask your assistant questions grounded in these files — e.g. "explain closures using the concepts in this bundle" or "quiz me on operators." The structured frontmatter and cross-linked concepts are designed to give an LLM accurate, scoped context to teach from.

## Under the hood: the OKF format

This bundle is written to the [Open Knowledge Format (OKF) 0.2](https://github.com/GoogleCloudPlatform/knowledge-catalog/blob/main/okf/SPEC.md) — every concept is a markdown file with YAML frontmatter (`id`, `title`, `type`, `description`, `status`, `tags`, and trust/lifecycle fields), which is what lets tools like obviewus import the whole thing as a navigable concept graph rather than just a folder of docs. `index.md` and `log.md` files are excluded from that import so the bundle stays machine-readable end to end.

## Acknowledgments

This bundle was written using <img src="assets/images/icon-vscode.png" width="16" height="16" alt=""> [VS Code](https://code.visualstudio.com/) and <img src="assets/images/icon-antigravity.png" width="16" height="16" alt=""> [Antigravity](https://antigravity.google/), with the help of <img src="assets/images/icon-claude-code.png" width="16" height="16" alt=""> [Claude Code](https://claude.com/claude-code) and Gemini 3.8 Flash — thank you to both for their assistance drafting and organizing this content.
