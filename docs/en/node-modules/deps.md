# Dependency management

JSBox has built-in support for the [npm](https://www.npmjs.com/) repository, which means you can resolve your node dependencies without leaving the app.

Of course, you can also set up node_modules on your desktop environment, then sync the code to your device.

# Install Node.js module

- Open your Node.js project
- Tap the "Node.js" button
- Install Node.js module
- Type in the module name, multiple values are separated by `,`, optionally, version can be specified with `@version`

# package.json

You can also manage dependencies using the `package.json` file:

```json
{
  "dependencies": {
    "uuid": "*",
    "lodash": "*"
  }
}
```