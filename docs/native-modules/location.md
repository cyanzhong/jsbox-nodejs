# module: "location"

`location` 模块提供了地理位置相关的接口。

# location.available()

返回当前是否有地理位置的权限：

```js
const location = require("location");
if (location.available()) {

}
```

# location.fetch() -> Promise

获取当前的地理位置：

```js
const location = require("location");
location.fetch().then(result => {
  const latitude = result.lat;
  const longitude = result.lng;
  const altitude = result.alt;
});
```

会同时返回经纬度和海拔。

# location.startUpdates(object)

开始监听位置变化：

```js
const location = require("location");
location.startUpdates({
  once: false
}，result => {
  // lat, lng, alt
});
```

`once` 表示是否只更新一次。

# location.trackHeading(object)

监听 Heading 数据变化：

```js
const location = require("location");
location.trackHeading(result => {
  const magneticHeading = result.magneticHeading;
  const trueHeading = result.trueHeading;
  const headingAccuracy = result.headingAccuracy;
  const x = result.x;
  const y = result.y;
  const z = result.z;
});
```

# location.stopUpdates()

停止地理位置更新：

```js
const location = require("location");
location.stopUpdates();
```

# location.select() -> Promise

在 JSBox 内建的地图组件里面选取一个位置：

```js
const location = require("location");
location.select().then(result => {
  const latitude = result.lat;
  const longitude = result.lng;
});
```