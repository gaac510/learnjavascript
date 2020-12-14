### [Link: freeCodeCamp challenge project - Telephone Number ValidatorPassed](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/javascript-algorithms-and-data-structures-projects/telephone-number-validator)

My solution:

```js
function telephoneCheck(str) {
  const checker = RegExp(
    "^(?:1\\s?)?" //May start with "1" followed by a space.
    + "(?:\\d{3}|[(]\\d{3}[)])" //Match 3 digits either by themselves or parenthesized.
    + "[-\\s]?" //May exist a "-" or a space.
    + "\\d{3}" //Match 3 digits.
    + "[-\\s]?" //May exist a "-" or a space.
    + "\\d{4}$" //End with 4 digits.
    , "ig"); //Flags shouldn't be required.
  console.log(checker);
  console.log(str.match(checker));
  return checker.test(str);
}

//Test
console.log(telephoneCheck("1 555-555-5555"));
