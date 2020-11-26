[Wikipedia: Callback (computer programming)](https://en.wikipedia.org/wiki/Callback_(computer_programming))

>...any executable code that is passed as an argument to other code; that other code is expected to **call back (execute)** the argument at a given time. This execution may be immediate as in a synchronous callback, or it might happen at a later time as in an asynchronous callback.

[MDN web docs: Callback function](https://developer.mozilla.org/en-US/docs/Glossary/Callback_function)

>... a quick example:
```js
function greeting(name) {
  alert('Hello ' + name);
}

function processUserInput(callback) {
  var name = prompt('Please enter your name.');
  callback(name);
}

processUserInput(greeting);
```
