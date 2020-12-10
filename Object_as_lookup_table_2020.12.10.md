[freeCodeCamp challenge: DNA Pairing](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/intermediate-algorithm-scripting/dna-pairing)

[freeCodeCamp solutions](https://forum.freecodecamp.org/t/freecodecamp-challenge-guide-dna-pairing/16009)

Note how solution 2 created an object for looking up pairs:
```js
function pairElement(str) {
  //create object for pair lookup
  var pairs = {
    A: "T",
    T: "A",
    C: "G",
    G: "C"
  };
  //split string into array of characters
  var arr = str.split("");
  //map character to array of character and matching pair
  return arr.map(x => [x, pairs[x]]);
}
```
