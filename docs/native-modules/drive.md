# module: "drive"

`drive` 模块提供了 iCloud 云盘相关的接口。

# drive.save(File) -> Promise

将 File 格式的文件保存到 iCloud 云盘：

```js
const drive = require("drive");
drive.save(buffer).then(path => {
  console.log(path);
})
```

返回值表示在 iCloud 云盘的路径。

# drive.open() -> Promise

使用系统的文件选择器从 iCloud 云盘选择文件：

```js
const drive = require("drive");
drive.open({
  type: ["public.data", "public.content"]
}).then(buffer => {
  console.log(buffer);
});
```

其中 `type` 指定文件的 MIME 类型，默认为全部文件。