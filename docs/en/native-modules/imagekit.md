# Image Processing

JSBox 2.1.0 brings `imagekit` module for image processing, you can achieve many effects easily:

- Resize
- Rotate
- Grayscale
- Masking
...

In order to make it easier to understand, we created a demo project that uses all APIs: https://github.com/cyanzhong/jsbox-imagekit-node

# imagekit.info(File)

Get image information:

```js
const imagekit = require("imagekit");
const info = imagekit.info(source);
// width, height, orientation, scale, props
```

# imagekit.grayscale(File)

Get grayscaled image:

```js
const imagekit = require("imagekit");
const output = imagekit.grayscale(source);
```

# imagekit.invert(File)

Invert colors:

```js
const imagekit = require("imagekit");
const output = imagekit.invert(source);
```

# imagekit.sepia(File)

Apply sepia filter:

```js
const imagekit = require("imagekit");
const output = imagekit.sepia(source);
```

# imagekit.adjustEnhance(File)

Enhance image automatically:

```js
const imagekit = require("imagekit");
const output = imagekit.adjustEnhance(source);
```

# imagekit.adjustRedEye(File)

Red-eye adjustment:

```js
const imagekit = require("imagekit");
const output = imagekit.adjustRedEye(source);
```

# imagekit.adjustBrightness(File, value)

Adjust brightness:

```js
const imagekit = require("imagekit");
const output = imagekit.adjustBrightness(source, 100);
// value range: (-255, 255)
```

# imagekit.adjustContrast(File, value)

Adjust contrast:

```js
const imagekit = require("imagekit");
const output = imagekit.adjustContrast(source, 100);
// value range: (-255, 255)
```

# imagekit.adjustGamma(File, value)

Adjust gamma value:

```js
const imagekit = require("imagekit");
const output = imagekit.adjustGamma(source, 4);
// value range: (0.01, 8)
```

# imagekit.adjustOpacity(File, value)

Adjust opacity:

```js
const imagekit = require("imagekit");
const output = imagekit.adjustOpacity(source, 0.5);
// value range: (0, 1)
```

# imagekit.blur(File, bias)

Apply gaussian blur:

```js
const imagekit = require("imagekit");
const output = imagekit.blur(source, 0);
```

# imagekit.emboss(File, bias)

Emboss effect:

```js
const imagekit = require("imagekit");
const output = imagekit.emboss(source, 0);
```

# imagekit.sharpen(File, bias)

Sharpen:

```js
const imagekit = require("imagekit");
const output = imagekit.sharpen(source, 0);
```

# imagekit.unsharpen(File, bias)

Unsharpen:

```js
const imagekit = require("imagekit");
const output = imagekit.unsharpen(source, 0);
```

# imagekit.detectEdge(source, bias)

Edge detection:

```js
const imagekit = require("imagekit");
const output = imagekit.detectEdge(source, 0);
```

# imagekit.mask(File, mask)

Crop an image with `mask`:

```js
const imagekit = require("imagekit");
const output = imagekit.mask(source, mask);
```

# imagekit.reflect(File, height, fromAlpha, toAlpha)

Create an up-down reflected image, from `height` position, change alpha value from `fromAlpha` to `toAlpha`:

```js
const imagekit = require("imagekit");
const output = imagekit.reflect(source, 100, 0, 1);
```

# imagekit.cropTo(File, size, mode)

Crop an image:

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

Resize an image with scale:

```js
const imagekit = require("imagekit");
const output = imagekit.scaleBy(source, 0.5);
```

# imagekit.scaleTo(File, size, mode)

Resize an image to a specific size:

```js
const imagekit = require("imagekit");
const output = imagekit.scaleTo(source, {width: 100, height: 100}, 0);
// mode:
//   - 0: scaleFill
//   - 1: scaleAspectFit
//   - 2: scaleAspectFill
```

# imagekit.scaleFill(File, size)

Resize an image using `scaleFill` mode:

```js
const imagekit = require("imagekit");
const output = imagekit.scaleFill(source, {width: 100, height: 100});
```

# imagekit.scaleAspectFit(File, size)

Resize an image using `scaleAspectFit` mode:

```js
const imagekit = require("imagekit");
const output = imagekit.scaleAspectFit(source, {width: 100, height: 100});
```

# imagekit.scaleAspectFill(File, size)

Resize an image using `scaleAspectFill` mode:

```js
const imagekit = require("imagekit");
const output = imagekit.scaleAspectFill(source, {width: 100, height: 100});
```

# imagekit.rotate(File, radians)

Rotate an image (it may change the size):

```js
const imagekit = require("imagekit");
const output = imagekit.rotate(source, Math.PI * 0.25);
```

# imagekit.rotatePixels(File, radians)

Rotate an image (keeps the image size, some contents might be clipped):

```js
const imagekit = require("imagekit");
const output = imagekit.rotatePixels(source, Math.PI * 0.25);
```

# imagekit.flip(File, mode)

Flip an image:

```js
const imagekit = require("imagekit");
const output = imagekit.flip(source, 0);
// mode:
//   - 0: vertically
//   - 1: horizontally
```

# imagekit.concatenate(Files, space, mode)

Concatenate images with space:

```js
const imagekit = require("imagekit");
const output = imagekit.concatenate(Files, 10, 0);
// mode:
//   - 0: vertically
//   - 1: horizontally
```

# imagekit.combine(File, mask, mode)

Add `mask` directly on `image`:

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

Get an image with rounded corners:

```js
const imagekit = require("imagekit");
const output = imagekit.rounded(source, 10);
```

# imagekit.circular(image)

Get a circular image, it will be centered and clipped if the source image isn't a square:

```js
const imagekit = require("imagekit");
const output = imagekit.circular(source);
```

# imagekit.extractGIF(data) -> Promise

Extract GIF data to frames:

```js
const imagekit = require("imagekit");
const {images, durations} = await imagekit.extractGIF(data);
// image: all image frames
// durations: duration for each frame
```

# imagekit.makeGIF(source, options) -> Promise

Make GIF with image array or video data:

```js
const imagekit = require("imagekit");
const images = [File1, File2];
const options = {
  durations: [0.5, 0.5],
  // size: 16, 12, 8, 4, 2
}
const data = await imagekit.makeGIF(Files, options);
```

You can also use `duration` instead of `durations`, it makes the duration of each frame are the same.

# imagekit.makeVideo(source, options) -> Promise

Make video with image array or GIF data:

```js
const imagekit = require("imagekit");
const images = [File1, File2];
const data = await imagekit.makeVideo(Files, {
  durations: [0.5, 0.5]
});
```

You can also use `duration` instead of `durations`, it makes the duration of each frame are the same, GIF data doesn't require durations.