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

# safari.exec(object)

Execute JavaScript using Safari's WebKit core:

```js
const safari = require("safari");
const result = await safari.exec("const a = 100; return a;");
//=> 100
```

You can also use the `script` parameter, and listen to notifications:

```js
const safari = require("safari");
safari.exec({
  script:
  `
  const a = 100;
  const b = 100;
  $notify("customEvent", {a, b});
  `,
  customEvent: result => {
    console.log(result);
  }
});
```

In WebKit environment, messages can be sent back to Node with `$notify(...)`.

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