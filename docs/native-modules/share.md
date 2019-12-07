# module: "share"

`share` 模块提供了对 iOS 内建 share sheet 的支持，可以用来分享文件或图片等。

# share.text(string) -> Promise

使用 share sheet 分享文本：

```js
const share = require("share");
share.text("Hey");
```

# share.texts([string]) -> Promise

使用 share sheet 分享一组文本：

```js
const share = require("share");
share.texts(["Hey", "Hey", "Hey"]);
```

# share.file(File) -> Promise

使用 share sheet 分享 File 格式的文件：

```js
const share = require("share");
share.file({
  name: "demo.png",
  data: buffer
});
```

# share.files([File]) -> Promise

使用 share sheet 分享一组 File 格式的文件：

```js
const share = require("share");
share.files([
  {
    name: "demo.png",
    data: buffer
  }
]);
```

# share.url(string) -> Promise

使用 share sheet 分享链接：

```js
const share = require("share");
share.url("https://apple.com");
```