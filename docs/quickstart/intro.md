# Node.js 官方文档

在阅读本文档之前，请确保您对 [Node.js](https://nodejs.org) 已经有一定的了解，本文档也不会提供 Node.js 官方文档提供的内容。

目前 JSBox 的运行时基于 `Node.js v10.13.0`, 相关的文档可以在这里找到：https://nodejs.org/docs/latest-v10.x/api/

本文档会着重介绍 JSBox 内置的 Node 环境有哪些差异，以及在移动平台上面使用 Node 时会碰到的问题。

# 如何在 JSBox 使用 Node.js

- 可以使用 JSBox 提供的 REPL 运行简单的代码
- 可以在 JSBox 内新建一个 Node.js 模块，运行即可
- 可以使用我们提供的 [VS Code 插件](https://marketplace.visualstudio.com/items?itemName=Ying.jsbox) 来将项目运行到 iOS 设备上

# 平台差异

由于移动平台和 iOS 平台的限制，JSBox 提供的 Node 环境有如下差异：

- `process.cwd()` 返回的是当前运行模块的根目录
- 执行 `process.exit()` 之后，会退出当前运行的模块
- `process.stdin` 和 `process.stdout` 需要使用 `$jsbox.stdin` 和 `$jsbox.stdout` 来替代
- 无法使用 `child_process` 模块相关的功能，例如 `spawn`
- 由于 intl 的限制，调试功能目前无法使用
- JSBox 目前不具备后台运行的权限，这一个限制也同样作用于 Node.js 运行时
- Node 运行时消耗过多内存，目前 JSBox 仅允许其在主应用运行，目前我们正在改进