# module: "qrcode"

`qrcode` module provides some APIs to handle QR Code.

# qrcode.encode(string)

Encode a string to QR Code image:

```js
const qrcode = require("qrcode");
const buffer = qrcode.encode("Hey");
```

# qrcode.decode(File)

Decode a File format QR Code image as string:

```js
const qrcode = require("qrcode");
const text = qrcode.decode(buffer);
```

# qrcode.scan(object) -> Promise

Scan QR Code with the JSBox built-in QR Code scanner:

```js
const qrcode = require("qrcode");
qrcode.scan({
  useFrontCamera: false,
  turnOnFlash: false
}).then(text => {
  console.log(text);
});
```

useFrontCamera: whether to use the front camera，turnOnFlash: whether turn on the flashlight.