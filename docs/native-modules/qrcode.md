# module: "qrcode"

`qrcode` 模块提供了二维码相关的一些接口。

# qrcode.encode(string)

将字符串编码为二维码图片：

```js
const qrcode = require("qrcode");
const buffer = qrcode.encode("Hey");
```

# qrcode.decode(File)

将 File 格式的二维码文件解码为字符串：

```js
const qrcode = require("qrcode");
const text = qrcode.decode(buffer);
```

# qrcode.scan(object) -> Promise

使用 JSBox 内建的二维码扫描组件扫描二维码：

```js
const qrcode = require("qrcode");
qrcode.scan({
  useFrontCamera: false,
  turnOnFlash: false
}).then(text => {
  console.log(text);
});
```

useFrontCamera: 是否使用前置摄像头，turnOnFlash: 是否打开闪光灯。