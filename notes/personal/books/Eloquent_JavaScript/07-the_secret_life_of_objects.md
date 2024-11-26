# The secret life of objects

> "An abstract data type is realized by writing a special kind of program \[…\] which defines the type in terms of the operations which can be performed on it." - Barbara Liskov, Programming with Abstract Data Types.

## Abstract data types

Each abstract data type has an **interface**, the collection of operations that external code can perform on it. Any details beyond that interface are **encapsulated**, treated as internal to the type and of no concern to the rest of the program.

## Methods

```JS
function speak(line) {
    console.log(`The ${this.type} rabbit says "${line}"`)
}
let white_rabbit = { type: "white", speak }
let hungry_rabbit = { type: "hungry", speak }

white_rabbit.speak("Oh my fur and whiskers") // The white rabbit says "Oh my fur and whiskers"
hungry_rabbit.speak("Got any carrots?") // The hungry rabbit says "Got any carrots?"
```

Since each function has its own `this` whose value depends on the way it is called, you cannot refer to the `this` of the wrapping scope in a regular function defined with the function keyword.

Arrow functions are different, they do not bind their own `this` but can see the `this` binding of the scope around them. Thus, you can do something like the following code, which references this from inside a local function:

```JS
let finder = {
    find(array) {
        return array.some(v => v == this.value)
    },
    value: 5
}
console.log(finder.find([4, 5])) // true
```

## Prototypes

When an object gets a request for a property that it does not have, its prototype will be searched for the property. If that does not have it, the prototype's prototype is searched, and so on until an object without prototype is reached (`Object.prototype`).

You can use `Object.create` to create an object with a specific prototype:

```JS
let rabbit_prototype = {
    speak(line) {
        console.log(`The ${this.type} rabbit says "${line}"`)
    }
}
let black_rabbit = Object.create(rabbit_prototype)
black_rabbit.type = "black"
black_rabbit.speak("I am fear and darkness") // The black rabbit says "I am fear and darkness"
```

## Classes

JavaScript's prototype system can be interpreted as a somewhat free-form take on abstract data types or classes. A **class** defines the shape of a type of object, what methods and properties it has. Such an object is called an **instance** of the class.

JavaScript's class notation makes it easier to define this type of function, along with a prototype object.

```JS
class Rabbit {
    constructor(type) {
        this.type = type
    }
    speak(line) {
        console.log(`The ${this.type} rabbit says "${line}"`)
    }
}
```

The `class` starts a class declaration, which allows us to define a constructor and a set of methods together. Any number of methods may be written inside the declaration's braces.

This function cannot be called like a normal function. Constructors, in JavaScript, are called by putting `new` in front of them. Doing so creates a fresh instance object whose prototype is the object from the function's prototype property, then runs the function with `this` bound to the new object, and finally returns the object.

Like `function`, `class` can be used both in statements and in expressions. When used as an expression, it does not define a binding but just produces the constructor as a value. You are allowed to omit the class name in a class expression.

```JS
let object = new class { get_word() { return "hello" } }
console.log(object.get_word()) // hello
```

## Private properties

To declare a private method, put a `#` in front of its name. Such methods can be called only from inside the class declaration that defines them.

## Overriding derived properties

Overriding is also used to give the standard function and array prototypes a different `toString` than the basic object prototype.

```JS
console.log(Array.prototype.toString ==
            Object.prototype.toString) // false

console.log([1, 2].toString()) // 1,2
```

## Maps

A **map** (noun) is a data structure that associates values (the keys) with other values.

For this reason, using plain objects as maps is dangerous. There are several possible ways to avoid this problem. First, you can create objects with no prototype. If you pass null to Object.create, the resulting object will not derive from Object.prototype and can be safely used as a map.

> The reason refers to the fact of calling unwanted keys of the objects (key that you did not declare).

```JS
console.log("toString" in Object.create(null)) // false
```

Object property names must be strings. If you need a map whose keys cannot easily be converted to strings (such as objects) you cannot use an object as your map.

Fortunately, JavaScript comes with a class called "Map" that is written for this exact purpose. It stores a mapping and allows any type of keys.

```JS
let ages = new Map()
ages.set("Boris", 39)
ages.set("Liang", 22)
ages.set("Júlia", 62)

console.log(`Júlia is ${ages.get("Júlia")}`)// Júlia is 62
console.log("Is Jack's age known?", ages.has("Jack")) // Is Jack's age known? false
console.log(ages.has("toString")) // false
```

If you do have a plain object that you need to treat as a map for some reason, it is useful to know that `Object.keys` returns only an object's own keys, not those in the prototype. As an alternative to the `in`, you can use the `Object.hasOwn`, which ignores the object's prototype.

```JS
console.log(Object.hasOwn({ x: 1 }, "x")) // true
console.log(Object.hasOwn({ x: 1 }, "toString")) // false
```

## Polymorphism

...Polymorphic code can work with values of different shapes, as long as they support the interface it expects.

## Symbols

...Symbols are values created with the Symbol function. Unlike strings, newly created symbols are unique...

```JS
let symbol = Symbol("name")
console.log(symbol == Symbol("name")) // false
```

The string you pass to Symbol is included when you convert it to a string and can make it easier to recognize a symbol...

Being both unique and usable as property names makes symbols suitable for defining interfaces that can peacefully live alongside other properties, no matter what their names are.

```JS
const length = Symbol("length")
Array.prototype[length] = 0

console.log([1, 2].length) // 2
console.log([1, 2][length]) // 0
```

It is possible to include symbol properties in object expressions and classes by using square brackets around the property name. That causes the expression between the brackets to be evaluated to produce the property name...

```JS
let my_trip = {
    length: 2,
    0: "Lankwitz",
    1: "Babelsberg",
    [length]: 21500
}
console.log(my_trip[length], my_trip.length) // 21500 2
```

## The iterator interface

The object given to a for/of loop is expected to be iterable. This means it has a method named with the `Symbol.iterator` symbol...

When called, that method should return an object that provides a second **interface**, iterator. This is the actual thing that iterates. It has a `next` that returns the next result. That result should be an object with a value property that provides the next value, if there is one, and a "done" property, which should be true when there are no more results and false otherwise.

## Inheritance

Whereas encapsulation and polymorphism can be used to **separate** pieces of code from one another, reducing the tangledness of the overall program, inheritance fundamentally ties classes together, creating **more** tangle. When inheriting from a class, you usually have to know more about how it works than when simply using it. Inheritance can be a useful tool to make some types of programs more succinct, but it shouldn’t be the first tool you reach for, and you probably shouldn’t actively go looking for opportunities to construct class hierarchies (family trees of classes).
