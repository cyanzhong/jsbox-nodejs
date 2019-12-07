# module: "calendar"

`calendar` 模块提供了 iOS 系统日历相关的接口。

# calendar.fetch(object) -> Promise

用于读取日历事件（会提示用户授权）：

```js
const calendar = require("calendar");
calendar.fetch({
  startDate: new Date(),
  hours: 3 * 24,
}).then(result => {
  const events = result.events;
});
```

表示读取从现在开始往后 3 天的所有日历事件，除了指定 `hours` 以外，也可以自己计算并指定 `endDate`。

在返回的数据里面，events 内含的对象结构如下：

属性 | 类型 | 读写 | 说明
---|---|---|---
title | string | 读写 | 标题
identifier | string | 只读 | id
location | string | 读写 | 位置
notes | string | 读写 | 备注
url | string | 读写 | 网址
modifiedDate | date | 只读 | 修改时间
creationDate | date | 只读 | 创建时间
allDay | boolean | 只读 | 是否全天
startDate | date | 只读 | 开始时间
endDate | date | 只读 | 结束时间
status | number | 只读 | 状态[请参考](https://developer.apple.com/documentation/eventkit/ekeventstatus)

# calendar.create(object) -> Promise

用于创建一个日历事项：

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

通过 `calendar.fetch` 取出来的日历项，可以修改一些属性，然后通过 save 接口更新：

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

可以通过 `alarmDate` 和 `alarmDates` 来指定提醒闹钟时间。

# calendar.delete(object) -> Promise

在系统日历中删除某个日历项：

```js
calendar.delete(event).then(result => {
  console.log(result);
});
```