# JSBox -> Node

On the opposite of calling JSBox from Node, sometimes you want to call Node from JSBox. This will be frequently used as well, such as using an npm module in JSBox code.

# $nodejs.run(object)

This is a mirror of `$jsbox.run()`, running in JSBox script. You can run Node code in the same way:

```js
$nodejs.run(`
  const request = require('request');
  request('http://www.google.com', function (error, response, body) {
    console.error('error:', error); // Print the error if one occurred
    console.log('statusCode:', response && response.statusCode); // Print the response status code if a response was received
    console.log('body:', body); // Print the HTML for the Google homepage.
  });
  `
);
```

For installing node modules, tap the debug button in the project explorer, such as `request` in the above example.

You can specify some details as well:

```js
$nodejs.run({
  name: "MyNodeModule",
  // script: "",
  // path: "",
  query: {
    k1: "v1",
    k2: "v2"
  },
  // argv: [],
  listener: {
    id: "eventId",
    handler: result => {
      console.log("Message from Node: ", result);
    }
  }
});
```

Specify which script with `name`, `script` or `path`, and listen to notifications just like how `$jsbox.run` works.

The parameters you specified with `query` can be retrieved like this:

```js
const query = $context.query;
```

As an alternative, you can also pass `argv` to the Node `process.argv`.

In order to observe notifications, we can register a `listener` in JSBox code. Node script can notify the `handler` with `id`:

```js
$jsbox.notify("eventId", {
  k1: "v1",
  k2: "v2"
});
```

The handler in the JSBox code will be called, and it prints the result. As you can see, `$nodejs.run/notify` and `$jsbox.run/notify` are paired, they will be used together to complete message dispatching.

# $nodejs.listen(string, Function)

Listen notifications from Node.js runtime:

```js
$nodejs.listen("eventId", () => {

});
```

Node.js can send message to above observers with `$jsbox.notify(...)`.

# $nodejs.version

Returns the current Node.js version.

# $nodejs.path

Returns the current Node.js paths.