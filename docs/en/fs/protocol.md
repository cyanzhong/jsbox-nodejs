# File protocol

Files are frequently used as a medium when transferring data, such as Photos, iCloud Drive files, etc.

In order to make those operations smoother, we designed a file protocol, it is used to send a file from Node to native.

In the subsequent introduction of the Native module, we will use `File` to refer to this data type.

There are 3 types of `File`, let's explain them with the `quicklook` module.

# File path

If you want to use an existing file on the disk, you can simply use its path:

```js
const ql = require("quicklook");
ql.file("test.txt");
```

This opens the `test.txt` file under the project folder.

# Buffer object

A file could be a Node.js [Buffer](https://nodejs.org/api/buffer.html) as well:

```js
const ql = require("quicklook");
const buffer = Buffer.from("I'm a string!", "utf-8");
ql.file(buffer);
```

# Named Buffer

Sometimes, you may want to specify a name for the file, for instance:

```js
const fs = require("fs");
const ql = require("quicklook");
const buffer = fs.readFileSync("image.png");
ql.file({
  name: "image.png",
  data: buffer
});
```

In a Node module, we can pass files to native using the above ways, and it may return a `Buffer` or `path` as the result, we can handle them in Node code.