[freeCodeCamp challenge: Spinal Tap Case](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/intermediate-algorithm-scripting/spinal-tap-case)

[freeCodeCamp: Solutions](https://forum.freecodecamp.org/t/freecodecamp-challenge-guide-spinal-tap-case/16078)

Note how solution 3 uses `(?=[A-Z])` to insert characters in front of any capital letters.

```js
function spinalCase(str) {
  // "It's such a fine line between stupid, and clever."
  // --David St. Hubbins

  return str
    .split(/\s|_|(?=[A-Z])/)
    .join("-")
    .toLowerCase();
}
```
