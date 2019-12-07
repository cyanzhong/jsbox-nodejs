# module: "reminder"

`reminder` 模块提供了 iOS 系统提醒事项相关的接口。

# reminder.fetch(object) -> Promise

用于读取提醒事项（会提示用户授权）：

```js
const reminder = require("reminder");
reminder.fetch({
  startDate: new Date(),
  hours: 2 * 24
}).then(resp => {
  const events = resp.events;
});
```

看起来和 `calendar` 极为相似，返回的数据是如下结构：

属性 | 类型 | 读写 | 说明
---|---|---|---
title | string | 读写 | 标题
identifier | string | 只读 | id
location | string | 读写 | 位置
notes | string | 读写 | 备注
url | string | 读写 | 网址
modifiedDate | date | 只读 | 修改时间
creationDate | date | 只读 | 创建时间
completed | boolean | 读写 | 是否完成
completionDate | date | 只读 | 完成时间
alarmDate | date | 读写 | 闹钟时间
priority | number | 读写 | 优先级(1 ~ 9) 

# reminder.create(object) -> Promise

用于创建一个提醒事项：

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

可以通过 `alarmDate` 和 `alarmDates` 来指定提醒闹钟时间。

# reminder.save(object) -> Promise

和 `calendar.save(...)` 类似，用于修改 event 后保存更新：

```js
const reminder = require("reminder");
reminder.save(event);
```

# reminder.delete(object) -> Promise

删除某个提醒事项：

```js
const reminder = require("reminder");
reminder.delete(event).then(result => {
  console.log(result);
});
```