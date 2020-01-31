# 图像处理

JSBox 2.1.0 增加了图像处理模块 `imagekit`，通过这个模块你可以很轻松的处理图像，例如：

- 调整大小
- 旋转
- 制作灰度图像
- 图像叠加
...

为了更直观的介绍，我们构建了一个使用了所有接口的样例项目：https://github.com/cyanzhong/jsbox-imagekit-node

# imagekit.info(File)

获取图片信息：

```js
const imagekit = require("imagekit");
const info = imagekit.info(source);
// width, height, orientation, scale, props
```

# imagekit.grayscale(File)

转换成灰度图像：

```js
const imagekit = require("imagekit");
const output = imagekit.grayscale(source);
```

# imagekit.invert(File)

将图像反色：

```js
const imagekit = require("imagekit");
const output = imagekit.invert(source);
```

# imagekit.sepia(File)

添加棕褐色滤镜：

```js
const imagekit = require("imagekit");
const output = imagekit.sepia(source);
```

# imagekit.adjustEnhance(File)

自动改善图像效果：

```js
const imagekit = require("imagekit");
const output = imagekit.adjustEnhance(source);
```

# imagekit.adjustRedEye(File)

自动红眼消除：

```js
const imagekit = require("imagekit");
const output = imagekit.adjustRedEye(source);
```

# imagekit.adjustBrightness(File, value)

调整图片亮度：

```js
const imagekit = require("imagekit");
const output = imagekit.adjustBrightness(source, 100);
// value range: (-255, 255)
```

# imagekit.adjustContrast(File, value)

调整图片对比度：

```js
const imagekit = require("imagekit");
const output = imagekit.adjustContrast(source, 100);
// value range: (-255, 255)
```

# imagekit.adjustGamma(File, value)

调整图片伽马值：

```js
const imagekit = require("imagekit");
const output = imagekit.adjustGamma(source, 4);
// value range: (0.01, 8)
```

# imagekit.adjustOpacity(File, value)

调整图片不透明度：

```js
const imagekit = require("imagekit");
const output = imagekit.adjustOpacity(source, 0.5);
// value range: (0, 1)
```

# imagekit.blur(File, bias)

高斯模糊效果：

```js
const imagekit = require("imagekit");
const output = imagekit.blur(source, 0);
```

# imagekit.emboss(File, bias)

浮雕效果：

```js
const imagekit = require("imagekit");
const output = imagekit.emboss(source, 0);
```

# imagekit.sharpen(File, bias)

锐化：

```js
const imagekit = require("imagekit");
const output = imagekit.sharpen(source, 0);
```

# imagekit.unsharpen(File, bias)

钝化:

```js
const imagekit = require("imagekit");
const output = imagekit.unsharpen(source, 0);
```

# imagekit.detectEdge(source, bias)

边缘检测：

```js
const imagekit = require("imagekit");
const output = imagekit.detectEdge(source, 0);
```

# imagekit.mask(File, mask)

使用 `mask` 作为蒙版进行切图：

```js
const imagekit = require("imagekit");
const output = imagekit.mask(source, mask);
```

# imagekit.reflect(File, height, fromAlpha, toAlpha)

创建上下镜像的图片，从 `height` 处折叠，透明度从 `fromAlpha` 变化到 `toAlpha`：

```js
const imagekit = require("imagekit");
const output = imagekit.reflect(source, 100, 0, 1);
```

# imagekit.cropTo(File, size, mode)

图片裁剪：

```js
const imagekit = require("imagekit");
const output = imagekit.cropTo(source, {width: 100, height: 100}, 0);
// mode:
//   - 0: top-left
//   - 1: top-center
//   - 2: top-right
//   - 3: bottom-left
//   - 4: bottom-center
//   - 5: bottom-right
//   - 6: left-center
//   - 7: right-center
//   - 8: center
```

# imagekit.scaleBy(File, value)

使用比例调整图片大小：

