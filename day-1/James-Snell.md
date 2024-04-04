# Understanding Async Context
```js
const requestId = new AsyncLocalStorage()
```

## The Storage Frame
It's essentially just a map, every instance of AsyncLocalStorage is a key.

```ts
{
  [key: AsyncLocalStorage]: Value
}
```

Storage frames are immutable, so it uses a copy-on-write strategy to make changes.
