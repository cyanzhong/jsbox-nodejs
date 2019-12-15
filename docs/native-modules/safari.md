# module: "safari"

`safari` 模块提供了对 Safari 相关接口的支持。

# safari.open(object) -> Promise

用 Safari View Controller 来打开一个链接：

```js
const safari = require("safari");
safari.open("https://apple.com");
```

也可以指定一些参数：

```js
const safari = require("safari");
safari.open({
  url: "https://apple.com",
  entersReader: true
});
```

其中 `entersReader` 表示是否自动进入阅读模式。

# safari.exec(object)

使用 Safari 自带的 WebKit 内核运行 JavaScript:

```js
const safari = require("safari");
const result = await safari.exec("const a = 100; return a;");
//=> 100
```

也可以通过 `script` 参数运行，并监听 WebKit 环境的通知：

```js
const safari = require("safari");
safari.exec({
  script:
  `
  const a = 100;
  const b = 100;
  $notify("customEvent", {a, b});
  `,
  customEvent: result => {
    console.log(result);
  }
});
```

在 WebKit 环境，可以通过 `$notify(...)` 函数将消息传递回 Node 环境。

# safari.addReadingItem(object)

添加到 Safari 的阅读列表：

```js
const safari = require("safari");
safari.addReadingItem({
  url: "https://apple.com",
  title: "Title",
  preview: "Preview text"
});
```

返回值表示是否添加成功。