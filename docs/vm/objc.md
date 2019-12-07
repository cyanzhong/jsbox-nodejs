# Node 调用 Objective-C

这一节实际上不是新内容，只是一个提醒。有些时候，即便是调用 JSBox 可能也不能实现对应的效果，因为 JSBox 也不可能提供 iOS 原生的全部接口。

但 JSBox 运行时提供了 Runtime 机制，用于调用 Objective-C，具体的文档可以在这里找到：https://docs.xteko.com/#/runtime/intro

这里给出一个简单的样例：

```js
$jsbox.run(`
  const url = $objc("NSURL").$URLWithString("https://google.com");
  $objc("UIApplication").$sharedApplication().$openURL(url);`
);
```

这会通过 Objective-C 的方式来打开一个网页。当然，我们不提倡在任何时候都使用这些技巧，但这些技巧在适合的时候能够成为一种解决方案。