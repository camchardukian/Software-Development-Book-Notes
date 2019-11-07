# Chapter 6 — Making Comments Precise and Compact

The key idea Boswell & Foucher open this chapter with is that:
> Comments should have a high information-to-space ratio.

Here are some of the tips given in this chapter followed by me elaborating my thoughts on each tip:

1. **Avoid Ambiguous Pronouns** —  I can’t agree with this concept enough. If someone needs to look at your code to see what a pronoun is referring to, your comment is probably too ambiguous.

1. **Polish Sloppy Sentences** — After writing a comment, it can be extremely beneficial to see if the comment could be re-written to be more precise. Not only can this make our comments more descriptive, but we can also cut deadweight or unnecessary words/information out of our comment as well.

1. **Describe Function Behavior Precisely** — My take on this suggestion is that generally speaking, one’s comment describing a function’s purpose should be precise enough that another developer could re-write said function (given enough time) just from reading the comment.

1. **Use Input/Output Examples that Illustrate Corner Cases** — Sometimes, a well-chosen example showing what a function will output if given a certain input is more insightful than a mere description of the function.

1. **State the Intent of Your Code** — Comments describing what you intend for your code to do are useful for two reasons. First, they give insights into why you wrote code the way you wrote. Second, they give the reader a greater likelihood of spotting code snippets that are producing bugs or not doing what you intended.

1. **“Named Function Parameter” Comments** — The authors suggest that  inline comments can be useful for explaining the purpose of numbers or booleans passed as arguments.

1. **Use Information Dense Words** — Many programming terms have risen to describe common programming problems. Understanding common programming phrases can help us to avoid making lengthy comments when we could simply use a word or phrase other developers already have a mental reference to.