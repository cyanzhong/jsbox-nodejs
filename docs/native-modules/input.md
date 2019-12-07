# 用户输入

在 Node 环境你可以使用 `stdin` 和 `stdout` 来处理输入输出，但正如我们之前提到的那样，由于一些限制，你需要使用：

- `$jsbox.stdin` 替代 `process.stdin`
- `$jsbox.stdout` 替代 `process.stdout`

除此之外，你可以用自己已有的 Node.js 知识来用他们，正如这个程序：

```js
const readline = require("readline");

const interface = readline.createInterface({
  input: $jsbox.stdin,
  output: $jsbox.stdout,
  terminal: false
});

interface.on('line', line => {
  console.log(`Echo: ${line}`);
});
```

这是一个 Echo 程序，用户输入什么，程序就输出什么。

# module: "input"

除此之外，你还可以使用 JSBox 内建的 `input` 模块来获得用户输入。

# input.text(object) -> Promise

使用 JSBox 原生组件输入文字内容：

```js
const input = require("input");
input.text({
  type: 0,
  placeholder: "Input your name..",
  text: "Ying"
}).then(text => {
  console.log(text);
});
```

其中 `placeholder` 和 `text` 分别指定了占位符和当前的文字，`type` 则指定了键盘类型，所有参数均可缺省。

`type` 可以参考：https://docs.xteko.com/#/data/constant?id=kbtype

函数返回一个 Promise 对象，你也可以使用 async/await 的方式调用。

# input.speech(object) -> Promise

使用 iOS 内建的语音识别来输入文字：

```js
const input = require("input");
input.speech({
  locale: "en-US",
  autoFinish: true
}).then(text => {
  console.log(text);
});
```

其中 `autoFinish` 表示是否在用户说完之后自动完成，默认为 `false`。`locale` 参数则指定语音的地区，默认为设备的地区。