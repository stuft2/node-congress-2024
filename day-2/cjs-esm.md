# CommonJS vs ESM, the fight is on!

CommonJS support may be deprecated but will *never* be removed from Node.js.

There's significant pain developing libraries and consuming libraries where publishers need to publish CJS, ESM, and Types. Consumers have to know how to to import ESM and CJS into their projects, which isn't trivial.

Enforcing fields (such as `exports`) in the `package.json` should not come from registries but from Node.js since the implementation resides there. If it came from registries, each registry's enforcement would look different which could cause further confusion.

CommonJS `require` [supports requiring esm](https://joyeecheung.github.io/blog/2024/03/18/require-esm-in-node-js/) synchronously while enabling `--experimental-require-module` (I still haven't been able to get this to work).
