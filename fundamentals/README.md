# Intro to JavaScript Objects - Fundamentals

![Hero image](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to tktk

## Object literal notation

Let’s create an object by using **Object Literal** notation, also known as an [Object Initializer](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Object_initializer):

```javascript
const game = {}
console.log(typeof game) // "object"
```

As you can see, Object Literal notation consists of a set of opening and closing curly braces, `{}`. We just used curly braces to create an empty game object.

Let’s change the code so that `game` has a property:

```javascript
const game = { title: 'Guess the Number!' }
console.log(game)
```

Properties are separated by commas:

```javascript
const game = {
  title: 'Guess the Number!',
  biggestNum: 100
}
```

Syntactically, [trailing commas](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Trailing_commas) are permitted and encouraged:

```javascript
const game = {
  title: 'Guess the Number!',
  biggestNum: 100, // <---
}
```

Why? Check out [this commit](https://github.com/DavidStinson/objects-are-a-thing/commit/b1bb58d364975e3dbed12f4c9726720ded2a3cfd) for a look into how this looks to version control software when modified. It’s also just straight up less work later!


## Accessing with dot notation

## Using square bracket notation

