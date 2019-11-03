# Chapter 10 Extracting Unrelated Subproblems

We’re now on part III of the book which is about *Reorganizing Your Code*.

The key suggestion Boswell & Foucher make in this chapter is to:
> “Aggressively identify and extract unrelated subproblems.”

The process the authors give for doing so is as follows (quoted directly from Chapter 10 of *The Art of Readable Code*:

1. Look at a given function or block of code, and ask yourself, “What is the high-level goal of this code?”

1. For each line of code, ask, “Is it working directly to that goal? Or is it solving an unrelated subproblem needed to meet it?”

1. If enough lines are solving an unrelated subproblem, extract that code into a separate function.

— The authors give a great guideline for creating utility functions (which I believe are also sometimes referred to as helper functions). My summarized version of their idea is that basically anytime you find yourself wishing your language/library/framework had an “XYZ” function, you should go ahead and write that function.

You can then reuse that “helper” function in the future to save time and avoid duplicating code. As a bonus tip: I’d also recommend you extract all of your “helper” functions into their own file(s) to make accessing and maintaining your helper functions easier in the future. :)

— An unexpected benefit of using helper functions is that it’s easier to improve a helper function than to improve that same snippet of code if it were already nested inside of another function. This is because of the additional readability being separated provides.

You’re also more likely to feel motivated to improve a helper function you can imagine yourself using multiple times versus some deeply nested code you know will only be used once.