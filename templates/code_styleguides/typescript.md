# Neostandard TypeScript Style Summary

Use `neostandard({ ts: true })` to apply the TypeScript-aware config (Standard.js successor). Defaults are “no semicolons”, ES modules, and JSX support included unless `noJsx: true` is set.

## Source files
- File names lowercase with underscores or dashes; `.ts` (or `.tsx`) extension; UTF-8; indent with spaces (ASCII 0x20).
- Prefer ES modules for all new code.

## Formatting
- 2-space indentation; tabs forbidden. One blank line between top-level blocks; no trailing whitespace.
- Brace style 1TBS; braces required for multi-line blocks, single-line control statements may omit braces.
- No semicolons (ASI allowed).
- Single quotes preferred; template literals for interpolation/multi-line. Object literals use spaced braces. Space before function parens.
- Trailing commas are not enforced; no column limit.

## Modules, imports, exports
- ES modules (`import`/`export`). Default exports are allowed. Import/exports must not duplicate names; no absolute paths without config.
- JSX output: components in `PascalCase`, boolean props shorthand (`<Comp disabled />`), fragment shorthand (`<>...</>`), keys on list/fragment items, no duplicate props, avoid `target="_blank"` without `rel` handling. Prefer single quotes in JSX, self-close empty tags, wrap multi-line JSX in parens, align closing tags/brackets, 2-space indent for JSX props.

## Language features and typing
- Prefer `const`; `let` when reassignment is needed. `var` discouraged (`no-var` warns). Shorthand properties encouraged.
- TypeScript-aware rules replace redundant JS checks; otherwise the JS rule set applies with TS equivalents.
- No built-in ban on `any`, `type assertions`, `non-null assertions`, `const enum`, `{}` types, or optional-vs-`|undefined` choices—use project policy if stricter behavior is desired.
- Equality: `===`/`!==` required. Unused variables error, but unused args are allowed.

## Naming
- Classes/interfaces/types/enums/decorators: `UpperCamelCase`; variables/params/functions/methods/properties: `lowerCamelCase`; constants (including enum values): `CONSTANT_CASE`.

## Disallowed/problematic patterns
- Same as JS baseline: `with`, `eval()`/`new Function`, extending built-ins, duplicate definitions, unsafe/unused code, and common Node pitfalls. `n/no-deprecated-api` is `warn`.

## Comments and docs
- JSDoc recommended for public classes, methods, and exports; not enforced by neostandard. Avoid redundant type tags; use `@param`, `@returns`, `@deprecated`, `@override` where helpful. Keep line comments spaced (`// comment`). Type annotations are enclosed in braces (e.g., `/** @param {string} userName */`).
