# Intro to JavaScript Objects - Manipulation

![Hero image](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will understand the basics of manipulating objects, such as changing and deleting properties.

## Changing an object's properties

To change an object's properties, you can reassign a new value to an existing key: 

```javascript
const music = {
  currentTrack: 'Just Ken',
  currentPlaylist = ['Hey Blondie', 'What Was I Made For', 'Dance The Night']
  volume: 70, 
}

// Let's lower the volume: 
music.volume = 60;

console.log(music.volume) // 60
```

## Deleting an object's properties

To completely remove a property from an object, we use the delete operator:

```javascript
const music = {
  currentTrack: 'Just Ken',
  currentPlaylist = ['Hey Blondie', 'What Was I Made For', 'Dance The Night']
  volume: 70, 
}

// Let's remove our current playlist: 
delete music.currentPlaylist


console.log(music)
// { currentTrack: 'Just Ken', volume: 70 }
```




