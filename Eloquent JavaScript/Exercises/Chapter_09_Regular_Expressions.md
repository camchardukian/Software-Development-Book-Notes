# Chapter 9 -- Regular Expressions

Note from Cam: For brevity's sake I'm simply going to put my solutions to the following exercises here. For explanations of what each exercise entails, please refer to the [free online version of this chapter here](https://eloquentjavascript.net/09_regexp.html).

Here are my solutions for this chapter's exercises.

---

## Regexp golf

**My solutions:**

```
#1 /car|cat/
#2 /pr?op/
#3 /ferr(et?|y|ari)/
#4 /\w+ious/
#5 /\s(\.|,|:|;)/
#6 /\w{7,}/
#7 /^[a-d|f-z|A-D|F-Z]((?![eE]).)*$/
```

**Thoughts:**

With each one of these problems I solved, I felt more confident in my ability to write Regular Expressions. I also feel a lot more comfortable reading and analyizing others regular expressions (though I've found this is something that's asked of me pretty rarely even as a professional software developer).

---

## Quoting Style

**My solution:**

```
console.log(text.replace(/'(?!\w\s)/g, "\""));
```

**Thoughts:**

I found this exercise pretty simple to solve. Solving this problem, however, will surely help me remember that it's possible to perform very powerful operations by coming Regular Expressions with the _replace_ method.

---

## Numbers Again

**My solution:**

```
let number = /^[+-]?(\.?\d+|\d+\.?\d*)([Ee][+-]?[\d]+)?$/;
```

**Thoughts:**
It took me quite a long time to put together this Regex. I overcomplicated things at first by thinking about how I could implement different lookaheads/lookbehinds.

In the end, however, I was able to come up with this reasonably concise solution.
