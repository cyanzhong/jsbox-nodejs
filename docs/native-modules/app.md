# module: "app"

`app` 模块封装了和应用相关的一些函数。

# app.openURL(string)

使用系统内置的机制打开一个 URL。如果是一个网页，将会被 Safari 打开，如果是一个 URL scheme，则将会打开对应的功能：

```js
const app = require("app");

// Open a website
app.openURL("https://apple.com");

// Open a URL scheme
app.openURL("twitter://user?id=734056753571241989");
```

其返回值表示该 URL 是否被成功打开。