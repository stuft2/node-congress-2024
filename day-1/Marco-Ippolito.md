# Creating an HTTP Server from Scratch with node-addon-api

Three libraries we will use:
1. node-addon-api
2. node-gyp
3. bindings

In your package.json file:
```json
{
    "gypfile": true,
    "type": "module",
    "scripts": { ??? }
}
```

Write your source C files.

Create a binding.gyp file which contains the bindings configuration.

You can then import your C exports in your javascript using the bindings library and use it as if it were javascript.

Libuv is a library that abstracts the differences between operating systems
