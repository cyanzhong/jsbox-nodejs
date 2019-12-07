# module: "message"

`message` 模块提供对短信、邮件相关接口的支持。

# message.sms(object) -> Promise

调用系统接口发送短信：

```js
const message = require("message");
message.sms({
  recipients: ["18688888888", "10010"],
  body: "Message body",
  subject: "Message subject",
  attachments: [
    {
      name: "image.png",
      data: buffer
    }
  ]
}).then(result => {

});
```

参数 | 说明
---|---
recipients | 接受者
body | 内容
subject | 主题
attachments | File 格式附件
result | 0: 取消 1: 成功 2: 失败

# message.mail(object) -> Promise

调用系统接口发送邮件：

```js
message.mail({
  subject: "Message subject",
  to: ["18688888888", "10010"],
  cc: [],
  bcc: [],
  body: "Message body",
  attachments: [
    {
      name: "image.png",
      data: buffer
    }
  ]
}).then(result => {

});
```

参数 | 说明
---|---
subject | 主题
to | 接受者
cc | 抄送
bcc | 密送
body | 内容
isHTML | 内容是否为 HTML
attachments | File 格式附件
result | 0: 取消 1: 保存 2: 成功 3: 失败