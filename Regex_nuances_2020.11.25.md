* Regex test results are dominated by "true" i.e. matching pattern(s); existance of "false" i.e. non-matching pattern(s) won't be revealed.
* If trying to check that a pattern doens't exist, construct the Regex so that a "true" result is returned for a "not" pattern.\
(These wordings need refinement...)

[freeCodeCamp: Basic Algorithm Scripting: Mutations](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-algorithm-scripting/mutations)
>Return true if the string in the first element of the array contains all of the letters of the string in the second element of the array.

[RandellDawson @ freeCodeCamp: ...solution using a Regular Expression](https://forum.freecodecamp.org/t/freecodecamp-challenge-guide-mutations/16025/18?u=gaac510)
```js
function mutation(arr) {
  var re = new RegExp('[^'+arr[0]+']', "i");
  return !re.test(arr[1]);
}
```
