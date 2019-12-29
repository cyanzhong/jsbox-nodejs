# Node 调用 JSBox

正如我们之前提到的那样，目前 Node 运行时并没有提供像 JSBox 运行时那样丰富的 Native 接口，所以当你想实现一个和 iOS 原生有关的功能却发现没有相关的 Node 模块，你可以调用 JSBox。

# $jsbox.run(object)

可以通过下面的方式来简单的运行一个 JSBox 脚本：

```js
$jsbox.run(`
  $ui.render({
    views: [
      {
        type: "label",
        props: {
          text: "Hey"
        },
        layout: (make, view) => {
          make.center.equalTo(view.super);
        }
      }
    ]
  });`
);
```

也就是说，传入一个字符串时，该字符串被当做 JSBox 脚本直接运行。

也可以对运行方式进行更详细的指定：

```js
$jsbox.run({
  name: "MyApp",
  // script: "",
  query: {
    k1: "v1",
    k2: "v2"
  },
  listener: {
    id: "eventId",
    handler: result => {
      console.log("Message from JSBox: ", result);
    }
  }
});
```

可以通过 `name` 指定 JSBox 脚本名，或者 `script` 指定直接运行的脚本内容。并且可以通过 `query` 传递参数给要运行的脚本，该 JSBox 脚本可以这样拿到参数：

```js
const query = $context.query;
```

为了获取 JSBox 脚本的消息，可以通过 `listener` 来监听，该 JSBox 脚本可以通过 `id` 来将消息派发到 `handler` 函数：

```js
$nodejs.notify("eventId", {
  k1: "v1",
  k2: "v2"
});
```

这个时候 Node 程序中的 handler 会被调用，并打印出从 JSBox 获得的结果。

# $jsbox.listen(string, Function)

监听来自 JSBox 环境的消息：

```js
$jsbox.listen("eventId", () => {

});
```

同样的，JSBox 环境可以通过 `$nodejs.notify(...)` 将消息传递给上述监听者。

# $jsbox.version

获取当前 JSBox 的版本。

# $jsbox.path

获取当前 JSBox 相关的路径。