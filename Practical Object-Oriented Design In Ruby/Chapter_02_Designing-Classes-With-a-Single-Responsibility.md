# Chapter 2 — Designing Classes with a Single Responsibility

> “Your goal is to model your application, using classes, such that it does what it is supposed to do right now and is also easy to change later. “

Metz writes that it’s easy to create an application that works right now. The quality of making code functional in the present while being easy to change in the future, however, is what truly takes knowledge, skill, and creativity.

In class-based object-oriented languages like Ruby, methods are defined inside of classes.

Metz gives the following criteria for evaluating if code is _easy to change_:

- Changes have no unexpected side effects
- Small changes in requirements require correspondingly small changes in code
- Existing code is easy to reuse
- The easiest way to make a change is to add code that in itself is easy to change

In order to meet these criteria, Metz recommends our code should be (paraphrased in my own words):

- Transparent — Both the direct and indirect consequences of changing some block of code should be obvious.
- Reasonable — The cost of changing some block of code should be proportional to the benefits achieved through said change.
- Usable — Code that we already have should be able to be easily reused in new and unexpected contexts.
- Exemplary — Existing code should encourage those who change it to perpetuate the three previous qualities in this list.

Code that embodies the above qualities can be referred to as being _TRUE_ code.

A class that has more than one responsibility is difficult to reuse (coming from a JavaScript background, I’d say the exact same thing about functions that have multiple responsibilities being difficult to reuse).

Duplicated code is problematic because it requires more maintenance and increases the likelihood of bugs occurring.

The more responsibilities a class has, the more likely it is to change. Each time a class changes, there’s a possibility it will break. Thus, giving classes a single responsibility greatly reduces the chance of our application unexpectedly breaking.

A great way to determine if a class has a single responsibility is to try to describe it’s purpose in one sentence. If you cannot describe the class in a simple manner without the words “and” or “or”, the class likely has multiple responsibilities.

It can be argued that when we make design decisions is nearly as important as which decisions we make. When the future cost of doing nothing is the same as the current cost, we should postpone decisions (because doing so does not result in technical debt while also bringing us closer to a future in which we have more information with which to make an informed decision).

We may be able to make our applications more reusable by using accessor methods to get the data we need, rather than defining the data directly using a variable in our class.

An easy to overlook mistake that violates the single responsibility principle for methods is forgetting to separate iteration from the action being performed.

Comments should be viewed as a form of decaying documentation. Instead of leaving a comment in a complicated method, the method should be simplified by extracting some amount of logic into another function.

Metz does an excellent job summarizing the chapter in saying:

> "The path to changeable and maintainable object-oriented software begins with classes that have a single responsibility. Classes that do one thing isolate that thing from the rest of your application. This isolation allows change without consequence and reuse without duplication."
