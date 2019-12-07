# module: "safari"

`safari` module provides support for Safari.

# safari.open(object) -> Promise

Open a link with Safari View Controller:

```js
const safari = require("safari");
safari.open("https://apple.com");
```

We can also provide some parameters:

```js
const safari = require("safari");
safari.open({
  url: "https://apple.com",
  entersReader: true
});
```

`entersReader` indicates whether to enter reader mode automatically.

# safari.addReadingItem(object)

Add a link as Safari reading item:

```js
const safari = require("safari");
safari.addReadingItem({
  url: "https://apple.com",
  title: "Title",
  preview: "Preview text"
});
```

The return value indicates whether it's succeeded.