# ![Intro to JavaScript Objects - Methods](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to create methods and understand prototyping and inheritance.

When a property holds a function, we commonly refer to it as a **method** of the object.

So, simply put, you can think of a method as a function which exists on an object. 

They can be defined when initializing an object:

```javascript
const music = {
  currentTrack: 'Just Ken',
  currentPlaylist: ['Just Ken', 'Hey Blondie', 'What Was I Made For', 'Dance The Night'],
  volume: 70, 
  // add the following: 
  mute: () => {
    music.volume = 0
  }
}
```

You could also use dot notation assignment to define the same method: 

```javascript
music.mute = () => {
  music.volume = 0
}
```

We invoke methods the same way we invoke functions, just remember that the method only exists on the object: 

```javascript
mute();
// reference error
```

```javascript
music.mute();
// works! 
```

At this point, you'll likely have realized that we've already experienced methods up to this point - when we use things like `.push()` or `.slice()`, we're invoking an array __method__. If we call `'some string'.split()`, we're invoking a string __method__. 

If you have been wondering why we use dot notation to call upon these functions, now you know why! 

## Adding a `next()` method

Let’s add a `next` *method* to the `music` object, so we can move to the next track in our `currentPlaylist`. 

One problem - how do we do that? The way our object is currently set up, we have a `currentTrack` property, and a `currentPlaylist` property, but no way to easily determine our current position in the playlist. 

Let's make one adjustment. It doesn't make much sense to keep track of `currentTrack` as a string, when the entire playlist we're working with already keeps track of our song names in an array.

Remember, we can access a specific item in an array using its index, so let's add a property called `trackIdx` that represents the current tracks index: 

```javascript
const music = {
  trackIdx: 0,
  currentPlaylist: ['Just Ken', 'Hey Blondie', 'What Was I Made For', 'Dance The Night'],
  volume: 70, 
};
```

Now we can dynamically access the current track by accessing the `trackIdx` of the `currentPlaylist`: 

```javascript
console.log(music.currentPlaylist[music.trackIdx]); // 'Just Ken'
```

Now, for our `next()` method, we can simply increment the `trackIdx` by `1`! 

```javascript
music.next = () => {
  music.trackIdx += 1
}
```

```javascript
// invoke the method
music.next();

console.log(music.currentPlaylist[music.trackIdx]); // 'Hey Blondie'
```