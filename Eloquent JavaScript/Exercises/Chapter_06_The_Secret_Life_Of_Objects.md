# Chapter 6 -- The Secret Life of Objects

Note from Cam: For brevity's sake I'm simply going to put my solutions to the following exercises here. For explanations of what each exercise entails, please refer to the [free online version of this chapter here](https://eloquentjavascript.net/06_object.html).

Here are my solutions for this chapter's exercises.

---

## A vector type

**My solution**

```
class Vec {
 constructor(x, y) {
 this.x = x;
 this.y = y;
 }
 plus(vector) {
 const x = vector.x + this.x;
 const y = vector.y + this.y;
 return {x, y}
 }
 minus(vector) {
 const x = this.x - vector.x
 const y = this.y - vector.y
 return {x, y}
 }
 get length() {
 return Math.sqrt((this.x**2)+ (this.y**2))
 }
}

const vec1 = new Vec(1,2)
const vec2 = new Vec(10, 20);
vec1.plus(vec2)
```

**Thoughts**:

This exercise took some time because it was the first time I'd ever written a class in JavaScript.

Although I had to refer to the book several times to get the syntax correct, I found creating the class and adding the plus and minus methods pretty straightforward.

Adding the getter method required a bit more time, however as I needed several minutes to research and remember how to use the formula for calculating the distance between two coordinate pairs (something I haven't done for nearly 10 years!)

In the end, however, I was able to solve this problem entirely on my own. In the process I became more comfortable with the basics of classes in JavaScript and I also learned that we can use \*\* as an alternative to Math.pow() to work with exponents in JavaScript!

The only thing I missed in this exercise was that the author wanted me to return a new vector from the plus and minus methods.

As such, I should've written:

```
return new Vec(x, y)
```

in my two function rather than simply returning an object with the specified coordinates. In any case, I still feel I did a mostly good job with this exercise! :D

---

## Groups

**My solution**

```
class Group {
  constructor(array) {
  this.group = array;
  }
  add(value) {
    if (this.group.indexOf(value) > -1) {
      return
    } else {
      this.group.push(value)
    }
  }
  delete(value) {
    this.group = this.group.filter((item) => item !== value )
  }
  has(value) {
    return this.group.indexOf(value) > -1 ? true : false
  }

  static from(array) {
  return new Group(array);
  }
}
```

**Thoughts:**

While solving this problem I learned that a static method in JavaScript is a method that can be created using the _static_ keyword. Static methods cannot be called on instances of a class.

They can only be called on the class itself. In addition, static methods do not require any instances of the class to be created before they are able to be called.

It took me a minute or two to think about how to use the _from_ method and constructor together to initialize new instantiations of the _Group_ class. Once I got that part, the rest of this problem was pretty smooth sailing.

I feel my solution would be very readable to other devs. I'm starting to get a lot more comfortable with the basics of using classes in JavaScript (though being honest, I still haven't thought of many cases where I'd actually use them).

The author's solution was pretty similar to mine. I would say their usage of _includes()_ is slightly more concise and readable than my usage of _indexOf()_. Overall, however, I feel we did a really good job with this exercise. On to the next one!

---

## Iterable groups

**My solution:**
Err... Uhhhh...

**Thoughts:** I was completely lost on this problem. I understand the concept of something being iterable, but I didn't know where to start. Well, actually I did. The only problem was I intended to use thethe Symbol.Iterator on my array which is exactly what they said _not_ to do :(.

Given that restraint, I got pretty stuck on this problem.

---

## Borrowing a Method

**My solution:**

```
console.log(Object.prototype.hasOwnProperty.call(map, 'one'))
```

**Thoughts:** It took me several iterations during the solution process before I realized I had to use JavaScript's _call()_ method to solve this problem.

I now understand that this could theoretically be useful in the case that we want to call one object's method on another object.

I'm still not sure when we'd use this in any real world case scenario, however. In any case, this problem did familiarize me with the _call()_ a method I'd never used before.
