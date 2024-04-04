# Deep Dive into Undici

## Why Undici?
Node.js core http/https is a mess. It uses the same API for
- Client & Server
- Ties the connection pooling with the public API
- Cannot support both HTTP 1 and 2 without
- Changing it will break Express

##  Why undici.fetch
- Be spec compliant
- Use WHATWG streams, so the code using fetch() could be isomorphic
- Separate the protocol from the API
- HTTP/2 support
- HTTP/1.1 pipelining

## Undici speed
undici - request is *really* fast

## HTTP/1.1 pipelining
Sending two requests with eachother but there are gotchas...

## Mocking requests
undici can mock requests because of its software design

## Checkout: undici-oidc-interceptor
But interceptors are being replaced in the next version of undici

## Why is fetch() slow?
- 50% of the time is spent initializing WHATWG streams
- It's because they are transferrable (worth its own talk)

## Can do networkless http requests
- That's how fastify.inject() works, using fastify-undici-dispatch
