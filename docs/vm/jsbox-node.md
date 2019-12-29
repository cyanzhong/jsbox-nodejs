# JSBox 调用 Node

与 Node 调用 JSBox 相反的是，有时候你会希望在 JSBox 脚本里面调用 Node。这也是一个常见的需求，例如你希望在 JSBox 里面使用一个 npm 模块。

# $nodejs.run(object)

这是一个与 `$jsbox.run()` 相对应的函数，运行在 JSBox 脚本里面。一样，你可以直接填写 Node 脚本：

```js
$nodejs.run(`
  const request = require('request');
  request('http://www.google.com', function (error, response, body) {
    console.error('error:', error); // Print the error if one occurred
    console.log('statusCode:', response && response.statusCode); // Print the response status code if a response was received
    console.log('body:', body); // Print the HTML for the Google homepage.
  });
  `
);
```

你可以点击项目管理器左上角的调试图标，来安装对应的 Node 模块，例如这个例子里面的 `request` 模块。

同样的，JSBox 调用 Node 也支持指定更详细的参数：

```js
$nodejs.run({
  name: "MyNodeModule",
  // script: "",
  // path: "",
  query: {
    k1: "v1",
    k2: "v2"
  },
  // argv: [],
  listener: {
    id: "eventId",
    handler: result => {
      console.log("Message from Node: ", result);
    }
  }
});
```

可以通过 `name`, `script` 或 `path` 来指定需要运行的 Node 脚本，并且监听消息的方式和 `$jsbox.run` 也完全一样。

通过 `query` 传递的参数，在 Node 脚本里面可以这样获取：

```js
const query = $context.query;
```

也可以通过 `argv` 参数将参数传递给 Node 的 `process.argv` 变量。

为了获取 Node 脚本的消息，可以通过 `listener` 来监听，该 Node 脚本可以通过 `id` 来将消息派发到 `handler` 函数：

```js
$jsbox.notify("eventId", {
  k1: "v1",
  k2: "v2"
});
```

这个时候 JSBox 程序中的 handler 会被调用，并打印出从 Node 获得的结果。可以看出，`$nodejs.run/notify` 和 `$jsbox.run/notify` 是两两对应的，共同完成两个环境的互相调用。

# $nodejs.listen(string, Function)

监听来自 Node.js 环境的消息：

```js
$nodejs.listen("eventId", () => {

});
```

同样的，Node.js 环境可以通过 `$jsbox.notify(...)` 将消息传递给上述监听者。

# $nodejs.version

获取当前 Node.js 的版本。

# $nodejs.path

获取当前 Node.js 相关的路径。