# module: "drive"

`drive` module provides support for the iCloud Drive.

# drive.save(File) -> Promise

Save a File to the iCloud Drive:

```js
const drive = require("drive");
drive.save(buffer).then(path => {
  console.log(path);
})
```

The return value is the file path.

# drive.open() -> Promise

Open an iCloud Drive file using the built-in file picker:

```js
const drive = require("drive");
drive.open({
  type: ["public.data", "public.content"]
}).then(buffer => {
  console.log(buffer);
});
```

You can specify MIME with `type`, by default, it loads all files.