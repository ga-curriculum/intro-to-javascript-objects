# Intro to JavaScript Objects - Methods

![Hero image](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to create methods. 

## What are methods? 

When a property holds a function, we commonly refer to it as a **method** of the object.

So, simply put, you can think of a method as a function which exists on an object. 

Let’s add a `play` *method* to the `game` object:

```jsx
game.play = function() {
  this.secretNum = Math.floor(Math.random() * 
    (this.biggestNum - this.smallestNum + 1)) + this.smallestNum
}
```

Try it out in the console by calling `game.play()` and then checking the value of `game.secretNum` a few times. 

## this

So what’s with the `this`?

The `this` keyword represents the “execution context” of a function. In this case, `this` is set by JavaScript to be the object the method is called on. 

**IMPORTANT:** Due to how `this` is set within *arrow functions*, it’s best to avoid using them as methods in objects.

## Prototyping and Inheritance

At this point, you'll likely have realized that we've already experienced methods up to this point - when we use things like `.push()` or `.slice()`, we're invoking an array __method__. If we call `'some string'.split()`, we're invoking a string __method__. 

If you have been wondering why we use dot notation to call upon these functions, now you know why - they're methods that are built into the [object prototypes](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Object_prototypes) for each of these types. 

To understand how we're able to access these methods, it's important to understand that, in JavaScript, anything which is not a primitive value (string, number, bigint, boolean, undefined, symbol, or null) is an object. 

**Prototypes** are how JavaScript objects inherit features from one another. Every object in JavaScript has a built-in property called its prototype, and this prototype itself is an object so it has its own prototype as well (it's prototypes all the way down!)

This creates a chain of prototypes. Whenever you access a method on an object (for example, an array), the JavaScript engine searches up this chain to try and find the method. This is how a new array you just created: 

```javascript
const myArray = [1, 2, 3, 4, 5]

myArray.join(' - ') // returns: 1 - 2 - 3 - 4 - 5
```

can still make use of an array method like `.join()`. It is inheriting these methods from the `Array.prototype` object. 

> 🧠 You may have noticed that methods on MDN always have a title syntax like 'Array.prototype.forEach' or 'Number.prototype.

<br>

So, what about the primitive values? We learned earlier that these are not objects, so how come we can still call methods on numbers, for instance?

Under the hood, the JavaScript engine converts any primitive value to the equivalent type object, which is why strings, despite not being objects, can inherit string methods like `.split()`, `length`, etc. When you create a new `string` and assign it to a variable, that variable will become a string object instance, which has its own prototypes and methods associated with it. 

Prototyping and inheritance are the mechanisms by which, almost like magic, we are able to access a number of pre-written methods to help us perform typical tasks with the various types of data we encounter in JavaScript!



