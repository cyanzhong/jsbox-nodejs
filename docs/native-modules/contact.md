# module: "contact"

`contact` 模块提供对系统通讯录相关的接口。

# contact.pick(object) -> Promise

从通讯录中选择一个或多个联系人：

```js
const contact = require("contact");
contact.pick({
  multi: false
}).then(result => {

});
```

其中 `multi` 为 `true` 时表示选择多个联系人。

# contact.fetch(object) -> Promise

通过关键字查找某些联系人：

```js
const contact = require("contact");
contact.fetch({
  key: "Ying"
}).then(results => {

});
```

获得的是一个数组，每个元素支持很多属性，请参考：https://developer.apple.com/documentation/contacts/cncontact

也可以查找某个分组下面的所有联系人：

```js
const contact = require("contact");
contact.fetch({
  group: group
}).then(results => {

});
```

# contact.create(object) -> Promise

创建联系人：

```js
const contact = require("contact");
contact.create({
  givenName: "Ying",
  familyName: "Zhong",
  phoneNumbers: {
    "Home": "18000000000",
    "Office": "88888888"
  },
  emails: {
    "Home": "log.e@qq.com"
  }
}).then(resp => {

});
```

# contact.save(object) -> Promise

将更新后的 contact 对象存储到系统通讯录：

```js
const contact = require("contact");
contact.save(object).then(resp => {

});
```

# contact.delete(object) -> Promise

删除一些联系人：

```js
const contact = require("contact");
contact.delete(contacts).then(resp => {

});
```

# contact.fetchGroups() -> Promise

获取联系人分组：

```js
const contact = require("contact");
contact.fetchGroups().then(groups => {
  console.log(`name: ${groups[0].name}`);
});
```

# contact.addGroup(string) -> Promise

添加一个新的分组：

```js
const contact = require("contact");
contact.addGroup("Group Name").then(group => {
  
});
```

# contact.deleteGroup(object) -> Promise

删除一个分组：

```js
const contact = require("contact");
contact.fetchGroups().then(groups => {
  contact.deleteGroup(groups[0]);
});
```

# contact.updateGroup(object) -> Promise

保存更新后的分组：

```js
const contact = require("contact");
contact.fetchGroups().then(groups => {
  const group = groups[0];
  group.name = "New Name";
  contact.updateGroup(group);
});
```

# contact.addToGroup(object) -> Promise

将联系人添加到分组：

```js
const contact = require("contact");
contact.addToGroup({
  contact: contactObject,
  group: groupObject
}).then(result => {

});
```

# contact.removeFromGroup(object) -> Promise

将联系人从分组中移除：

```js
const contact = require("contact");
contact.removeFromGroup({
  contact: contactObject,
  group: groupObject
}).then(result => {

});
```