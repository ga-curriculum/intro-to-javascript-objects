# Intro to JavaScript Objects - Methods

![Hero image](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to create methods and understand prototyping and inheritance.

## What are methods? 

When a property holds a function, we commonly refer to it as a **method** of the object.

So, simply put, you can think of a method as a function which exists on an object. 

Let’s add a `play` *method* to the `game` object:

```jsx
game.play = function() {
  game.secretNum = Math.floor(Math.random() * 
    (game.biggestNum - game.smallestNum + 1)) + game.smallestNum
}
```

At this point, you'll likely have realized that we've already experienced methods up to this point - when we use things like `.push()` or `.slice()`, we're invoking an array __method__. If we call `'some string'.split()`, we're invoking a string __method__. 

If you have been wondering why we use dot notation to call upon these functions, now you know why! 
