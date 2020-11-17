[A re-introduction to JavaScript (JS tutorial)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/A_re-introduction_to_JavaScript)

>You can convert a string to an integer using the built-in `parseInt()` function. This takes the base for the conversion as an optional second argument, which you should always provide:

```javascript
parseInt('123', 10); // 123
parseInt('010', 10); // 10
```

>In older browsers, strings beginning with a "0" are assumed to be in octal (radix 8), but this hasn't been the case since 2013 or so. Unless you're certain of your string format, you can get surprising results on those older browsers:

```javascript
parseInt('010');  //  8
parseInt('0x10'); // 16
```

>Here, we see the `parseInt()` function treat the first string as octal due to the leading 0, and the second string as hexadecimal due to the leading "0x". The hexadecimal notation is still in place; only octal has been removed.

**...**

>... `parseFloat()` always uses base 10.

**...**

>The `parseInt()` and `parseFloat()` functions parse a string until they reach a character that isn't valid for the specified number format, then return the number parsed up to that point. However the `+` operator simply converts the string to `NaN` if there is an invalid character contained within it. Just try parsing the string "10.2abc" with each method by yourself in the console and you'll understand the differences better.
