# Chapter 14 — Testing and Readability

The key idea Boswell & Foucher open this chapter with is that having readable test code is of the utmost importance. This is for several reasons, few of which include:

— Other developers will often look at test code as “unofficial” documentation of how the actual code should behave and be used.

— Having readable test code ensures other developers will be capable of efficiently changing or adding tests.

A general design principle that applies to tests (and many other things!) is that by hiding less important details from the user, the important details will be more easily seen by the user.

As such, when we’re designing tests, we should only show the user the things that are important or necessary for them to see. Repeated parameters or complex operations that don’t need to be immediately paid attention to can be placed in util/helper functions.

— Keeping test statements short makes it easier to add more test cases.

— The most helpful error messages are those that contain the user’s input, the expected output, and what the code actually produced (the actual output).

— To choose good input values for our tests, we should try to use values that will both thoroughly test the code, but also be as simple as possible to read.

— Writing multiple smaller tests is often more effective than trying to construct a single “perfect” test. Smallest tests are often easier to read, and being able to see specifically which test case failed can also make it easier for other developers to debug their code.

— The authors suggest that if we know that we’ll later have to write tests for our code, we’ll naturally design our code so that it’s easier to test. As such, keeping testing in mind while writing code can be useful in steering us to write cleaner, better organized code.

— The amount of time spent writing test code depends on how costly potential bugs are.