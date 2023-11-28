# ![Intro to JavaScript Objects - Level Up - Property Shorthand Syntax](./assets/hero-property-shorthand-syntax.png)


**Learning objective:** By the end of this lesson, students will be able to utilize ES6 Property Shorthand syntax to succinctly assign variables as object properties when the property names match the variable names.

It’s a common scenario to want to pass the values of variables as properties (having the same name as the variable) in an object:

```javascript
const latitude = getLat('Disneyland')
const longitude = getLng('Disneyland')

const location = {
  name: 'Disneyland',
  latitude: latitude,
  longitude: longitude,
}
```

Thanks to ES2015’s Property Shorthand syntax, we can do this:

```javascript
const latitude = getLat('Disneyland')
const longitude = getLng('Disneyland')

const location = {
  name: 'Disneyland',
  latitude,
  longitude,
}
```

The variable name determines the name of the property.