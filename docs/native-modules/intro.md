# Native 模块

在 JSBox 里面使用 Node 运行时，你可以运行标准的 Node.js 程序。同时，我们也为 Node 运行时提供了很多 Native 模块，让你可以通过标准的 Node.js 程序来与 iOS 原生功能进行交互。例如：读取剪贴板、使用 share sheet 分享文件等等。

这些 JSBox 特有的模块，我们统一将其称为 Native 模块。

Native 模块是标准的 `node module`，所以在使用上和普通的 node module 没有任何区别，例如这样：

```js
const clipboard = require("clipboard");

// Returns the clipboard text
const text = clipboard.text();

// Change the clipboard text
clipboard.setText("Hey");
```

# 支持的模块

在理想的状况下，我们希望 JSBox 的 Node 环境具有和原生运行时同样的能力。但做到这一点需要巨大的时间和精力，所以在目前的版本里面我们暂时只提供了大部分的模块：

- [应用相关](native-modules/app.md)
- [系统相关](native-modules/system.md)
- [设备相关](native-modules/device.md)
- [用户输入](native-modules/input.md)
- [用户界面](native-modules/ui.md)
- [本地化](native-modules/l10n.md)
- [剪贴板](native-modules/clipboard.md)
- [图片](native-modules/photo.md)
- [iCloud 云盘](native-modules/drive.md)
- [预览](native-modules/quicklook.md)
- [社交分享](native-modules/share.md)
- [二维码](native-modules/qrcode.md)
- [地理位置](native-modules/location.md)
- [Safari](native-modules/safari.md)
- [推送](native-modules/push.md)
- [音频](native-modules/audio.md)
- [语音合成](native-modules/speech.md)
- [日历](native-modules/calendar.md)
- [提醒事项](native-modules/reminder.md)
- [通讯录](native-modules/contact.md)
- [消息](native-modules/message.md)
- [传感数据](native-modules/motion.md)
- [数据检测](native-modules/detector.md)

这些模块能够满足你绝大部分时候的需求，如果需要更灵活的功能，在我们完善 Native 模块之前，可以考虑通过 JSBox 与 Node 的通信来实现。

关于这部分的内容，可以在这里找到：[通信机制](vm/intro.md)。