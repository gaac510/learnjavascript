[Faith Chikwekwe: When to Loop? When to Recurse?](https://medium.com/better-programming/when-to-loop-when-to-recurse-b786ad8977de#:~:text=When%20should%20I%20use%20recursion,complex%20for%20an%20iterative%20approach.)

>### When should I use recursion?
>Recursion is made for solving problems that can be broken down into smaller, repetitive problems. It is ***especially good for working on things that have many possible branches*** and are too complex for an iterative approach.\
\
One good example of this would be searching through a file system. You could start at the root folder, and then you could search through all the files and folders within that one. After that, you would enter each folder and search through each folder inside of that.\
![](https://miro.medium.com/max/700/0*5EuDOMXrvbghXkpn.jpg)\
Recursion works well for [this](https://github.com/gaac510/learnjavascript/blob/main/When_recursion_is_preferred_2020.12.12.md#:~:text=tree%20structure) type of structure ***because you can search multiple branching paths without having to include many different checks and conditions for every possibility***.\
\
For those of you who are familiar with data structures, you might notice that the image above of the file system looks a lot like a ***tree structure***.\
\
Trees and graphs are another time when recursion is the best and easiest way to do traversal.
