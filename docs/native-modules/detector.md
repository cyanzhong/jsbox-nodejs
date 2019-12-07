# module: "detector"

`detector` 提供了一套检测数据的机制。

# detector.date(string)

将文本中所有的日期提取出来：

```js
const detector = require("detector");
const dates = detector.date("2017年10月10日");
```

# detector.address(string)

将文本中所有的地址提取出来：

```js
const detector = require("detector");
const addresses = detector.address("");
```

# detector.link(string)

将文本中所有的链接提取出来：

```js
const detector = require("detector");
const links = detector.link("http://apple.com hello http://xteko.com");
```

# detector.phoneNumber(string)

将文本中所有的电话号码提取出来：

```js
const detector = require("detector");
const phoneNumbers = detector.phoneNumber("18666666666 hello 18777777777");
```