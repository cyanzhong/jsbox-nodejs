# Node -> JSBox

Like we have just mentioned, Node runtime doesn't support so many APIs like JSBox does. If you want to use a native API which isn't provided you can run JSBox script:

# $jsbox.run(object)

This is the simplest example:

```js
$jsbox.run(`
  $ui.render({
    views: [
      {
        type: "label",
        props: {
          text: "Hey"
        },
        layout: (make, view) => {
          make.center.equalTo(view.super);
        }
      }
    ]
  });`
);
```

That means a string parameter will be executed as the script.

You can also specify some details:

```js
$jsbox.run({
  name: "MyApp",
  // script: "",
  query: {
    k1: "v1",
    k2: "v2"
  },
  listener: {
    id: "eventId",
    handler: result => {
      console.log("Message from JSBox: ", result);
    }
  }
});
```

The `name` parameter specifies its script name, or `script` specifies the script content. Using `query` to pass parameters, JSBox script can retrieve them with:

```js
const query = $context.query;
```

In order to observe notifications, we can register a `listener` in Node code. JSBox script can notify the `handler` with `id`:

```js
$nodejs.notify("eventId", {
  k1: "v1",
  k2: "v2"
});
```

The handler in Node code will be called, and it prints the result.

# $jsbox.listen(string, Function)

Listen notifications from JSBox runtime:

```js
$jsbox.listen("eventId", () => {

});
```

JSBox can send message to above observers with `$nodejs.notify(...)`.

# $jsbox.version

Returns the current JSBox version.

# $jsbox.path

Returns the current JSBox paths.