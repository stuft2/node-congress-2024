# How to optimize your lambda functions

1. Use cache where possible, especially with the parameter store.
1. Optimize with lambda extensions.
1. Bundle size matters.
  - Minimize your code.
  - Choose your libraries carefully for treeshaking.
1. Use [middy](https://npmjs.com/package/middy)
1. Use Gravaton
