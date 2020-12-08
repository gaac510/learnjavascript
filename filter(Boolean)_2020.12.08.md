[Michael Uloth: The filter(Boolean) trick](https://www.michaeluloth.com/filter-boolean)

>... in JavaScript, this:
```js
array.filter(item => Boolean(item))
```
>is exactly the same as this:
```js
array.filter(Boolean)
```
>The second version is just written in a “tacit” or “point-free” style. We don’t name each item and pass it into Boolean, but ***JavaScript understands that Boolean takes one argument, so it takes the argument filter() exposes and passes it to Boolean for you***.

>If you find the first version easier to understand, use it! ***Readable code is more important than fancy tricks***.