```js
const imagekit = require("imagekit");
const output = imagekit.scaleBy(source, 0.5);
```

# imagekit.scaleTo(File, size, mode)

使用 size 调整图片大小：

```js
const imagekit = require("imagekit");
const output = imagekit.scaleTo(source, {width: 100, height: 100}, 0);
// mode:
//   - 0: scaleFill
//   - 1: scaleAspectFit
//   - 2: scaleAspectFill
```

# imagekit.scaleFill(File, size)

使用 `scaleFill` 模式调整大小：

```js
const imagekit = require("imagekit");
const output = imagekit.scaleFill(source, {width: 100, height: 100});
```

# imagekit.scaleAspectFit(File, size)

使用 `scaleAspectFit` 模式调整大小：

```js
const imagekit = require("imagekit");
const output = imagekit.scaleAspectFit(source, {width: 100, height: 100});
```

# imagekit.scaleAspectFill(File, size)

使用 `scaleAspectFill` 模式调整大小：

```js
const imagekit = require("imagekit");
const output = imagekit.scaleAspectFill(source, {width: 100, height: 100});
```

# imagekit.rotate(File, radians)

旋转图片（将会调整图像大小）：

```js
const imagekit = require("imagekit");
const output = imagekit.rotate(source, Math.PI * 0.25);
```

# imagekit.rotatePixels(File, radians)

旋转图片（不会改变图像大小，可能会裁剪）：

```js
const imagekit = require("imagekit");
const output = imagekit.rotatePixels(source, Math.PI * 0.25);
```

# imagekit.flip(File, mode)

获得镜像图片：

```js
const imagekit = require("imagekit");
const output = imagekit.flip(source, 0);
// mode:
//   - 0: vertically
//   - 1: horizontally
```

# imagekit.concatenate(Files, space, mode)

拼接多张图片，可以添加间距：

```js
const imagekit = require("imagekit");
const output = imagekit.concatenate(Files, 10, 0);
// mode:
//   - 0: vertically
//   - 1: horizontally
```

# imagekit.combine(File, mask, mode)

将两个图片叠加：

```js
const imagekit = require("imagekit");
const output = imagekit.combine(File1, File2, mode);
// mode:
//   - 0: top-left
//   - 1: top-center
//   - 2: top-right
//   - 3: bottom-left
//   - 4: bottom-center
//   - 5: bottom-right
//   - 6: left-center
//   - 7: right-center
//   - 8: center (default)
//   - {x: number, y: number}: absolute position
```

# imagekit.rounded(File, radius)

获取圆角图片：

```js
const imagekit = require("imagekit");
const output = imagekit.rounded(source, 10);
```

# imagekit.circular(image)

获取正圆形图片，如果原图不是正方形则会居中并从来裁剪：

```js
const imagekit = require("imagekit");
const output = imagekit.circular(source);
```

# imagekit.extractGIF(data) -> Promise

将 GIF 文件分解成单帧：

```js
const imagekit = require("imagekit");
const {images, durations} = await imagekit.extractGIF(data);
// image: all image frames
// durations: duration for each frame
```

# imagekit.makeGIF(source, options) -> Promise

将 image 数组或视频文件 data 合成为 GIF 文件：

```js
const imagekit = require("imagekit");
const images = [File1, File2];
const options = {
  durations: [0.5, 0.5],
  // size: 16, 12, 8, 4, 2
}
const data = await imagekit.makeGIF(Files, options);
```

若使用 `duration` 替代 `durations`，则每张图片时长一致。

# imagekit.makeVideo(source, options) -> Promise

将 image 数组或 GIF 文件合成为视频文件：

```js
const imagekit = require("imagekit");
const images = [File1, File2];
const data = await imagekit.makeVideo(Files, {
  durations: [0.5, 0.5]
});
```

若使用 `duration` 替代 `durations`，则每张图片时长一致，使用 GIF 时不需要指定时长。