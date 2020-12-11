[freeCodeCamp challenge: Sum All Primes](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/intermediate-algorithm-scripting/sum-all-primes)

[freeCodeCamp: solutions](https://forum.freecodecamp.org/t/freecodecamp-challenge-guide-sum-all-primes/16085)

Note solution 1's prime number generator `getPrimes()` which appears to be using a very efficient logic:
1. Start from 2 which is a prime#, and we add 2 to the prime# list.
2. Mark every multiple of 2 - skip these #'s later.
3. Move on to the next # 3 (not a multiple of 2 and has not been marked for skipping); we are confident that up to this point all non-prime#'s have been skipped, so add 3 to the prime# list.
4.Mark every multiple of 3 - skip these #'s later.
4. Skip 4 (multiple of 2) which has been marked for skipping.
5. Now come to 5 which has not been marked and we are confident that up to this point all non-prime#'s have been skipped, so add 5 to the prime# list.
4.Mark every multiple of 5 - skip these #'s later.
4. Skip 6 (multiple of 2) which has been marked for skipping.
4. Now come to 7...

Also note the `<<` bitwise shift is not necessary, i.e. `j = i << 1` can be substituted with `j = i * 2` or `j = i + i` or even `j = i`. (The solution writer could just be trying to flex his muscle :b; or perhaps I'm being ignorant right now...)
```js
function getPrimes(max) {
    var sieve = [];
    var i;
    var j;
    var primes = [];
    for (i = 2; i <= max; ++i) {
      if (!sieve[i]) {
        // i has not been marked -- it is prime
        primes.push(i);
        for (j = i << 1; j <= max; j += i) {
          sieve[j] = true;
        }
      }
    }

    return primes;
  }
  ```
