# Chapter 4 -- Data Structures: Objects and Arrays Exercises

Note from Cam: For brevity's sake I'm simply going to put my solutions to the following exercises here. For explanations of what each exercise entails, please refer to the [free online version of this chapter here](https://eloquentjavascript.net/04_data.html).

I found the exercises in this chapter pretty challenging -- _especially_ the list exercise.

## The Sum of a Range

**My solution**

```
const range = ({start, end, incrementAmount = 1}) => {
  const myArray = [];
  if (incrementAmount > 0) {
    for (let i = start; i <= end; i+=incrementAmount) {
      myArray.push(i)
    }
  } else if (incrementAmount < 0) {
    for (let i = start; i >= end; i+= incrementAmount) {
      myArray.push(i)
    }
  } else {
    return "Something went wrong. We're sorry for the inconvenience."
  }
  return myArray
  // return sum(myArray)
  // The above line would return all of our array numbers summed together
  }
  const sum = (numbersArray) => {
  return numbersArray.reduce((a, b) => a + b)
}
```

**Thoughts:** I found this exercise simple enough that I was able to produce this answer on my own with minimal amounts of difficulty. I did have to take about 2 minutes to recall the syntax for how to sum numbers using the .reduce() function, but things were pretty straightforward apart from that.

---

## Reversing an Array

**My solution**

```
const reverseArray = (array) => {
  let newArray = []
  for (let i = array.length - 1; i >= 0 ; i-=1) {
    newArray.push(array[i])
  }
  return newArray
}

const reverseArrayInPlace = (array) => {
  for (let i = 0; i < array.length ; i+=1) {
    array.push(array[0])
    array.shift()
  }
  return array
}
```

**Thoughts**: It's been almost two weeks since I completed this exercise so I don't remember in-depth my process for solving this problem.

I just remember that I found solving this problem fairly easy, and that the author asked whether we thought the _reverseArray_ or _reverseArrayInPlace_ method would be more useful.

My thought at the time was that the reverseArray method would be more useful because it would allow us to manipulate the data provided by an input and return a result without mutating the original input.

---

## A List

**My solution:**

```
// const arrayToList = (array) => {
//   let list = {value: null, rest: null}
//   let restCounter = ['rest']
//   for (let i = 0; i < array.length; i+=1) {
//     console.log('loop', list)
//     if (i > 0) {
//       // list[i]['value'] = array[i];
//       list['rest'] = {value: array[i], rest: null};
//       // list[i - 1]['rest'] = list[i]
//     } else {
//       list['value'] = array[i]
//       list['rest'] = null
//     }
//   }
//   return list
// }


// const arrayToList = (array) => {
//   let list = {value: null, rest: null}
//   for (let i = array.length - 1; i >= 0; i-=1) {
//     console.log('array[i]', array[i])
//     list['value']
//     list['rest'] = {value: array[i], rest: null}
//     console.log('list', list)
//   }
//   return list
// }

// Stackoverflow solution
// function arrayToList(array) {
//     let list = null;
//     for (let i = array.length - 1; i >= 0; i--) {
//         list = { value: array[i], rest: list };
//     }
//     return list;
// }


// const listToArray = (list) => {
//   const arrayFromList = Object.entries(list);
//   const recursedArray = recursionFunc(arrayFromList)
//   return arrayFromList
// }

// const recursionFunc = (array) => {
//   if (array[array.length - 1]) {

//   }
//   console.log('arrrr', array)
// }

function listToArray(list) {
  let array = [];
  for (let node = list; node; node = node.rest) {
    array.push(node.value);
  }
  return array;
}

const prepend = (element, list) => {
  let prependedList = {};
  prependedList.value = element
  prependedList.rest = list;
  return prependedList
}

const nth = (number, list) => {
  let incrementor = 0

  for (let node = list; node; node = node.rest) {
    incrementor+=1
    if (incrementor === number) {
      return node;
    }
  }
  return undefined
}


// const nthUsingRecursion = (number, list) => {
//  let myNumber = 0
//  if (number === myNumber)
//      if(condition) {
        // stop calling itself
        //
//    } else {
//       nthUsingRecursion()
//    }
// }

const myArray = [1, 2, 3];

const myList = {
value: 1,
rest: {
  value: 2,
  rest: {
    value: 3,
    rest: {
      value: 'a',
      rest: null
    }
    }
  }
};

// prepend(10, myList)
// nth(2, myList)
nthUsingRecursion(2, myList)


// listToArray(myList)
```

**Thoughts**: YIKES. That's all I can say about this problem. This problem was quite a doozy for me. While I was able to solve the second half of the problem, the first half of the problem had me completely bamboozled.

I left some of my brainstormed code in comments to show that I did put a sincere effort into this problem but I just wasn't able to solve it in full.

One thing this problem did show me, however, is that although I'm decent with algorithms, I need more practice with data structures.

---

## Deep Comparison

**My solution:**

```
const deepEqual = (val1, val2) => {
  if (val1 === val2) {
    return 'Equal'
  }
  if (confirmAllItemsAreNonNullObjects(val1, val2)) {
    if (confirmTwoObjectsHaveSameKeys(val1, val2)) {
      if (confirmTwoObjectsHaveSameValues(val1, val2)) {
        return 'Equal'
      }
    }
  }
  return 'Not equal!!'
}

const confirmAllItemsAreNonNullObjects = (...items) => {
  if (items.length < 1) {
    return false
  } else {
    for (let i = 0; i < items.length; i+=1) {
      if (typeof items[i] !== 'object' || items[i] === null ) {
        return false
      }
    }
    return true
  }
}

const confirmTwoObjectsHaveSameKeys = (object1, object2) => {
  if (object1 && object2) {
    const object1Keys = Object.keys(object1).sort()
    const object2Keys = Object.keys(object2).sort()
    if (JSON.stringify(object1Keys) === JSON.stringify(object2Keys)) {
      return true
    }
  }
  return false
}

const confirmTwoObjectsHaveSameValues = (object1, object2) => {
  if (object1 && object2) {
    const object1Values = Object.values(object1).sort()
    const object2Values = Object.values(object2).sort()
    if (JSON.stringify(object1Values) === JSON.stringify(object2Values)) {
      return true
    }
  }
  return false
}
```

**Thoughts**: This exercise took me about 50 minutes to solve. Solving this problem helped me learn about using JSON.stringify() to compare arrays. I never had any serious doubts about my ability to solve this problem.

With that being said, it seemed my solution and the others differed a bit. I felt that two objects with the same keys and same values but in different orders should be considered equal to each other.

The author did not. The author also solved this problem using recursion whereas I felt doing so would decrease the readability of the solution.

---

## Conclusion

These exercises really stretched me. I'm looking forward to continuing to work on challenging exercises for the rest of this book to push myself to become an even better software developer.
