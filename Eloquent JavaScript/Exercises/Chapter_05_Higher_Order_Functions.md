# Chapter 5 Higher-Order Functions Exercises

Note from Cam: For brevity's sake I'm simply going to put my solutions to the following exercises here. For explanations of what each exercise entails, please refer to the [free online version of this chapter here](https://eloquentjavascript.net/05_higher_order.html).

I really enjoyed the exercises in this chapter. They were challenging, and I had to stretch myself to solve them.

Even with that being the case, however, I felt confident with these problems that if I put in the time and effort I would eventually be able to come up with solutions.

And my feelings were mostly right! Here are my solutions for this chapter's exercises.

---

## Flattening

**My solution**

```
const twoDimendionalArray = [
 [1, 2],
 [3, 4],
 [5, 6]
];

twoDimendionalArray.reduce((total, item) => {
 return total.concat(item)
})
```

Thoughts: I overestimated this problem. My first impression was that this problem was going to be somewhat complicated, but I solved it in all of three minutes.

---

## Your Own Loop

**My solution**

```
const loop = (value, testFunc, updateFunc, bodyFunc) => {
  for (let i = value; testFunc(i); i = updateFunc(i)) {
   bodyFunc(i)
 }
}
const exampleTestFunc = (value) => {
if (value > 5) {
  return false;
}
return true;
}
const exampleBodyFunc = (value) => {
}
const exampleUpdateFunc = (value) => {
return value + 1
}

loop(1, exampleTestFunc, exampleUpdateFunc, exampleBodyFunc)
```

Thoughts: While I was working on this problem, I didn't find it very interesting. In retrospective, however, it was interesting to use function calls inside of the 2nd and 3rd statements in my for loop. I'm not sure I had ever done that before this exercise.

---

## Everything

**My solution**

const everyByLooping = (array, test) => {
for (let i = 0; i < array.length; i+=1) {
if (!test(array[i])) {
return false;
}
}
return true
}

const everyViaSome = (array, test) => {
return !array.some(test);
}

**Thoughts:** I found implementing the first every method to be quite simple. Implementing every using the some method was much more difficult, however. My first thought was to check the inverse method of my test function or to simply return:

> !array.some(test)
> This obviously doesn't work, however, because there are many cases in which the some method may naturally produce the same boolean as the every method.

After a bit more research I discovered the some method has an optional _thisArg_ argument. I thought this may be the key, but later figured _thisArg_ probably wasn't going to help me much.

In the end, it turns out I was almost right at the beginning. If I would've combined my two initial ideas using a callback function with _some_ I would've seen success. Oh well, this problem stretched my thinking.

I've grown from this problem and will be more ready for similar problems in the future which I guess is the most important thing :D

---

## Dominant Writing Direction

**My solution**

```
function dominantDirection(text) {
  let isValueAtCodePoint = true;
  let dominantDirectionCount = {ltr: 0, rtl: 0, ttb: 0}
	 for (let i = 0; isValueAtCodePoint; i+=1) {
  if (text.codePointAt(i)) {
    	let scriptItem = characterScript(text.codePointAt(i))
        if (scriptItem && scriptItem.direction) {
          dominantDirectionCount[scriptItem.direction] = dominantDirectionCount[scriptItem.direction] + 1
        }
      }
       else {
         isValueAtCodePoint = false
		}
	}
  return Object.keys(dominantDirectionCount).reduce((a, b) => {
    return dominantDirectionCount[a] > dominantDirectionCount[b] ? a : b
  })
}
```

**Thoughts:** This problem was challenging for a couple reasons. At least half of the challenge was figuring out what I did and didn't have to work with. I didn't realize that my job was to calculate the writing direction based on the SCRIPTS array that the author provided on their website.

As such, I spent a while searching Google for how to find a script's writing direction based on the value returned from charCodeAt(). I obviously didn't get very far.

Once I figured this out, I then consulted the earlier pages to see how the characterScript() and countBy() functions were implemented by the author.

I thought my job was to implement them from scratch hahaha. I thought the author's note that they'd be useful was simply implying I should use them as a resource to write my own code -- not that his functions would actually work in the code sandbox on his website.

In any case, once I realized I could use his functions I wrote some pseudocode that looked something like this:

```
function dominantDirection(text) {
  let isValueAtCodePoint = true;
  let dominantDirectionCount = {ltr: 0, rtl: 0, ttb: 0}
	 for (let i = 0; isValueAtCodePoint; i+=1) {
  if (text.codePointAt(i)) {
       console.log(text.codePointAt(i))
    // I now have the unicode.

    // I need to somehow go through the SCRIPTS array, and see if the unicode falls
    // into any of the ranges for a given item.

    // Then, I need to take the value of that script item's direction property.

    // I'll then use the value to increment the value of the corresponding key's value
    // in my dominantDirectionCount variable.

    // I'll repeat this process until my isValueAtCodePoint variable has a value of false.

    // I'll then break out of my loop and determine which key to return using the
    // following function: Object.keys(myObj).reduce((a, b) => myObj[a] > myObj[b] ? a : b)
    console.log(SCRIPTS)
      }
       else {
         isValueAtCodePoint = false
		}
	}
}
```

That pseudocode should give you a good overview of my thought process for solving this problem.

---

## Conclusion

These were some great challenges. I hope the rest of the book gradually ramps up the difficulty level from here so I can continue to be challenged as my skills grow! :D
