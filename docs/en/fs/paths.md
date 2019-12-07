# The current path

After a Node module is launched, the current path points to the current running folder:

```js
// The running module's root
console.log(process.cwd());

const fs = require("fs");
fs.writeFileSync("test.txt", "Hello, World!");
```

The above code creates a text file under its root folder, the content is "Hello, World!".

# HOME

You can get JSBox's root folder like this:

```js
const fs = require("fs");
const path = require("path");
const home = process.env["HOME"];

fs.writeFileSync(path.join(home, "tmp/test.txt"), "Hello, World!");
```

The above example creates a text file under the `tmp` folder, the content is "Hello, World!". When you trying to change files under HOME, please keep your mind clear, you may delete some required files otherwise.

# Other paths

JSBox has some other useful paths, if you want to access them with Node, here is how:

```js
const path = $jsbox.path;

// Equals to process.env["HOME"]
const home = path.home;
// JSBox shared folder
const shared = path.shared;
// Folder that stores scripts
const scripts = path.scripts;
// iCloud Drive folder
const icloud = path.icloud;
// The running module's root
const current = path.current;
```

Note, the above paths may include some very important files, please double-check before taking any action.

Besides, for some folders under HOME, you may only have read access, and cannot make changes.