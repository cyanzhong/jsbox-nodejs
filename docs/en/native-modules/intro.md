# Native modules

You can use standard Node.js code in JSBox. At the same time, we also wrapped many native iOS modules, letting you touch iOS components with standard Node.js programs. Such as accessing the clipboard, files sharing.

For those JSBox only modules, we call them native modules.

Native modules are standard `node modules`, the usage has no difference compared using other npm modules:

```js
const clipboard = require("clipboard");

// Returns the clipboard text
const text = clipboard.text();

// Change the clipboard text
clipboard.setText("Hey");
```

# Supported modules

Ideally, we would like to wrap everything you have in JSBox runtime. But it may take to long to achieve, in the current version, we only wrapped the following modules:

- [Intro](en/native-modules/intro.md)
- [App](en/native-modules/app.md)
- [System](en/native-modules/system.md)
- [Device](en/native-modules/device.md)
- [Input](en/native-modules/input.md)
- [UI](en/native-modules/ui.md)
- [Localization](en/native-modules/l10n.md)
- [Clipboard](en/native-modules/clipboard.md)
- [Photo](en/native-modules/photo.md)
- [iCloud Drive](en/native-modules/drive.md)
- [Quick Look](en/native-modules/quicklook.md)
- [Sharing](en/native-modules/share.md)
- [QR Code](en/native-modules/qrcode.md)
- [Location](en/native-modules/location.md)
- [Safari](en/native-modules/safari.md)
- [Local Push](en/native-modules/push.md)
- [Audio](en/native-modules/audio.md)
- [Speech](en/native-modules/speech.md)
- [Calendar](en/native-modules/calendar.md)
- [Reminder](en/native-modules/reminder.md)
- [Contact](en/native-modules/contact.md)
- [Message](en/native-modules/message.md)
- [Montion](en/native-modules/motion.md)
- [Detector](en/native-modules/detector.md)

We believe those modules are enough for most scenarios, if you really need more, before we finish everything, you can consider calling JSBox from Node.

Regarding communications between JSBox and Node, refer to: [Virtual runtimes](en/vm/intro.md).