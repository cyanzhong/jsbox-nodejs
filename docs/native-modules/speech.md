# module: "speech"

`speech` 模块提供了文字转语音相关的接口。

# speech.voices()

返回所有可用的语言列表：

```js
const speech = require("speech");
const voices = speech.voices();
```

# speech.speak(object)

调用文字转语音功能：

```js
const speech = require("speech");
speech.speak({
  text: "Hello, World!",
  rate: 0.5, // 0 ~ 1
  pitch: 1.0, // 0 ~ 1,
  language: "zh-Hans",
  voiceIdentifier: ""
});
```

其中 `voiceIdentifier` 需要使用 `voices` 接口得到，`language` 列表：

```
ar-SA
cs-CZ
da-DK
de-DE
el-GR
en-AU
en-GB
en-IE
en-US
en-US
en-ZA
es-ES
es-MX
fi-FI
fr-CA
fr-FR
he-IL
hi-IN
hu-HU
id-ID
it-IT
ja-JP
ko-KR
nl-BE
nl-NL
no-NO
pl-PL
pt-BR
pt-PT
ro-RO
ru-RU
sk-SK
sv-SE
th-TH
tr-TR
zh-CN
zh-HK
zh-TW
```