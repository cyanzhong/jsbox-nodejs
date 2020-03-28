# module: "addin"

`addin` 模块封装了管理本地脚本的一些方法。

# addin.list()

获取设备上所有的本地脚本：

```js
const addin = require("addin");
const list = addin.list();
console.log(list[0]);
// name, url, version, icon, summary, author, website...
```

# addin.categories()

获取设备上所有的脚本分类：

```js
const addin = require("addin");
const categories = addin.categories();
console.log(categories);
// [string]
```

# addin.current()

获取当前正在运行的脚本：

```js
const addin = require("addin");
const current = addin.current();
// name, url, version, icon, summary, author, website...
```

# addin.save(object)

保存一个脚本：

```js
const addin = require("addin");
addin.save({
  name: "Node Module",
  file: "downloaded/package.zip",
  // url, version, icon, summary, author, website
});
```

其中 `name` 和 `file` 为必填字段，`file` 为 `File` 格式的 zip 文件。

# addin.delete(string)

使用脚本名删除一个脚本：

```js
const addin = require("addin");
addin.delete("Node Module");
```

# addin.run(object)

运行另一个脚本：

```js
const addin = require("addin");
addin.run("Node Module");
```

也可以指定运行时的输入参数：

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

被运行的脚本可以通过 `$context.query` 获得输入参数。

# addin.restart()

重新运行当前的脚本：

```js
const addin = require("addin");
addin.restart();
```