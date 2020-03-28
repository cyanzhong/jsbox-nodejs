# module: "addin"

`addin` module provides APIs for local script management.

# addin.list()

Get all local scripts:

```js
const addin = require("addin");
const list = addin.list();
console.log(list[0]);
// name, url, version, icon, summary, author, website...
```

# addin.categories()

Get all script categories:

```js
const addin = require("addin");
const categories = addin.categories();
console.log(categories);
// [string]
```

# addin.current()

Get the current running script:

```js
const addin = require("addin");
const current = addin.current();
// name, url, version, icon, summary, author, website...
```

# addin.save(object)

Save a script:

```js
const addin = require("addin");
addin.save({
  name: "Node Module",
  file: "downloaded/package.zip",
  // url, version, icon, summary, author, website
});
```

The `name` and `file` are required, and `file` is a zip file in `File` format.

# addin.delete(string)

Delete a script using its name:

```js
const addin = require("addin");
addin.delete("Node Module");
```

# addin.run(object)

Run another script:

```js
const addin = require("addin");
addin.run("Node Module");
```

You can also specify input parameters:

```js
const addin = require("addin");
addin.run({
  name: "Node Module",
  query: {
    k1: "v1",
    k2: "v2"
  }
});
```

The script that will be executed can retrieve input parameters with `$context.query`.

# addin.restart()

Restart the current running script:

```js
const addin = require("addin");
addin.restart();
```