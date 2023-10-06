# Intro to JavaScript Objects - Methods

![Hero image](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to create methods. 

When a property holds a function, we commonly refer to it as a **method** of the object.

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

The `this` keyword represents the “execution context” of a function. In this case, `this` is set by JavaScript to be the object the method is called on. We will have a dedicated lesson on `this` soon.

**IMPORTANT:** Due to how `this` is set within *arrow functions*, it’s best to avoid using them as methods in objects.