# module: "ui"

`ui` module provides some UI components.

# ui.success(string, number)

Similar to `toast`, but the bar color is green, indicates success:

```js
const ui = require("ui");
ui.success("Done");
```

# ui.warning(string, number)

Similar to `toast`, but the bar color is yellow, indicates warning:

```js
const ui = require("ui");
ui.warning("Be careful!");
```

# ui.error(string, number)

Similar to `toast`, but the bar color is red, indicates error:

```js
const ui = require("ui");
ui.error("Something went wrong!");
```

# ui.alert(object)

Present an alert, the simplest usage is:

```js
const ui = require("ui");
ui.alert("Hey");
```

You can also use its global alias: `alert(...)`.

When we need to use `title` and `message`:

```js
const ui = require("ui");
ui.alert({
  title: "Title",
  message: "Message"
});
```

By default, alert shows a confirm button, we can customize it with `actions`:

```js
const ui = require("ui");
ui.alert({
  title: "Title",
  message: "Message",
  actions: ["Action 1", "Action 2"]
});
```

# ui.action(object)

Works exactly the same as `ui.alert(...)`, but shows as an action sheet.

# ui.menu(object) -> Promise

Present a menu for choosing an option:

```js
const ui = require("ui");
ui.menu(["A", "B", "C"]).then(option => {
  const index = option.index;
  const title = option.title;
});
```

It can be more descriptive with a `title`:

```js
const ui = require("ui");
ui.menu({
  title: "Options",
  items: ["A", "B", "C"]
}).then(option => {});
```

# ui.toast(string, number)

Present a toast, it will be removed automatically after a delay:

```js
const ui = require("ui");
ui.toast("Hi", 3.0);
```

By default, it lives 2 seconds.

# ui.clearToast()

Clears all toast on the screen:

```js
const ui = require("ui");
ui.clearToast();
```

# ui.showHUD(string)

Show a HUD message:

```js
const ui = require("ui");
ui.showHUD("Loading...");
```

# ui.hideHUD()

Hide HUD message on the screen:

```js
const ui = require("ui");
ui.hideHUD();
```

# ui.showProgress(number, string)

Display a loading progress bar (0 ~ 1):

```js
const ui = require("ui");
ui.showProgress(0.5, "Loading");
```

# ui.hideProgress()

Hide the loading progress bar on the screen:

```js
const ui = require("ui");
ui.hideProgress();
```