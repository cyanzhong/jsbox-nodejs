# module: "system"

`system` 模块封装了和系统功能相关的一些函数。

# system.brightness()

获取当前设备的亮度：

```js
const system = require("system");
const brightness = system.brightness();
```

# system.setBrightness(number)

设置当前设备的亮度：

```js
const system = require("system");

// 0 ~ 1
system.setBrightness(0.5);
```

# system.volume()

获取当前设备的音量：

```js
const system = require("system");
const volume = system.volume();
```

# system.setVolume(number)

设置当前设备的音量：

```js
const system = require("system");

// 0 ~ 1
system.setVolume(0.5);
```

# system.call(number)

拨打电话：

```js
const system = require("system");
system.call("18000000000");
```

# system.sms(number)

发送短信：

```js
const system = require("system");
system.sms("18000000000");
```

# system.mailto(string)

发送邮件：

```js
const system = require("system");
system.mailto("log.e@qq.com");
```

# system.facetime(string)

进行 FaceTime 通话：

```js
const system = require("system");
system.facetime("log.e@qq.com");
```

# system.home()

返回到系统桌面：

```js
const system = require("system");
system.home();
```