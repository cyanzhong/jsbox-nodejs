# module: "share"

`share` module provides support for the iOS share sheet.

# share.text(string) -> Promise

Share a text with the share sheet:

```js
const share = require("share");
share.text("Hey");
```

# share.texts([string]) -> Promise

Share a list of text with the share sheet:

```js
const share = require("share");
share.texts(["Hey", "Hey", "Hey"]);
```

# share.file(File) -> Promise

Share a File with the share sheet:

```js
const share = require("share");
share.file({
  name: "demo.png",
  data: buffer
});
```

# share.files([File]) -> Promise

Share a list of File with the share sheet:

```js
const share = require("share");
share.files([
  {
    name: "demo.png",
    data: buffer
  }
]);
```

# share.url(string) -> Promise

Share a link with the share sheet:

```js
const share = require("share");
share.url("https://apple.com");
```