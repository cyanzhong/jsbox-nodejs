# module: "audio"

`audio` module provides audio APIs.

# audio.play(object)

Play audio with ID or path: 

```js
const audio = require("audio");
audio.play(1000);
```

This uses sound id for playing system built-in sounds. Refer to: https://github.com/TUNER88/iOSSystemSoundsLibrary.

The parameter can also be a string, which is a remote URL or a local path:

```js
const audio = require("audio");
audio.play("https://");
// audio.play("assets/test.wav");
```

If you want to control it more precisely, use methods as below:

```js
// Pause the audio
audio.pause();
```

```js
// Resume the audio
audio.resume();
```

```js
// Stop the audio
audio.stop();
```

```js
// Seek to location, second based
audio.seek(60);
```

```js
// Get the current status
const status = audio.status();
// 0: paused, 1: waiting, 2: playing
```

```js
// Get the audio length
const duration = audio.duration();
```

```js
// Get the current offset
const offset = audio.offset();
```

# Events

You can observe some events, such as:

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

Refer to: https://developer.apple.com/documentation/avfoundation/avplayeritem?language=objc