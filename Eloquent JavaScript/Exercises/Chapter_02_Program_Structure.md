# Chapter 2 Program Structure Exercises

Note from Cam: For brevity's sake I'm simply going to put my solutions to the following exercises here. For explanations of what each exercise entails, please refer to the [free online version of this chapter here](https://eloquentjavascript.net/02_program_structure.html).

For this chapter, I was able to solve all of the problems independently spending around 5-10 minutes per exercise.

After solving each problem, I then checked the author's solution to see if they solved the problem in a more optimal fashion.

## Looping a Triangle

**My solution:**

```
const triangleLoop = () => {
  let str = "";
  for (let i = 0; i < 7; i+=1) {
  str+= "#"
  }
}

triangleLoop()
```

**Thoughts**: I was able to solve this problem fairly easily. My solution ended up being essentially identical to the authors.

---

## FizzBuzz

**My solution:**

```
const fizzbuzz = () => {
  for (let i = 1; i <= 100; i+=1) {

    if (i % 3 === 0 && i % 5 === 0) {
      console.log('FIZZBUZZ')
    } else if (i % 3 === 0) {
      console.log('FIZZ')
    } else if (i % 5 === 0) {
      console.log('BUZZ')
    }
    else {
console.log(i)
    }
  }
}

fizzbuzz()
```

**Thoughts**: This problem ended up being easier than I expected it to be! In retrospect, it seems I could have produced a more clever solution via the usage of the OR operator ( | ) rather than chaining a number of _if_ and _else_ statements.

---

## Chessboard

**My solution:**

```
const chessboard = (numberOfRowsAndColumns) => {
  let str = '';
  for (let i = 0; i < numberOfRowsAndColumns; i+= 1) {
    for (let ii = 0; ii < numberOfRowsAndColumns; ii+=1) {
      ii % 2 === 0 ? str = str + '0' : str = str + '#';
      if (ii === numberOfRowsAndColumns - 1) {
        str = str + '\n'
      }
    }
  }
  console.log(str)
}

chessboard(8)
```

**Thoughts**: This was another routine problem that was pretty easy to solve. I haven't used nested loops in a while so I made a mistake while solving this problem when I accidentally incremented _i_ in the inner loop rather than _ii_.

This of course caused an infinite loop. Fortunately, after a minute or two I recognized my error and was still able to solve the entire problem in under 10 minutes.

The biggest thing I took away from this exercise was a better understanding of how to use '\n' to add line breaks to my console.log statements.

---

## Conclusion

This chapter's excercises were fairly simple. I'm looking forward to the difficulty of the problems ramping up as we continue to get deeper into this book.
