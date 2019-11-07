# Chapter 3 — Names That Can’t Be Misconstrued

The key idea Boswell & Foucher open this chapter with is that developers should strive to:
> Always scrutinize your names by asking yourself, “What other meanings could someone interpret from this name?”

Basically, it seems to me that the main idea the authors are trying to impart on us is that we should avoid ambiguity and anything that could possibly be misinterpreted when naming things as a developer.

I like the first example they give in this chapter of a function named filter(). The authors say that filter is an ambiguous word because it’s difficult to know whether our usage of said function is to help us choose something, or get rid of something.

For that reason, the authors propose two better possible names for this hypothetical function.

In the authors’ words, 
> If you want “to pick out,” a better name is select(). If you want “to get rid of,” a better name is exclude(). 
>
>  — <cite>The Art of Readable Code</cite>

— Instead of using the words *start* and *stop* to indicate a range, it may be clearer to use the parameter names *begin* and *end*.

— When naming booleans we should be conscious to avoid negative terms in our names. *disableSecurityMode* is a variable name that is not immediately clear about what it is doing (you may need to spend several seconds conceptually thinking about what a value of true would mean).

— The words *is* and *has* can also be used in our variable names to indicate that our variable is indeed a boolean.

— We should be conscious of naming our functions to clearly indicate to other developers whether the usage of said functions would be resource intensive and have a significant effect on performance.

The function names *getAverageEmployeeSalary* and *computeAverageEmployeeSalary* clearly give different first impressions about how many resources firing the function would command.