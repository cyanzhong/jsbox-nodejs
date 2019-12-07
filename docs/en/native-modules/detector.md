# module: "detector"

`detector` provides some data detection methods.

# detector.date(string)

Retrieve all dates from a string:

```js
const detector = require("detector");
const dates = detector.date("2017/10/10");
```

# detector.address(string)

Retrieve all addresses from a string:

```js
const detector = require("detector");
const addresses = detector.address("");
```

# detector.link(string)

Retrieve all links from a string:

```js
const detector = require("detector");
const links = detector.link("http://apple.com hello http://xteko.com");
```

# detector.phoneNumber(string)

Retrieve all phone numbers from a string:

```js
const detector = require("detector");
const phoneNumbers = detector.phoneNumber("18666666666 hello 18777777777");
```