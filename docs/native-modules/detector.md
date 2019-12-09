# module: "detector"

`detector` 提供了一套检测数据的机制。

# detector.dates(string)

将文本中所有的日期提取出来：

```js
const detector = require("detector");
const dates = detector.dates("2017年10月10日");
```

# detector.date(string)

获取文本中的第一个日期。

# detector.addresses(string)

将文本中所有的地址提取出来：

```js
const detector = require("detector");
const addresses = detector.addresses("");
```

# detector.address(string)

获取文本中的第一个地址。

# detector.links(string)

将文本中所有的链接提取出来：

```js
const detector = require("detector");
const links = detector.links("http://apple.com hello http://xteko.com");
```

# detector.link(string)

获取文本中的第一个链接。

# detector.phoneNumbers(string)

将文本中所有的电话号码提取出来：

```js
const detector = require("detector");
const phoneNumbers = detector.phoneNumbers("18666666666 hello 18777777777");
```

# detector.phoneNumber(string)

获取文本中的第一个电话号码。