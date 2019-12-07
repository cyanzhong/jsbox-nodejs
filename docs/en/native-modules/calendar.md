# module: "calendar"

`calendar` module provides calendar APIs.

# calendar.fetch(object) -> Promise

Fetch calendar items in the Calendar.app:

```js
const calendar = require("calendar");
calendar.fetch({
  startDate: new Date(),
  hours: 3 * 24,
}).then(result => {
  const events = result.events;
});
```

It fetches items from now to 3 days later. Other than specifying with `hour`, `endDate` is also supported.

The returned data contains an event list, it has the following properties:

Prop | Type | Read/Write | Description
---|---|---|---
title | string | rw | title
identifier | string | r | id
location | string | rw | location
notes | string | rw | notes
url | string | rw | url
modifiedDate | date | r | last modified date
creationDate | date | r | creation date
allDay | boolean | r | is all day event
startDate | date | r | start date
endDate | date | r | end date
status | number | r | [Refer](https://developer.apple.com/documentation/eventkit/ekeventstatus)

# calendar.create(object) -> Promise

Create a calendar item:

```js
const calendar = require("calendar");
calendar.create({
  title: "Hey!",
  startDate: new Date(),
  hours: 3,
  notes: "Hello, World!"
}).then(result => {
  console.log(result);
});
```

# calendar.save(object) -> Promise

Save a calendar item after some properties are changed:

```js
const calendar = require("calendar");
calendar.fetch({
  startDate: new Date(),
  hours: 3 * 24
}).then(resp => {
  const event = resp.events[0];
  event.title = "Modified";
  calendar.save(event);
});
```

You can use `alarmDate` and `alarmDates` to set up alarms.

# calendar.delete(object) -> Promise

Delete a certain calendar item:

```js
calendar.delete(event).then(result => {
  console.log(result);
});
```