# Intro to JavaScript Objects - Manipulation

![Hero image](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to change and delete properties from an object. 

## Changing an object's properties

To change an object's properties, you can reassign a new value to an existing key: 

```javascript
const tastyIceCreamFlavors = {
  vanilla: true,
  chocolate: true,
  mintChip: true,
}

// If someone comes along who doesn't like mint chip ice cream: 
tastyIceCreamFlavors.mintChip = false

console.log(tastyIceCreamFlavors) 
// { vanilla: true, chocolate: true, mintChip: false }
```

## Deleting an object's properties

To completely remove a property from an object, we use the delete operator:

```javascript
const tastyIceCreamFlavors = {
  vanilla: true,
  chocolate: true,
  salmon: false
}

// Let's remove salmon entirely: 
delete tastyIceCreamFlavors.salmon


console.log(tastyIceCreamFlavors)
// { vanilla: true, chocolate: true }
```




