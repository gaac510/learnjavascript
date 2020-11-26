[Object Oriented Programming: Override Inherited Methods](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/object-oriented-programming/override-inherited-methods)

```js
function Animal() { }
Animal.prototype.eat = function() {
  return "nom nom nom";
};
function Bird() { }

// Inherit all methods from Animal
Bird.prototype = Object.create(Animal.prototype);

// Bird.eat() overrides Animal.eat()
Bird.prototype.eat = function() {
  return "peck peck peck";
};
```

>If you have an instance let duck = new Bird(); and you call duck.eat(), this is how JavaScript looks for the method on duck’s prototype chain:
>1. duck => Is eat() defined here? No.
>1. Bird => Is eat() defined here? => Yes. Execute it and stop searching.
>1. Animal => eat() is also defined, but JavaScript stopped searching before reaching this level.
>1. Object => JavaScript stopped searching before reaching this level.
