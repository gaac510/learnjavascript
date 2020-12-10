For [freeCodeCamp challenge: Missing letters](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/intermediate-algorithm-scripting/missing-letters), trying to create a lookup table object where the keys are each of the a-y letters and the values are each of the b-z letters.

Could have typed them out but also tried (with success) using the below to generate the list from console output:

```js
console.log("abcdefghijklmnopqrstuvwxyz".replace(/(\w)(?=(\w))/g, "$1: '$2',\n\t\t"))
```
This experience also highlights a proper use of RegExp forward assertion.

Could have also used Excel but took this as a practice opportunity.
