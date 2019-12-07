# module: "audio"

`audio` 模块提供跟音频播放相关的接口：

# audio.play(object)

播放一个音频：

```js
const audio = require("audio");
audio.play(1000);
```

该方式使用 sound id 播放内置音频，请参考：https://github.com/TUNER88/iOSSystemSoundsLibrary 。

也可以使用路径来播放一段音频，同时支持网络文件和本地文件：

```js
const audio = require("audio");
audio.play("https://");
// audio.play("assets/test.wav");
```

如果对播放状态进行更精细的控制，可以使用下面这些方法：

```js
// 暂停播放
audio.pause();
```

```js
// 恢复播放
audio.resume();
```

```js
// 停止播放
audio.stop();
```

```js
// 设置播放进度（秒）
audio.seek(60);
```

```js
// 获得当前的状态
const status = audio.status();
// 0: 已停止, 1: 等待播放, 2: 正在播放
```

```js
// 获取时长
const duration = audio.duration();
```

```js
// 获取当前的播放时间
const offset = audio.offset();
```

# 事件消息

音频播放过程中可以监听一些消息，例如：

```js
const audio = require("audio");
audio.play({
  events: {
    itemEnded: () => {},
    timeJumped: () => {},
    didPlayToEndTime: () => {},
    failedToPlayToEndTime: () => {},
    playbackStalled: () => {},
    newAccessLogEntry: () => {},
    newErrorLogEntry: () => {},
  }
});
```

参考：https://developer.apple.com/documentation/avfoundation/avplayeritem?language=objc