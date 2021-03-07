# Chapter 8 -- Bugs And Errors

Note from Cam: For brevity's sake I'm simply going to put my solutions to the following exercises here. For explanations of what each exercise entails, please refer to the [free online version of this chapter here](https://eloquentjavascript.net/08_error.html).

Here are my solutions for this chapter's exercises.

---

## Retry

**My solution:**

My first attempt at solving this problem used recursion and looked like this:

```
class MultiplicatorUnitFailure extends Error {}
function primitiveMultiply(a, b) {
  if (Math.random() < 0.2) {
    return a * b;
  } else {
    throw new MultiplicatorUnitFailure("Klunk");
  }
}
function reliableMultiply(a, b) {
  let product;
  try {
  product = primitiveMultiply(a, b)
    return product;
  }
  catch {
    reliableMultiply(a, b)
  }
}
```

The above attempt didn't work, however, so I devised another solution that instead relied on looping:

```
function primitiveMultiply(a, b) {
  if (Math.random() < 0.2) {
    return a * b;
  } else {
    throw new MultiplicatorUnitFailure("Klunk");
  }
}
function reliableMultiply(a, b) {
  for (;;) {
  try {
  const product = primitiveMultiply(a, b)
  return product;
  }
  catch (e) {
    if (e instanceof MultiplicatorUnitFailure) {
      console.log('primitivee failed')
    }
    else {
      throw e;
    }
  }
  }
}
```

**Thoughts**: I thought this was a great exercise for learning how the _instanceof_ operator can help us to selectively catch errors in JavaScript.

---

## The Locked Box

**My solution:**

Coming soon...
