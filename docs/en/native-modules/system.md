# module: "system"

`system` module provides some system-related APIs.

# system.brightness()

Get the current brightness:

```js
const system = require("system");
const brightness = system.brightness();
```

# system.setBrightness(number)

Set the current brightness:

```js
const system = require("system");

// 0 ~ 1
system.setBrightness(0.5);
```

# system.volume()

Get the current volume:

```js
const system = require("system");
const volume = system.volume();
```

# system.setVolume(number)

Set the current volume:

```js
const system = require("system");

// 0 ~ 1
system.setVolume(0.5);
```

# system.call(number)

Make a phone call:

```js
const system = require("system");
system.call("18000000000");
```

# system.sms(number)

Send a text message:

```js
const system = require("system");
system.sms("18000000000");
```

# system.mailto(string)

Send an email:

```js
const system = require("system");
system.mailto("log.e@qq.com");
```

# system.facetime(string)

Initiate a FaceTime session:

```js
const system = require("system");
system.facetime("log.e@qq.com");
```

# system.home()

Returns to the iOS home screen:

```js
const system = require("system");
system.home();
```