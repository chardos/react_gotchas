#Redux

### Principles
- State changes are made by dispatching `actions`. State can't be modified any other way.
- Next state = Previous state + action

### Pure functions

- Functions that take input only from its parameters, and return a result.
- Doesn't have any side effects (e.g. doesnt modify a database, or change state of the app).
- Use `.map` over `.forEach` so as not to overwrite original array.

### Reducer

- Reducer is a function that takes the **previous state** of the app, applies the **action**, and returns the **next state** of the app

### The immutable way of doing things

#### Adding an item to an array
```js
var addCounter = (list) => {
  return [...list, 0]
}
```

#### Removing an item from an array
```js
var removeCounter = (list, index) => {

  return [
    ...list.slice(0, index),
    ...list.slice(index+1)
  ]
}
```
