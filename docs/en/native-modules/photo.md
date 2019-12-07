# module: "photo"

`photo` module provides APIs for the iOS Photos app.

# photo.take() -> Promise

Take a photo using the built-in camera:

```js
const photo = require("photo");
photo.take().then(result => {
  const buffer = result.data;
  const metadata = result.metadata;
});
```

It returns a Buffer object photo, and a JSON format metadata.

# photo.pick(object) -> Promise

Select a photo from the iOS photo library:

```js
const photo = require("photo");
photo.take({
  multi: true
}).then(result => {
  const buffer = result.data;
  const metadata = result.metadata;
});
```

`multi` indicates whether multiple-selection is allowed.

# photo.scan() -> Promise

Scan documents using the iOS built-in documents scanner:

```js
const photo = require("photo");
photo.scan().then(files => {
  console.log(files);
});
```

It returns multiple results as a Buffer array.

# photo.save(File) -> Promise

Save a File format photo to the iOS photo library:

```js
const photo = require("photo");
photo.save(buffer).then(success => {
  console.log(success);
});
```

# photo.fetch(object) -> Promise

Fetch photos in the iOS photo library:

```js
const photo = require("photo");
photo.fetch({
  count: 10,
  type: 0,
  subType: 0
}).then(files => {
  console.log(files);
});
```

The `type` and `subType` control fetching types, refer to: https://docs.xteko.com/#/en/data/constant?id=assetmedia

# photo.delete(object) -> Promise

Delete some photos in the iOS photo library:

```js
const photo = require("photo");
photo.delete({
  count: 10,
  type: 0,
  subType: 0
}).then(success => {
  console.log(success);
});
```

The parameters are exactly the same as `photo.fetch(...)`, returns whether it's succeeded.