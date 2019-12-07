# module: "photo"

`photo` 模块提供照片相关的接口。

# photo.take() -> Promise

使用系统相机拍摄照片：

```js
const photo = require("photo");
photo.take().then(result => {
  const buffer = result.data;
  const metadata = result.metadata;
});
```

返回 Buffer 类型的数据，以及 JSON 结构的 metadata。

# photo.pick(object) -> Promise

使用系统相册选取照片：

```js
const photo = require("photo");
photo.take({
  multi: true
}).then(result => {
  const buffer = result.data;
  const metadata = result.metadata;
});
```

`multi` 表示是否需要选择多张照片。

# photo.scan() -> Promise

使用系统内建的文档扫描功能扫描文档：

```js
const photo = require("photo");
photo.scan().then(files => {
  console.log(files);
});
```

支持同时扫描多张图片，返回的数据是 Buffer 的一个数组。

# photo.save(File) -> Promise

将 File 格式的照片保存到相册：

```js
const photo = require("photo");
photo.save(buffer).then(success => {
  console.log(success);
});
```

# photo.fetch(object) -> Promise

读取系统相册：

```js
const photo = require("photo");
photo.fetch({
  count: 10,
  type: 0,
  subType: 0
}).then(files => {
  console.log(files);
});
```

其中 `type` 和 `subType` 指定了读取的类型，请参考：https://docs.xteko.com/#/data/constant?id=assetmedia

# photo.delete(object) -> Promise

删除系统相册的内容：

```js
const photo = require("photo");
photo.delete({
  count: 10,
  type: 0,
  subType: 0
}).then(success => {
  console.log(success);
});
```

参数类型与 `photo.fetch(...)` 一致，返回是否成功。