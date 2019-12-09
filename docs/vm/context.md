# $context

我们常常需要传递一些参数给脚本，这些参数可以通过 `$context` 对象获取。

# $context.query

我们通过 URL scheme 方式运行脚本时，或者通过 `$nodejs.run(...)` 运行脚本时，参数可以这样获取：

```js
const query = $context.query;
```

# $context.text/image/link/safari

当我们在 share sheet 运行脚本时，可以通过这些方法来获取传递给脚本的数据：

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

通过 share sheet 运行 Node 脚本时，将会自动打开应用来运行，你可以通过上述方法获取相应的数据。