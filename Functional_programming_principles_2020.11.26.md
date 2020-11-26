#### Core principle #1 - Don't change things
[Avoid Mutations and Side Effects Using Functional Programming Passed](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/avoid-mutations-and-side-effects-using-functional-programming)
>One of the core principles of functional programming is to not change things. ***Changes lead to bugs. It's easier to prevent bugs knowing that your functions don't change anything***, including the function arguments or any global variable.

#### Core principle #2 - Always declare dependencies explicitly
[Pass Arguments to Avoid External Dependence in a Function](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/pass-arguments-to-avoid-external-dependence-in-a-function)
>... This means if a function depends on a variable or object being present, then ***pass that variable or object directly into the function as an argument***.\
\
There are several good consequences from this principle. The function is easier to test, you ***know exactly what input it takes, and it won't depend on anything else in your program***.\
\
This can give you more confidence when you alter, remove, or add new code. You ***would know what you can or cannot change and you can see where the potential traps are***.\
\
Finally, the ***function would always produce the same output for the same set of inputs***, no matter what part of the code executes it.
