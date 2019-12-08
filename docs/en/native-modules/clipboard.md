# module: "clipboard"

`clipboard` module provides clipboard APIs.

# clipboard.text()

Get text in clipboard:

```js
const clipboard = require("clipboard");
const text = clipboard.text();
```

# clipboard.setText(string)

Set text to clipboard:

```js
const clipboard = require("clipboard");
clipboard.setText("Hey");
```

# clipboard.setTextLocalOnly(string)

Set text to local clipboard, it doesn't trigger the "Universal Clipboard" syncing:

```js
const clipboard = require("clipboard");
clipboard.setTextLocalOnly("Hey");
```

# clipboard.image() -> Buffer

Get image in clipboard:

```js
const clipboard = require("clipboard");
const buffer = clipboard.image();
```

# clipboard.setImage(File)

Set image to clipboard:

```js
const clipboard = require("clipboard");
clipboard.setImage(buffer);
```

# clipboard.clear()

Clear all contents in clipboard:

```js
const clipboard = require("clipboard");
clipboard.clear();
```