# Chapter 7 — Making Control Flow Easy to Read

The key idea Boswell & Foucher open this chapter with (we’ve now made it two part II of the book by the way!) is that us developers should:

> Make all your conditionals, loops, and other changes to control flow as  “natural” as possible — written in a way that doesn’t make the reader stop and reread your code.

— In regards to conditionals like if statements or ternary operators, choosing which variable/expression goes on the left side and which goes on the right side can make a big difference in how readable our code is.

— The recommendation the authors give is that we should generally try to put the expression that’s more “in flux” on the left, and the expression whose value is more constant on the right.

— There don’t seem to be any hard and fast rules about how to order if/else clauses. In general, the best advice seems to be simply to be conscious about how, we’ve ordered our if/else clauses, and simply avoid anything awkward/difficult to read.

— In regards to ternary operators, a key idea *The Art of Readable Code* suggests is that minimizing the number of lines our code takes up is of secondary importance to minimizing the time it takes for other developers to understand our code.

— Boswell & Foucher suggest that if possible, we should try to rewrite do while loops, as while loops (or other types of loop).

— Another suggestion Boswell & Foucher make in this chapter is that we should try to minimize nesting as deeply nested code can be difficult to read as we have to pay attention each time we see a closing brace.

— One way we can minimize nesting in our code is by returning early from a function.