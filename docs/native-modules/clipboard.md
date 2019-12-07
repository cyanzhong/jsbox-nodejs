# module: "clipboard"

`clipboard` 模块提供了剪贴板相关的接口。

# clipboard.text()

获取剪贴板里的文字：

```js
const clipboard = require("clipboard");
const text = clipboard.text();
```

# clipboard.setText(string)

设置剪贴板里的文字：

```js
const clipboard = require("clipboard");
clipboard.setText("Hey");
```

# clipboard.setTextLocalOnly(string)

设置剪贴板文字到本地，不会触发 iOS 的通用剪贴板同步：

```js
const clipboard = require("clipboard");
clipboard.setTextLocalOnly("Hey");
```

# clipboard.image() -> Buffer

获取剪贴板里的图片：

```js
const clipboard = require("clipboard");
const buffer = clipboard.image();
```

# clipboard.setImage(File)

设置剪贴板里的图片：

```js
const clipboard = require("clipboard");
clipboard.setImage(buffer);
```

# clipboard.clear()

清除剪贴板的全部内容：

```js
const clipboard = require("clipboard");
clipboard.clear();
```