# Template for a library in a monorepo with React + TypeScript + Vite

- `build:site` build the website to `docs`, so it can be served on Github Pages
- `build:lib` build the library to `dist`, where `package.json` is configured to expect it

**NOTE: Make sure to search and replace all instances of `"NEW_LIB"` with the appropriate value for your library**

## TypeScript 7 note

TypeScript 7 (native compiler) ships no JavaScript compiler API yet, which
`typescript-eslint` and `vite-plugin-dts` need. Per the [official guidance](https://devblogs.microsoft.com/typescript/announcing-typescript-7-0/#running-side-by-side-with-typescript-6.0),
the `typescript` package name is aliased to `@typescript/typescript6` (JS API,
`tsc6` binary) and TypeScript 7 is installed as `@typescript/native` (provides the
`tsc` binary). `tsc` in the build scripts therefore runs the native TS 7 compiler.
