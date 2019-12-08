# module: "contact"

`contact` module provides iOS contacts APIs.

# contact.pick(object) -> Promise

Select one or more contacts using the built-in picker:

```js
const contact = require("contact");
contact.pick({
  multi: false
}).then(result => {

});
```

It allows multiple-selection when `multi` is `true`.

# contact.fetch(object) -> Promise

Search contacts using a keyword:

```js
const contact = require("contact");
contact.fetch({
  key: "Ying"
}).then(results => {

});
```

It returns an array which supports many properties, refer to: https://developer.apple.com/documentation/contacts/cncontact for details.

You can also retrieve all contacts under a certain group:

```js
const contact = require("contact");
contact.fetch({
  group: group
}).then(results => {

});
```

# contact.create(object) -> Promise

Create a contact:

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

Save an updated contact:

```js
const contact = require("contact");
contact.save(object).then(resp => {

});
```

# contact.delete(object) -> Promise

Delete some contacts:

```js
const contact = require("contact");
contact.delete(contacts).then(resp => {

});
```

# contact.fetchGroups() -> Promise

Get all contact groups:

```js
const contact = require("contact");
contact.fetchGroups().then(groups => {
  console.log(`name: ${groups[0].name}`);
});
```

# contact.addGroup(string) -> Promise

Create a new group:

```js
const contact = require("contact");
contact.addGroup("Group Name").then(group => {
  
});
```

# contact.deleteGroup(object) -> Promise

Delete a group:

```js
const contact = require("contact");
contact.fetchGroups().then(groups => {
  contact.deleteGroup(groups[0]);
});
```

# contact.updateGroup(object) -> Promise

Save an updated group:

```js
const contact = require("contact");
contact.fetchGroups().then(groups => {
  const group = groups[0];
  group.name = "New Name";
  contact.updateGroup(group);
});
```

# contact.addToGroup(object) -> Promise

Add a contact into a group:

```js
const contact = require("contact");
contact.addToGroup({
  contact: contactObject,
  group: groupObject
}).then(result => {

});
```

# contact.removeFromGroup(object) -> Promise

Remove a contact from a group:

```js
const contact = require("contact");
contact.removeFromGroup({
  contact: contactObject,
  group: groupObject
}).then(result => {

});
```