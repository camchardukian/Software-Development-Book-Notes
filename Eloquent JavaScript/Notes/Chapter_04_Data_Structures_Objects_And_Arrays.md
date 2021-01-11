# Chapter 4 -- Data Structures: Objects and Arrays

## Data Sets

Being a full-time software developer I obviously understand the concept of [zero-based numbering](https://en.wikipedia.org/wiki/Zero-based_numbering). I remember, however, that this concept wasn't so simple when I first started learning how to code.

This section offers a great way of explaining zero-based numbering to beginners. It says we can think of the index as the number of items to skip starting from the beginning of the array.

## Properties

If we try to access a property on _null_ or _undefined_ we will receive an error. Most other values in JavaScript _do_ have properties though. For example, strings have the _length_ property.

There are some differences between _dot notation_ and _bracket notation_. For one, _dot notation_ attempts to access the literal name of a property.

_Bracket notation_ works by evaluating the expression we nest inside of the brackets. It then uses that value, converts it to a string, and uses that string to attempt to access our property.

Another key difference is that we are only able to use valid variable names when using _dot notation_.

## Methods

Both string and array values contain a number of properties that hold function values. For strings think _.toUpperCase()_, _.toLowerCase()_, etc. For arrays think _.push()_, _.pop()_, etc.

## Objects

It seems like using the _delete_ keyword on an object works exactly how one would expect it to work. Yet, while testing some concepts in this section, I found that using the _delete_ keyword with arrays can result in some unexpected behaviors.

For example, if we have an array like so:

```
const myArray = [1, 2, 3, 4, 5]
```

We would expect myArray to have a length of 5. Next, let's look to see what happens when we use the _delete_ keyword on this array.

```
delete myArray[2]
--> returns [1, 2, undefined, 4, 5]
```

That's right, it looks like "deleting" an item from an array doesn't actually delete it. It seems to me that "deleting" an item merely replaces its value with undefined.

Our _myArray_ still has a length of 5 and all of the values can still be accessed at the same index they were previously located at (except of course the "deleted" value).

_End of my rant ;))_

Back to objects... We can use the _in_ keyword to see if an object has a property/key with a given name. Here's code to illustrate the difference between using the _in_ keyword and evaluating the property's value using dot notation...

```
const cameronObj = {
  firstName: "Cameron",
  lastName: "Chardukian",
  tribalName: undefined,
}
if (cameronObj.tribalName) {
  // this block does not run.
} else if ("tribalName" in cameronObj) {
  // this block DOES run.
}
```

## Mutability

When we declare a variable with _const_ we are not able to change which object our variable is binded to. We CAN change the contents of the object being pointed to though.
When comparing objects with JavaScript's _==_ operator JavaScript evaluates whether both objects have the same identity. Objects with identical properties but different identities will return _false_.
JavaScript does not have a "deep comparison" method built into it. It is possible to write such a function ourselves though.

## Future Arrayology

The _.indexOf()_ method returns the first occurrence of a value while the _.lastIndexOf()_ method returns the last occurence of a value.
We can use the _.concat()_ method to combine two arrays into a single array. Here's an example I wrote demonstrating this:

```
const arrayOne = [1, 'one']
const arrayTwo = [2, 'two']
const arrayThree = arrayOne.concat(arrayTwo)
console.log(arrayThree)
// [1, 'one', 2, 'two'] is logged to the console.
```

## Strings and Their Properties

Key quote here from this section...

> "Values of type string, number, and Boolean are not objects, and though the language doesn't complain if you try to set new properties on them, it doesn't actually store those properties. As mentioned earlier, such values are immutable and cannot be changed."

Here are some methods I didn't previously know strings had:

- .slice() --> basically the same as the .slice() method for arrays.
- .padStart() --> A method which pads the beginning of our string with a string passed as an argument until our original string reaches the number of characters passed to this function.
- .padEnd() --> The same as _.padStart_ except this functions pads the end of our string.
- .repeat() --> A method which takes a number as an argument as the number of times the string should be repeated.

## Destructuring

Trying to destructure _null_ or _undefined_ will result in an error.

## JSON

JSON.stringify() takes a JavaScript value and returns a JSON-encoded string. JSON.parse() takes a JSON-encoded string and converts it into a JavaScript value.
