# 当前路径

Node 模块运行起来之后，当前路径指向的是正在运行模块的根目录：

```js
// The running module's root
console.log(process.cwd());

const fs = require("fs");
fs.writeFileSync("test.txt", "Hello, World!");
```

上面的代码会在模块根目录创建一个文本文件，内容是 "Hello, World!"。

# HOME

可以这样获取 JSBox 的文件根目录：

```js
const fs = require("fs");
const path = require("path");
const home = process.env["HOME"];

fs.writeFileSync(path.join(home, "tmp/test.txt"), "Hello, World!");
```

上面的代码会在 JSBox 的 `tmp` 目录创建一个文本文件，内容是 "Hello, World!"。当你操作 HOME 的时候，请明确地知道自己在做什么，否则可能会删除一些应用需要的文件。

# 其他目录

JSBox 有一些其他目录，如果你希望通过 Node 去读写他们，可以通过下面的方式获取：

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

请注意，上面的文件路径包含了一些对 JSBox 运行极为重要的文件，如果误删了其中的一些，可能会导致应用不能正常运行。所以，请再三确认自己正在做的事情。

另外，HOME 目录其中的一些子目录只具有只读权限，不能被写入。