# Chapter 2 -- Packing Information Into Names

The key idea Boswell & Foucher open this chapter with is developers should:
> Pack information into your names.

While it’s not really an epiphany for me, I like that the authors make the analogy of a variable, function, or class name being a lot like a mini comment.

While names don’t give us a ton of space to work with, they still have the potential to convey a lot of information.

**Concept #1**

The first actionable step we can take to improve our variable/function/class naming abilities is to use words that are very specific.

The authors give an excellent example using a function called *Stop()*. While *Stop()*, kind of gives you the idea of a what a function may do, renaming our function to *Kill()* or *Pause()* may more clearly express whether we would later be able to resume a process or not.

**Concept #2**
Boswell & Foucher suggest that in general we should avoid using generic names like *retvalue* or *foo*. Many developers use generic variable names because they can’t immediately think of anything better.

In the case of variables, we should drive to use names that describe the value(s) our variable(s) contain. By spending an extra few seconds naming our variables, we can save significantly more time down the road debugging our code.

**Concept #3**
Developers should strive to prefer concrete names over abstract names. In other words, we should aim to make our names describe precisely what our functions do, rather than the circumstances in which the function is used or the results of running the function.

**Concept #4**
Because readers will see a variable’s name every time said variable is used, we should try to include any information that’s very important to know inside of the variable’s name.

Here’s an example of my own I just came up with after reading some of the authors’ ideas.

Instead of naming a variable *id*, we may opt to name the variable *numberId* to help the reader of our code remember that the format of the variable needs to be a number data type rather than a string.

**Concept #5**
If our variables are measurements, it can be very helpful to include the unit type into the variable’s name. For example, delayedDispatchAction could be renamed delayedDispatchAction_ms.

This would inform the readers of our code which unit type (in this case milliseconds) that we were using.

Explicitly naming our variables and describing their data types can also be important for security purposes.

For example, instead of naming a variable *password*, we could name the variable *unsafePlainTextPassword* before it is encrypted.

**Concept #6**
There are a couple things we should consider when deciding how long our variable names should be. The first is that if a variable has a narrow scope, you can probably get away with giving the variable a shorter name because the reader is likely to be “closer” to the code, and seeing exactly how it is being used in context.

Should we use abbreviations or acronyms when naming? Boswell & Foucher suggest that it’s fine to use general programmer abbreviations like ‘string —> str’, or ‘evaluation —> eval’.

They seem to argue against using project-specific abbreviations in most cases, however.

As such, their general guideline is that if a new team member could understand your abbreviation, the name is probably fine. If not, you should probably refactor your code to use a clearer name.

Finally, also consider using formatting to convey meaning in your naming efforts. In JavaScript for example, constructor functions by convention should start with a capital letter while regular functions start with lowercase letters.
