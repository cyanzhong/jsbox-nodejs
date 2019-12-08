# module: "motion"

`motion` 模块提供了传感器相关的接口。

# motion.available()

检查当前设备是否支持相关的传感器：

```js
const motion = require("motion");
if (motion.available()) {
  
}
```

# motion.startUpdates(object)

监听数据变化：

```js
const motion = require("motion");
motion.startUpdates({
  interval: 2,
  handler: resp => {
    console.log(resp);
  }
})
```

返回的数据请参考 [CMDeviceMotion](https://developer.apple.com/documentation/coremotion/cmdevicemotion)。

# motion.stopUpdates()

停止更新数据：

```js
const motion = require("motion");
motion.stopUpdates();
```