# module: "speech"

`speech` module is a simple wrapper of the iOS TTS.

# speech.voices()

Returns all available voices:

```js
const speech = require("speech");
const voices = speech.voices();
```

# speech.speak(object)

Text to speech service:

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

`voiceIdentifier` could be retrieved by calling `voices` method. Available `language` values:

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