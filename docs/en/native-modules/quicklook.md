# module: "quicklook"

`quicklook` module provides some APIs to leverage the iOS QuickLook.

# quicklook.text(string) -> Promise

Open a text with the quicklook component:

```js
const quicklook = require("quicklook");
quicklook.text("Hey");
```

# quicklook.file(File) -> Promise

Open a File with the quicklook component:

```js
const quicklook = require("quicklook");
quicklook.file({
  name: "demo.txt",
  data: buffer
});
```

# quicklook.files([File]) -> Promise

Open a list of Files with the quicklook component:

```js
const quicklook = require("quicklook");
quicklook.files([
  {
    name: "demo.txt",
    data: buffer
  }
]);
```

You can navigate files by swiping left and right.

# quicklook.json(JSON) -> Promise

Open a JSON object with the JSBox built-in JSON viewer:

```js
const quicklook = require("quicklook");
quicklook.json({
  "Key": "Value"
});
```

# quicklook.html(string) -> Promise

Open an HTML with the quicklook component:

```js
const quicklook = require("quicklook");
quicklook.html("<h1>Hey, there!<h1>");
```

# quicklook.markdown(string) -> Promise

Open a markdown text with the quicklook component:

```js
const quicklook = require("quicklook");
quicklook.markdown("**Bold** text");
```