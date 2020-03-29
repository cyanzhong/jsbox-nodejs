# module: "ui"

`ui` 模块目前提了一些简单的 UI 控件，用于完成简单的用户交互。

# ui.alert(object)

展示弹窗，最简单的调用方式可以是：

```js
const ui = require("ui");
ui.alert("Hey");
```

也可以使用其全局的别名：`alert(...)`。

需要指定标题和内容时，可以使用 `title` 和 `message` 参数：

```js
const ui = require("ui");
ui.alert({
  title: "Title",
  message: "Message"
});
```

在默认情况下，alert 会展示一个确认按钮，如果需要指定按钮，可以使用 `actions` 参数：

```js
const ui = require("ui");
ui.alert({
  title: "Title",
  message: "Message",
  actions: ["Action 1", "Action 2"]
});
```

# ui.action(object)

参数与 `ui.alert(...)` 完全一样，但展示方式是弹出 action sheet。

# ui.menu(object) -> Promise

弹出一个选项列表以供用于选择：

```js
const ui = require("ui");
ui.menu(["A", "B", "C"]).then(option => {
  const index = option.index;
  const title = option.title;
});
```

也可以指定 `title` 用于提示用户：

```js
const ui = require("ui");
ui.menu({
  title: "Options",
  items: ["A", "B", "C"]
}).then(option => {});
```

# ui.toast(string, number)

显示一个消息，过一段时间后会自动消失：

```js
const ui = require("ui");
ui.toast("Hi", 3.0);
```

时间参数可以缺省，默认情况下是 2 秒。

# ui.success(string, number)

与 `toast` 类似，但背景色为绿色，以表示成功：

```js
const ui = require("ui");
ui.success("Done");
```

# ui.warning(string, number)

与 `toast` 类似，但背景色为黄色，以表示警告：

```js
const ui = require("ui");
ui.warning("Be careful!");
```

# ui.error(string, number)

与 `toast` 类似，但背景色为红色，以表示错误：

```js
const ui = require("ui");
ui.error("Something went wrong!");
```

# ui.clearToast()

清除屏幕上的 toast 消息：

```js
const ui = require("ui");
ui.clearToast();
```

# ui.showHUD(string)

显示一个 HUD 提示文字：

```js
const ui = require("ui");
ui.showHUD("Loading...");
```

# ui.hideHUD()

隐藏屏幕上的 HUD 提示文字：

```js
const ui = require("ui");
ui.hideHUD();
```

# ui.showProgress(number, string)

在屏幕上显示加载进度条（0 ~ 1）：

```js
const ui = require("ui");
ui.showProgress(0.5, "Loading");
```

# ui.hideProgress()

取消屏幕上的进度条显示：

```js
const ui = require("ui");
ui.hideProgress();
```