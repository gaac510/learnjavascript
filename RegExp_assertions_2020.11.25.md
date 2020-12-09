[FreeCodeCamp: Regular Expressions: Positive and Negative LookaheadPassed](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/regular-expressions/positive-and-negative-lookahead)

* May include patterns at fixed locations outside lookahead parentheses. 
* Patterns not at an fixed location presumably should be inside the lookahead parentheses.

>A positive lookahead will look to make sure the element in the search pattern is there, _**but won't actually match it**_. A positive lookahead is used as `(?=...)` where the `...` is the required part that is not matched.\
\
On the other hand, a negative lookahead will look to make sure the element in the search pattern is not there. A negative lookahead is used as `(?!...)` where the `...` is the pattern that you do not want to be there. _**The rest of the pattern**_ is returned if the negative lookahead part is not present.\
...\
A more practical use of lookaheads is to _**check two or more patterns in one string**_. Here is a (naively) simple password checker that looks for between 3 and 6 characters and at least one number:
```js
let password = "abc123";
let checkPass = /(?=\w{3,6})(?=\D*\d)/;
checkPass.test(password); // Returns true
```
