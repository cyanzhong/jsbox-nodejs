# 通信机制

目前 JSBox 提供了两个运行时，分别是 `JSBox 运行时`，和 `Node.js 运行时`，并且提供了让两种运行时互相调用的机制。

两个运行时互相调用，可以取长补短，更容易地完成一些需求，比如说：

- JSBox 脚本可以借助 Node 实现的解决方案
- Node 脚本可以借助 JSBox 强大的 UI 能力
- Node 脚本可以借助 JSBox 调用 Objective-C Runtime

这套机制，与在 JSBox 里的 WebView 运行 JavaScript 类似，本质上是消息传递和事件监听。