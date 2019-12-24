# 依赖管理

JSBox 内置了对 [npm](https://www.npmjs.com/) 仓库的支持，这意味着你可以直接在应用内完成 node modules 的安装。

当然，也可以在桌面端完成 node_modules 的配置，并将项目运行到设备上。

# 安装 Node.js 模块

- 打开项目目录
- 点击左上角 Node 图标
- 安装 Node.js 模块
- 输入模块名，可以使用 `,` 分割多个模块，可以通过 `@version` 来指定版本号

# package.json

你可以使用项目路径下的 `package.json` 文件来管理依赖，例如：

```json
{
  "dependencies": {
    "uuid": "*",
    "lodash": "*"
  }
}
```