# module: "reminder"

`reminder` module provides support for the Reminders

# reminder.fetch(object) -> Promise

Fetch reminders in the iOS Reminders.app:

```js
const reminder = require("reminder");
reminder.fetch({
  startDate: new Date(),
  hours: 2 * 24
}).then(resp => {
  const events = resp.events;
});
```

It looks very similar to the `calendar` module, the object structure:

Prop | Type | Read/Write | Description
---|---|---|---
title | string | rw | title
identifier | string | r | id
location | string | rw | location
notes | string | rw | notes
url | string | rw | url
modifiedDate | date | r | last modified date
creationDate | date | r | creation date
completed | boolean | rw | is completed
completionDate | date | r | completion date
alarmDate | date | rw | alarm date
priority | number | rw | priority (1 ~ 9) 

# reminder.create(object) -> Promise

Create a reminder item:

```js
const reminder = require("reminder");
reminder.create({
  title: "Hey!",
  alarmDate: new Date(),
  notes: "Hello, World!",
  url: "https://apple.com"
}).then(resp => {
  console.log(result);
});
```

You can use `alarmDate` and `alarmDates` to set up alarms.

# reminder.save(object) -> Promise

Similar to `calendar.save(...)`, it saves an updated reminder item:

```js
const reminder = require("reminder");
reminder.save(event);
```

# reminder.delete(object) -> Promise

Delete a reminder item:

```js
const reminder = require("reminder");
reminder.delete(event).then(result => {
  console.log(result);
});
```