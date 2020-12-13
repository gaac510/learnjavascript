Note this list may require continuous updates.

When coding, prioritise and try to balance the below:

1. Runtime efficiency
1. Readability 
1. General work efficiency


#### [Wikipedia: Cyclomatic complexity](https://en.wikipedia.org/wiki/Cyclomatic_complexity)
#### [freeCodeCamp challenge: Palindrome Checker](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/javascript-algorithms-and-data-structures-projects/palindrome-checker)
#### [freeCodeCamp: solutions](https://forum.freecodecamp.org/t/freecodecamp-challenge-guide-palindrome-checker/16004)

Note solution 3 - even though it doesn't have the shortest codes, it runs most efficient as its creator noted:
>* I was given this problem in an interview. I quickly arrived at the basic solution, and the ***interviewer told me to make it better***. The algorithm would take way too long if he passed the Bible as the string. He wanted it to be instant.
>
>* The simpler solutions perform very poorly on long strings because they ***operate on the whole string*** multiple times (toLowerCase(), replace(), split(), reverse(), join()) before comparing the whole string twice.
>* The beauty of this solution is it ***never*** needs to ***read through the whole string***, even once, to know that it’s not a palindrome. Why read through the whole string if you can tell that it’s not a palindrome just by looking at two letters?
>* Uses a while loop instead of a for loop as a best practice - because we are using two variables, one is the index starting from the beginning of the string, and the other starts at the end of the string.
