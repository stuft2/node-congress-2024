# Making My Node.js API Super Fast

1. Use a connection pool
  - Configure it for the environment that will use it. Think about connection pool size.

2. Use Efficient Serialization
  - A synchronous operation that blocks the event loop.
  - [fast-json-stringify](https://npmjs.com/package/fast-json-stringify)
3. Logging
  - Logging will always impact response times
  - Pinojs is the most efficient log library
  - Let the log library build your string templates. Don't do it yourself!
    ```js
    ✔logger.info('Data:', data)
    ❌logger.info(`Data: ${JSON.stringify(data)}`)
    ```
4. Use a modern web server framework
  - Fastify is the fastest web server framework
5. Use caching
