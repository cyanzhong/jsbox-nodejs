# User input

In Node script, you can use `stdin` and `stdout` for I/O, but just like we mentioned before, you should use:

- `$jsbox.stdin` instead of `process.stdin`
- `$jsbox.stdout` instead of `process.stdout`

Other than that difference, you can use them with your Node.js knowledge, for example:

```js
const readline = require("readline");

const interface = readline.createInterface({
  input: $jsbox.stdin,
  output: $jsbox.stdout,
  terminal: false
});

interface.on('line', line => {
  console.log(`Echo: ${line}`);
});
```

This is an echo program, it replicates what the user says.

# module: "input"

Other than stdin and stdout, using the `input` module is also a good solution.

# input.text(object) -> Promise

Using the JSBox text input component:

```js
const input = require("input");
input.text({
  type: 0,
  placeholder: "Input your name..",
  text: "Ying"
}).then(text => {
  console.log(text);
});
```

The `type` parameter specifies the keyboard appearance, refer to https://docs.xteko.com/#/en/data/constant?id=kbtype

This method returns a Promise object, you can also use it with async/await fashion.

# input.speech(object) -> Promise

Using the iOS built-in voice to text service:

```js
const input = require("input");
input.speech({
  locale: "en-US",
  autoFinish: true
}).then(text => {
  console.log(text);
});
```

The `autoFinish` means whether autocomplete after voice stopped, default is `false`. `locale` specifies the language locale, default is the current device locale.