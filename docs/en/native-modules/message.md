# module: "message"

`message` provides support for the system mail and SMS service.

# message.sms(object) -> Promise

Sending SMS using the system built-in component:

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

Param | Description
---|---
recipients | receivers
body | body
subject | subject
attachments | attachments (Files)
result | 0: cancelled 1: succeeded 2: failed

# message.mail(object) -> Promise

Sending emails using the system built-in component:

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

Param | Description
---|---
subject | subject
to | receiver
cc | cc
bcc | bcc
body | body
isHTML | is body an HTML
attachments | attachments (Files)
result | 0: cancelled 1: succeeded 2: failed