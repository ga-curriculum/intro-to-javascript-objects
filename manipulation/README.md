# ![Intro to JavaScript Objects - Manipulation](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will understand the basics of manipulating objects, such as changing and deleting properties.

## Changing an object's properties

To change an object's properties, you can reassign a new value to an existing key. When using the assignment operator, if a property doesn’t exist, it is created; otherwise, it’s updated:

```javascript
const music = {
  currentTrack: 'Just Ken',
  currentPlaylist: ['Just Ken', 'Hey Blondie', 'What Was I Made For', 'Dance The Night'],
  volume: 70, 
}

// Let's lower the volume: 
music.volume = 60;

console.log(music.volume) // 60
```

In this example, `volume` already exists as a property on `music` so this line of code updates the value.

## Deleting an object's properties

To completely remove a property from an object, we use the delete operator:

```javascript
const music = {
  currentTrack: 'Just Ken',
  currentPlaylist: ['Just Ken', 'Hey Blondie', 'What Was I Made For', 'Dance The Night'],
  volume: 70, 
}

// Let's remove our current playlist: 
delete music.currentPlaylist

console.log(music)
// { currentTrack: 'Just Ken', volume: 70 }
```