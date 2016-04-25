#Redux

### Principles
- State changes are made by dispatching `actions`. State can't be modified any other way.


### Pure functions

- Functions that take input only from its parameters, and return a result.
- Doesn't have any side effects (e.g. doesnt modify a database, or change state of the app).
- Use `.map` over `.forEach` so as not to overwrite original array.
