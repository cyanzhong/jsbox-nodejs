# Node -> Objective-C

Literally, this is not new, just a kind reminder. Sometimes, you cannot achieve your goal even using JSBox APIs.

In that case, think about Objective-C Runtime. You can take look at this: https://docs.xteko.com/#/en/runtime/intro

Here is a simple example:

```js
$jsbox.run(`
  const url = $objc("NSURL").$URLWithString("https://google.com");
  $objc("UIApplication").$sharedApplication().$openURL(url);`
);
```

It opens a URL with Objective-C code. Of course, we don't encourage using it all the time, but just in case for some workarounds.