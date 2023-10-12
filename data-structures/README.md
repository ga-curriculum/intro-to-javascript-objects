# Intro to JavaScript Objects - Data Structures

![Hero image](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to understand how objects and arrays combine to form common data structures.

As a reference, here is our `music` object: 

```javascript
const music = {
  position: 0,
  currentPlaylist: ['Just Ken', 'Hey Blondie', 'What Was I Made For', 'Dance The Night'],
  volume: 70,
  next(){
    music.position += 1
  },
};
```

As you've seen, objects excel at grouping related data, and arrays are great for storing multiple ordered items. As a result, data is often structured using a combination of both! 

Let's examine our current `music.currentPlaylist`: 

```javascript
['Just Ken', 'Hey Blondie', 'What Was I Made For', 'Dance The Night']
```

In a real world application, each song would likely have more associated data - an artist, album, song length, etc. This is a great use case for an object, something like: 

```javascript
{ 
  title: 'Just Ken',
  artist: 'Ryan Gosling',
  album: 'Barbie The Album',
  length: '3:43',
}
```

If we adopted that structure for each song, then our `currentPlaylist` array would resemble something like this, an array of objects: 
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

That means we can now use dot notation to return specific properties on that element! 

```javascript
console.log(music.currentPlaylist[music.position].title) // 'Just Ken'
console.log(music.currentPlaylist[music.position].artist) // 'Ryan Gosling'
```




