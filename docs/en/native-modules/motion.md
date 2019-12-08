# module: "motion"

`motion` module provides APIs for device sensors.

# motion.available()

Check whether the device supports motion sensors:

```js
const motion = require("motion");
if (motion.available()) {

}
```

# motion.startUpdates(object)

Start tracking motion updates:

```js
const motion = require("motion");
motion.startUpdates({
  interval: 2,
  handler: resp => {
    console.log(resp);
  }
})
```

For details, refer to [CMDeviceMotion](https://developer.apple.com/documentation/coremotion/cmdevicemotion)。

# motion.stopUpdates()

Stop motion updates:

```js
const motion = require("motion");
motion.stopUpdates();
```