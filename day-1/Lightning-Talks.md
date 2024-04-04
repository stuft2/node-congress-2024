# Managing Large-Scale Node.js Projects with Monorepos
> by Fortune Ikechi

1. Atomic Commits: Making small, atomic commits that encapsulate a single change or feature. This practice enhances claritya nd eases the process of code reviews and debugging.
2. Automated Testings: Run the test suite on new pull requests.
3. Parallel Testing: Run tests on multiple runners.
4. PR Guidelines: Establish clear guidelines for contributing.
5. Use GitHub CODEOWNERS

# Understanding Package Resolution in Node.js
> by Yagiz Nizipli

## Commonjs vs ESM
- Commonjs uses require without file extension.
- ESM uses import which returns a promise and requires the file extension.

## Module Resolution
- Looks at `type` in package.json
- Check if --experimental-detect-module exists
- Fallback to commonjs

## Node Module Resolution
- node_modules will default to `type` in *their* package.json
- fallback to parent `type`

For scripts:
- Create a package.json with `type` field
- Use `.mjs` or `.cjs`
- Use `--experimental-detect-module`

## Tips
- Always use file extensions in `import` **AND** `require` calls
