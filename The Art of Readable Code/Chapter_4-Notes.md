# Chapter 4 — Aesthetics

The key idea Boswell & Foucher open this chapter with is that:
> It’s easier to work with code that’s aesthetically pleasing.

— The authors also make the distinction between the aesthetics of our code, and the design (which I believe could also include the architecting of our application).

Basically, writing code that is aesthetically pleasing allows both ourselves and other developers to quickly skim our code to understand what it is doing.

— One principle Boswell & Foucher discuss in this chapter is the idea that “similar code should look similar”.

If we have a handful of functions that would make sense to be formatted similarly (Redux actions and reducers are the first thing that immediately come to mind for me), we should do our best to format said functions in a consistent fashion.

— One concept presented in this chapter that I can’t agree enough with is the idea that making our code “look pretty” not only results in surface level improvements, but can also help us to better structure our code.

— While not a universal recommendation, some developers feel that lining up function arguments or variable names in columns can be useful in spotting mistakes and making code easy to skim through.

— In circumstances where the order of code does not affect the application, it’s recommended to order variable definitions (or anything really) in some consistent fashion.

Whether alphabetically, from most important to least important, most frequently used to least frequently used, the sorting method isn’t important. Being consistent, however, will reduce the likelihood of making mistakes and also make our code easier to scan later on.

— Grouping classes, methods, or variables into logically organized sections or blocks can contribute to making our code easier to digest by improving the reader’s ability to quickly find the snippet of code they’re looking for.

— The final takeaway the authors try to impart upon us is that consistency is more important than personal preference. In circumstances where the coding style or format does not significantly impact the readability of our code, we should strive to be consistent with the style choice used on our project even if it doesn’t match our personal preference.