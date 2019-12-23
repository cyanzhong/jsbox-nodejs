# module: "quicklook"

`quicklook` 模块提供了 iOS 内建的快速预览功能。

# quicklook.text(string) -> Promise

使用预览功能打开一个文本：

```js
const quicklook = require("quicklook");
quicklook.text("Hey");
```

# quicklook.file(File) -> Promise

使用预览功能打开一个文件：

```js
const quicklook = require("quicklook");
quicklook.file({
  name: "demo.txt",
  data: buffer
});
```

# quicklook.files([File]) -> Promise

使用预览功能打开一组文件：

```js
const quicklook = require("quicklook");
quicklook.files([
  {
    name: "demo.txt",
    data: buffer
  }
]);
```

多个文件被打开时，可以左右滑动切换文件。

# quicklook.json(JSON) -> Promise

使用 JSBox 内置的 JSON 查看器预览 JSON:

```js
const quicklook = require("quicklook");
quicklook.json({
  "Key": "Value"
});
```

# quicklook.html(string) -> Promise

使用预览功能打开 HTML 格式文本：

```js
const quicklook = require("quicklook");
quicklook.html("<h1>Hey, there!<h1>");
```

# quicklook.markdown(string) -> Promise

使用预览功能打开 Markdown 格式文本：

```js
const quicklook = require("quicklook");
quicklook.markdown("**Bold** text");
```