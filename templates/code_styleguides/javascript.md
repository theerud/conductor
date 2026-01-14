# Neostandard JavaScript Style Summary

This aligns with the `neostandard` ESLint preset (Standard.js successor). Defaults are “no semicolons”, ES modules, and JSX support included.

## Source files
- File names lowercase with underscores or dashes; `.js` extension; UTF-8; indent with spaces (ASCII 0x20).
- Prefer ES modules for all new code.

## Formatting
- 2-space indentation; tabs forbidden. One blank line between top-level blocks; no trailing whitespace.
- Brace style 1TBS; braces required for multi-line blocks, single-line control statements may omit braces.
- No semicolons (ASI allowed).
- Single quotes preferred; template literals for interpolation/multi-line. Object literals use spaced braces (`{ foo: 1 }`). Space before function parens.
- Trailing commas are not enforced (comma-dangle is ignored/warn). No hard column limit.

## Modules, imports, exports
- ES modules (`import`/`export`). Default exports are allowed. Imports/exports must not duplicate names; no absolute paths without config.
- JSX output: components in `PascalCase`, boolean props shorthand (`<Comp disabled />`), fragment shorthand (`<>...</>`), keys on list/fragment items, no duplicate props, avoid `target="_blank"` without `rel` handling. Prefer single quotes in JSX, self-close empty tags, wrap multi-line JSX in parens, align closing tags/brackets, 2-space indent for JSX props.

## Language features
- Prefer `const`; `let` when reassignment is needed. `var` discouraged (`no-var` warns). Use shorthand properties.
- Equality: `===`/`!==` required. Avoid unused vars (`no-unused-vars` errors, but ignores unused args).
- Style allows getter/setter syntax, arrow functions, and class fields. No rules against `this` usage beyond standard errors.

## Naming
- Classes: `UpperCamelCase`; functions/methods/variables: `lowerCamelCase`; constants: `CONSTANT_CASE`.

## Disallowed/problematic patterns
- `with`, `eval()`/`new Function`, extending built-ins, duplicate definitions, shadowing restricted names, unused expressions without intent, unreachable code, and most unsafe constructs are errors.
- Node-specific pitfalls flagged (deprecated APIs, callback errors, path concat). Many are `error`, `n/no-deprecated-api` is `warn`.

## Comments and docs
- JSDoc recommended for public classes, methods, and exports; not enforced by neostandard. Use `@param`, `@returns`, `@deprecated`, `@override` as needed. Keep line comments spaced (`// comment`). Type annotations are enclosed in braces (e.g., `/** @param {string} userName */`).
