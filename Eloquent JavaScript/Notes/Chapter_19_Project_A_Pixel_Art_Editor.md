# Chapter 19 -- Project: A Pixel Art Editor

One of the main benefits of JS frameworks is that they’ve already set up the infrastructure for parent components notifying child parents whenever the parent state changes.

The two snippets of code below are functionally the same:

```
// #1 Object.assign({}, state, action);
// #2 {...state, ...action}
```

If a component doesn’t understand the application state outside of itself, it’s not wise for that component to be able to directly dispatch actions. Instead, the component should call a callback function provided by the code that created the component.
