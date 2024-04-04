# The State of Node Compatibility in Deno

## Differences from Node.js
1. TypeScript support
2. Deno prompts for access to machine resources like the file system or network.
3. Linter, and test runner and assertion libraries provided by default.
4. `deno compile index.ts` creates an no-dependency executable.

## Compatibility with Node.js
1. ESM only (no commonjs support)
2. No `process` global in Deno. It must be imported `node:process`
3. Use local node_modules or install directly from npm `npm:express`
