# module: "push"

`push` module provides support for the iOS local push notifications.

# push.schedule(object) -> Promise

Schedule a local push notification:

```js
const push = require("push");
push.schedule({
  title: "Title",
  body: "Body",
  delay: 5,
  handler: result => {
    const id = result.id;
  }
});
```

This notification will be delivered after 5 seconds.

Param | Type | Description
---|---|---
title | string | title
body | string | body
id | string | identifier (optional)
sound | string | sound
mute | bool | mute
repeats | bool | repeats
script | string | script name
height | number | 3D Touch view height
query | json | extra parameters, will be passed to $context.query
attachments | array | media attachments, File format
renew | bool | whether renew

Above case is how to schedule a push with delay, you can also setup a date:

```js
const date = new Date();
date.setSeconds(date.getSeconds() + 10);

const push = require("push");
push.schedule({
  title: "Title",
  body: "Body",
  date: date,
  handler: result => {
    const id = result.id;
  }
});
```

Other than that, location based notifications are supported:

```js
const push = require("push");
push.schedule({
  title: "Title",
  body: "Body",
  region: {
    lat: 0, // latitude
    lng: 0, // longitude
    radius: 1000, // meters
    notifyOnEntry: true, // notify on entry
    notifyOnExit: true // notify on exit
  }
});
```

This requires location access, it will fail if the user rejected.

Besides, a `script` parameter is supported to specify a script, it will be executed when the notification is tapped by the user. Also, the user can preview the script result by triggering 3D Touch.

# push.cancel(object)

Cancel a scheduled push notification:

```js
const push = require("push");
push.cancel({
  title: "Title",
  body: "Body",
});
```

JSBox will cancel all notifications that match the `title` and `body`.

You can also can it the identifier:

```js
const push = require("push");
push.cancel({
  id: ""
});
```

# push.clear()

Clears all push notifications:

```js
const push = require("push");
push.clear();
```