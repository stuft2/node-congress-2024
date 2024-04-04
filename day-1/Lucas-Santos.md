# What's New on Node.js Test Runner and WHy it's Game-changing

Works with any assertion library that throws when it encounters a failed assertion:
1. node:assert
2. chai

## Mocks
Mocks are available in node:test, including mock timers and dates.

```js
test(ctx => {
  const mock = ctx.mock.fn()
  ctx.mock.timers.enable({ apis: ['Date'] })
})
```

## Code Coverage

```sh
node --test --experimental-test-coverage \
--test-reporter=lcov \
test.js
```

## TypeScript Support
Importers (aka "loaders") are functions that execute before the module loads.

```sh
node --import=tsx --test test.ts
```

## Other features
- test.skip, todo, only
- File name globbing

## Future features
- module mocking
- Improved test filtering
- More reporters
- Snapshot testing
- Source Map Support
- More mocks

The hope is to outperform jest
