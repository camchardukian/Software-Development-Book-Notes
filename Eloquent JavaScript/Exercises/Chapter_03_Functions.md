# Chapter 3 Functions Exercises

Note from Cam: For brevity's sake I'm simply going to put my solutions to the following exercises here. For explanations of what each exercise entails, please refer to the [free online version of this chapter here](https://eloquentjavascript.net/03_functions.html).

## Minimum

**My solution**

```
const returnMinArgument = (x, y) => {
  if (typeof x === 'number' && typeof y !== 'number' ) {
    return x;
} else if (typeof y === 'number' && typeof x !== 'number') {
  return y;
} else {
    if (typeof x === 'number' && typeof y === 'number') {
      if (x < y) {
      return x;
      } else if (y < x) {
      return y;
    } else {
    return 'both arguments are equal';
    }
  } else {
    return "Please ensure you include at least one argument with a type of 'number'.";
    }
  }
}
```

**Thoughts:** I remember this exercise being pretty straightforward.

## Recursion

**My solution**

```
const isEven = (number) => {
  const absoluteNumber = Math.abs(number);
  if (absoluteNumber % 2 > 0) {
  return false
  } else {
    return true
  }
}
```

**Thoughts**: I found solving this problem pretty easy. Solving this problem using recursion, however, proved to be a little tricky. I still need more practice to become comfortable using recursion in practical settings rather than merely understanding the theory of it.

## Bean Counting

**My solution:**

```
const countBs = (string) => {
  if (string && typeof string === 'string') {
    const arrayFromString = string.split('')
    let bigBCount = 0
    arrayFromString.forEach((character) => {
      if (character === 'B') {
        bigBCount+=1
        }
      })
      return bigBCount
    }
  }

const countChar = (string, characterToBeCounted) => {
  if (string && typeof string === 'string') {
    const arrayFromString = string.split('')
    let charCount = 0 arrayFromString.forEach((character) => {        if (character === characterToBeCounted) {
      charCount+=1
      }
      })
      return charCount
    }
  }


const countBs = (string) => { return countChar(string, 'B') }
```

**Thoughts**: While this exercise consisted of 3 parts, they were all pretty simple. First we wrote a function that lacked flexibility because it could only count the number of 'B' characters in a string. Then we wrote a more flexible function that was able to count the number of occurrences of any character the user passed. Finally, we rewrote our original _countBs_ function to make use of the flexibility of the _countChar_ function.

I felt this question could have been reworded to have been easier to understand. With that being said, the actual logic was pretty straightforward once I got my head around the problem.

## Conclusion

These exercises were decent brainteasers, but again none of them were particularly challenging. It's always good to reinforce the fundamentals though. I'm looking forward to the next chapter's exercises! :D
