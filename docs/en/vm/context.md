# $context

Sometimes, we want to pass parameters to a Node script, those parameters can be retrieved with the `$context` object.

# $context.query

If a script is invoked with URL scheme, or `$nodejs.run(...)`, it can be accessed like:

```js
const query = $context.query;
```

# $context.text/image/link/safari

If we run a Node script via share sheet, the shared data can be found with:

```js
// Get the first text
const text = $context.text;
// Get all text items
const textItems = $context.textItems;
// Get the first image
const image = $context.image;
// Get all image items
const imageItems = $context.imageItems;
// Get the first link
const link = $context.link;
// Get all link items
const linkItems = $context.linkItems;
// Get parameters from Safari sharing
const safariParameters = $context.safari;
// Get all items from share sheet
const allItems = $context.allItems;
```

It opens the main app directly, and you retrieve the shared data with the above methods.