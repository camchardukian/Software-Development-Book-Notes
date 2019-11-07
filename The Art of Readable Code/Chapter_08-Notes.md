# Chapter 8 Breaking Down Giant Expressions

The key idea Boswell & Foucher open this chapter with is that as a developer, you should try to:
> Break down your giant expressions into more digestible pieces.

— The authors suggest that the use of “summary variables” is one way we can break down large chunks of code into smaller chunks. Here’s an example taken straight from chapter 8 of *The Art of Readable Code* (I just changed the code a little to be JavaScript rather than their example from another language).
```
if (request.user.id == document.owner_id {
   //  user can edit this comment 
}
```
The above code can be converted to…
```
const user_owns_document = (request.user.id == document.owner_id);

if (user_owns_document) {
   // user can edit this comment.	
}
```

— Another way to make our expressions more readable is to avoid double negatives.

— Most programming languages have something called “short-circuit logic”. This term basically refers to the idea that a boolean operator with an *or clause* such as, “(a || b) will not evaluate *b* is *a* is true. Because of this, boolean operators can be used to perform some very complex logical operations.

While using short-circuit logic to evaluate a complex expression can make one feel “clever”, it’s important to be conscious of the fact that others won’t have the same mental context when looking at your code.

While you may immediately understand the complex line of code you wrote, that single line may later cause mental strain or require additional time from other developers (or even you in the future!).


While short-circuit logic certainly has its place in a developer’s arsenal, it’s also important to be cognizant of the fact that the aim of our code isn’t to be “clever”. It’s to make others feel “clever” by the fact that they can immediately or quickly understand all of the code that we wrote.

— Apart from being reusable, another benefit of preferring constants over string literals is that constants will produce an error when misspelled whereas misspelled string literals can often be time consuming to debug.

— Here’s a great quote from this chapter (with some filler removed, see ellipses), 
> “What started as a simple problem… turned into a surprisingly convoluted piece of logic. This is often a sign that there must be an easier way.

