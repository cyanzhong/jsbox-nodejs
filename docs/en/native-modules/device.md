# module: "device"

`device` provides some device APIs.

# device.info()

Returns the device information:

```js
const device = require("device");
const info = device.info();
```

Sample result:

```json
{
  "model": "string",
  "language": "string",
  "version": "string",
  "name": "cyan's iPhone",
  "screen": {
    "width": 240,
    "height": 320,
    "scale": 2.0,
    "orientation": 1,
  }
}
```

# device.isDarkMode()

Detect whether the device is using dark mode:

```js
const device = require("device");
if (device.isDarkMode()) {

}
```

# device.isXXX()

Detect the device type quickly:

```js
const device = require("device");
const isIphoneX = device.isIphoneX();
const isIphonePlus = device.isIphonePlus();
const isIpad = device.isIpad();
const isIpadPro = device.isIpadPro();
```

# device.space()

Detect the device memory/disk space:

```js
const device = require("device");
const space = device.space();
```

Sample result:

```json
{
  "disk": {
    "free": {
      "bytes": 87409733632,
      "string": "87.41 GB"
    },
    "total": {
      "bytes": 127989493760,
      "string": "127.99 GB"
    }
  },
  "memory": {
    "free": {
      "bytes": 217907200,
      "string": "207.8 MB"
    },
    "total": {
      "bytes": 3221225472,
      "string": "3 GB"
    }
  }
}
```

# device.ssid()

Get the current Wi-Fi SSID:

```js
const device = require("device");
const ssid = device.ssid();
```

Sample result:

```json
{
  "SSIDDATA": {},
  "BSSID": "aa:bb:cc:dd:ee:ff",
  "SSID": "SSID"
}
```

Note: In iOS 13 and above, this API needs location access, you can use `$location` APIs to request the access.

# device.networkType()

Get the current network type:

```js
const device = require("device");
const networkType = device.networkType();
```

Value | Type
---|---
0 | None
1 | Wi-Fi
2 | Cellular

# device.wlanAddress()

Get the current wlan address:

```js
const device = require("device");
const address = device.wlanAddress();
```

# device.hasTouchID()

Check if the device supports Touch ID:

```js
const device = require("device");
const hasTouchID = device.hasTouchID();
```

# device.hasFaceID()

Check if the device supports Face ID:

```js
const device = require("device");
const hasFaceID = device.hasFaceID();
```

# device.taptic(number)

Trigger a taptic feedback if supported:

```js
const device = require("device");
device.taptic(0);
```

Param | Type | Description
---|---|---
level | number | 0 ~ 2

# device.isJailbroken()

Check whether device is jailbroken:

```js
const device = require("device");
const isJailbroken = device.isJailbroken();
```

# device.isVoiceOverOn()

Check whether VoiceOver is running:

```js
const device = require("device");
const isVoiceOverOn = device.isVoiceOverOn();
```