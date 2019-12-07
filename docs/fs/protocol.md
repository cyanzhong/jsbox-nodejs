# 文件协议

在 Node 与 iOS 原生接口通信的过程中，文件是很常见的一种数据。例如读取照片、获取 iCloud Drive 文件等。

为了让这个过程更方便，我们设计了一个格式，用于从 Node 模块传递一个文件给 Native。

在之后关于 Native 模块的介绍里面，我们都用 `File` 来指代这种数据类型。

`File` 可以是三种类型，下面使用 `quicklook` 模块来讲解。

# 文件路径

如果使用磁盘上的文件，可以直接用它的路径来表示：

```js
const ql = require("quicklook");
ql.file("test.txt");
```

这将使用 iOS 的快速预览功能打开项目路径下的 `test.txt` 文件。

# Buffer 对象

文件也可以是 Node.js 的一个 [Buffer](https://nodejs.org/api/buffer.html) 对象：

```js
const ql = require("quicklook");
const buffer = Buffer.from("I'm a string!", "utf-8");
ql.file(buffer);
```

# 包含名字的 Buffer

在很多时候你需要为文件起一个名字，这种情况可以使用：

```js
const fs = require("fs");
const ql = require("quicklook");
const buffer = fs.readFileSync("image.png");
ql.file({
  name: "image.png",
  data: buffer
});
```

在 Node 模块里面，我们可以通过上述方式传递文件给 Native 模块，然后获取到 `Buffer` 或`路径`等文件，可以在 Node 代码里面将他们进行转换。