# module: "detector"

`detector` provides some data detection methods.

# detector.dates(string)

Retrieve all dates from a string:

```js
const detector = require("detector");
const dates = detector.dates("2017/10/10");
```

# detector.date(string)

Retrieve the first date from a string.

# detector.addresses(string)

Retrieve all addresses from a string:

```js
const detector = require("detector");
const addresses = detector.addresses("");
```

# detector.address(string)

Retrieve the first address from a string.

# detector.links(string)

Retrieve all links from a string:

```js
const detector = require("detector");
const links = detector.links("http://apple.com hello http://xteko.com");
```

# detector.link(string)

Retrieve the first link from a string.

# detector.phoneNumbers(string)

Retrieve all phone numbers from a string:

```js
const detector = require("detector");
const phoneNumbers = detector.phoneNumbers("18666666666 hello 18777777777");
```

# detector.phoneNumber(string)

Retrieve the first phone number from a string.