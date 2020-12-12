[Wikipedia: Euclidean Algorithm](https://en.wikipedia.org/wiki/Euclidean_algorithm)
>...\
\
The version of the Euclidean algorithm described above (and by Euclid) can take many subtraction steps to find the GCD when one of the given numbers is much bigger than the other. A more efficient version of the algorithm shortcuts these steps, instead replacing the larger of the two numbers by its remainder when divided by the smaller of the two (with this version, the algorithm stops when reaching a zero remainder). ***With this improvement, the algorithm never requires more steps than five times the number of digits (base 10) of the smaller integer. This was proven by Gabriel Lamé in 1844, and marks the beginning of computational complexity theory. Additional methods for improving the algorithm's efficiency were developed in the 20th century.***\
\
The Euclidean algorithm ***has many theoretical and practical applications***. It is used for reducing fractions to their simplest form and for performing division in modular arithmetic. Computations using this algorithm form part of the ***cryptographic protocols that are used to secure internet communications***, and in methods for breaking these cryptosystems by factoring large composite numbers. The Euclidean algorithm may be used to solve Diophantine equations, such as finding numbers that satisfy multiple congruences according to the Chinese remainder theorem, to construct continued fractions, and to find accurate rational approximations to real numbers. Finally, ***it can be used as a basic tool for proving theorems in number theory*** such as Lagrange's four-square theorem and the uniqueness of prime factorizations. The original algorithm was described only for natural numbers and geometric lengths (real numbers), but the algorithm was generalized in the 19th century to other types of numbers, such as Gaussian integers and polynomials of one variable. This led to modern abstract algebraic notions such as Euclidean domains.


[zh.wikipedia: 輾轉相除法](https://zh.wikipedia.org/wiki/%E8%BC%BE%E8%BD%89%E7%9B%B8%E9%99%A4%E6%B3%95)\
![](https://upload.wikimedia.org/wikipedia/commons/e/e2/Euclidean_algorithm_252_105_animation_flipped.gif)
>辗转相除法有很多应用，它甚至可以用来生成全世界不同文化中的传统音乐节奏。[1]在现代密码学方面，它是RSA算法（一种在电子商务中广泛使用的公钥加密算法）的重要部分。它还被用来解丢番图方程，比如寻找满足中国剩余定理的数，或者求有限域中元素的逆。辗转相除法还可以用来构造连分数，在施图姆定理和一些整数分解算法中也有应用。***辗转相除法是现代数论中的基本工具***。\
\
辗转相除法处理大数时***非常高效***，如果用除法而不是减法实现，它需要的步骤不会超过较小数的位数（十进制下）的五倍。拉梅于1844年证明了这点，同时这也标志着***计算复杂性理论的开端***。


[freeCodeCamp challenge: Smallest Common MultiplePassed](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/intermediate-algorithm-scripting/smallest-common-multiple)

[freeCodeCamp: solutions](https://forum.freecodecamp.org/t/freecodecamp-challenge-guide-smallest-common-multiple/16075)

Note solution 2 & at least one other solution use the Euclidean Algorithm to reduce the number of loops / computing resources required to complete the task. The logic goes like:
1. Use the Euclidean Algorithm to find the GCD (Greatest Common Divisor) of two numbers.
1. [Calculate the LCM (Least Common Multiple) of the two numbers. (Wikipedia)](https://en.wikipedia.org/wiki/Least_common_multiple#Using_the_greatest_common_divisor)\
![](https://wikimedia.org/api/rest_v1/media/math/render/svg/d5722b8e2574f2ffbb929208d3a4b98fd2a0f7ff)
1. Generate a list of integers from the higher of the range given till the lower of the range. 
1. Start by getting the LCM of the largest two of the list, and work through the remainder of the list, to get the LCM of all list elements.


```js
function smallestCommons(arr) {
  var range = [];
  for (var i = Math.max(arr[0], arr[1]); i >= Math.min(arr[0], arr[1]); i--) {
    range.push(i);
  }

  // can use reduce() in place of this block
  var lcm = range[0];
  for (i = 1; i < range.length; i++) {
    var GCD = gcd(lcm, range[i]);
    lcm = (lcm * range[i]) / GCD;
  }
  return lcm;

  function gcd(x, y) {
    // Implements the Euclidean Algorithm
    if (y === 0) return x;
    else return gcd(y, x % y);
  }
}

// test here
smallestCommons([1, 5]);
```

Also note solution 4 - while the codes look simple enough, it appears to me they are essentially brute forcing for a solution and would be resource-intensive.
```js
const smallestCommons = arr => {
  let max = Math.max(...arr);
  let min = Math.min(...arr);
  // Initially the solution is assigned to the highest value of the array
  let sol = max;

  for (let i = max - 1; i >= min; i--) {
    // Each time the solution checks (i.e. sol%i===0) it won't be necessary
    // to increment 'max' to our solution and restart the loop
    if (sol % i) {
      sol += max;
      i = max;
    }
  }
  return sol;
};

// test here
smallestCommons([1, 5]);
```
