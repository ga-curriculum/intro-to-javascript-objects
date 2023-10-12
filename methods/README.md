# Intro to JavaScript Objects - Methods

![Hero image](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to create methods and understand prototyping and inheritance.

## What are methods? 

When a property holds a function, we commonly refer to it as a **method** of the object.

So, simply put, you can think of a method as a function which exists on an object. 

They can be defined when initializing an object:

```javascript
const music = {
  currentTrack: 'Just Ken',
  currentPlaylist: ['Just Ken', 'Hey Blondie', 'What Was I Made For', 'Dance The Night'],
  volume: 70, 
  // add the following: 
  mute(){
    music.volume = 0
  }
}
```

You could also use dot notation assignment to define the same method: 

```javascript
music.mute = function(){
  music.volume = 0
}
```

We invoke methods the same way we invoke functions, just remember that the method only exists on the object: 

```javascript
mute()
// reference error
```

```javascript
music.mute() 
// works! 
```

At this point, you'll likely have realized that we've already experienced methods up to this point - when we use things like `.push()` or `.slice()`, we're invoking an array __method__. If we call `'some string'.split()`, we're invoking a string __method__. 

If you have been wondering why we use dot notation to call upon these functions, now you know why! 

## Adding a next() method

Let’s add a `next` *method* to the `music` object, so we can move to the next track in our `currentPlaylist`. 

One problem - how do we do that? The way our object is currently set up, we have a `currentTrack` property, and a `currentPlaylist` property, but no way to easily determine our current position. 

Let's make one adjustment. It doesn't make much sense to keep track of `currentTrack` as a string, when the entire playlist we're working with already keeps track of our song names in an array.

Remember, we can access a specific item in an array using its index, so let's add a property called `position` that represents the current tracks index: 

```javascript
const music = {
  position: 0,
  currentPlaylist: ['Just Ken', 'Hey Blondie', 'What Was I Made For', 'Dance The Night'],
  volume: 70, 
}
```

Now we can dynamically access the current track by accessing the `position` of the `currentPlaylist`: 

```javascript
console.log(music.currentPlaylist[music.position]) // 'Just Ken'
```

Now, for our `next()` method, we can simply increment the `position` by `1`! 

```javascript
music.next = () => {
  music.position += 1
}
```

```javascript
// invoke the method
music.next()

console.log(music.currentPlaylist[music.position]) // 'Hey Blondie'
```

## Objects and arrays

As you've seen, objects excel at grouping related data, and arrays are great for storing multiple ordered items. As a result, data is often structured using a combination of both! 

Let's examine our current `music.currentPlaylist`: 

```javascript
['Just Ken', 'Hey Blondie', 'What Was I Made For', 'Dance The Night']
```

It would be nice if each song had more associated data - the artist, album, song length, etc. This is a great use case for an object, something like: 

```javascript
{ 
  title: 'Just Ken',
  artist: 'Ryan Gosling',
  album: 'Barbie The Album',
  length: '3:43',
}
```

If we adopted that structure for each song our `currentPlaylist` array would resemble something like this, an array of objects: 
```javascript
music.currentPlaylist = [
  {
    title: 'Just Ken',
    artist: 'Ryan Gosling',
    album: 'Barbie The Album',
    length: '3:43',
  }, {
    title: 'Hey Blondie',
    artist: 'Dominic Fike',
    album: 'Barbie The Album',
    length: '2:21',
  }, {
    title: 'What Was I Made For',
    artist: 'Billie Eilish',
    album: 'Barbie The Album',
    length: '3:42',
  }, {
    title: 'Dance The Night',
    artist: 'Dua Lipa',
    album: 'Barbie The Album',
    length: '2:56',
  }
]
```

We can still access each element the same way as before, but now they are objects rather than strings: 

```javascript
console.log(music.currentPlaylist[music.position])
// { title: 'Just Ken', artist: 'Ryan Gosling', album: 'Barbie The Album',length: '3:43' }
```

That means we can use dot notation to return specific properties on that element! 

```javascript
console.log(music.currentPlaylist[music.position].title) // 'Just Ken'
console.log(music.currentPlaylist[music.position].artist) // 'Ryan Gosling'
```





