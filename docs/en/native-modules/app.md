# module: "app"

`app` module provides APIs related to the app.

# app.openURL(string)

Opens a URL using the system built-in mechanism. For websites, it uses Safari. For URL schemes, it opens it directly:

```js
const app = require("app");

// Open a website
app.openURL("https://apple.com");

// Open a URL scheme
app.openURL("twitter://user?id=734056753571241989");
```

The return value indicates whether the action is succeeded.