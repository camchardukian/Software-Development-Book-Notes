# Chapter 1 -- Code Should Be Easy To Understand

The very first concept the authors introduce is that:
> Code should be easy to understand.

*How do we define code that’s easy to understand?* Well, the authors (Boswell & Foucher) propose that the definition of code that is easy to understand can be measured by how long it takes our average colleague to understand our code.

One objection many people have to this (and that I may have previously agreed with), is that it doesn’t matter if others can understand our code if we’re working on a one person project.

Boswell & Foucher refute this claim, however, by pointing out that it’s worth pursuing making our code easier for others to understand even on one-man projects because 6 months later, our own code is likely to look unfamiliar to us.

Another interesting concept is the idea of making our code short. I’ve always strived to refactor my code for brevity.

This is a good starting point as a 500 line file is likely to take less time to understand than a 2000 line file.

Boswell & Foucher suggest, however, that while trying to write fewer lines of code is a good goal, the benefits attained from adding comments to our code or spreading overly complex logic from one line to 2 or more lines often outweighs simply trying to have the shortest code possible.

Here’s another takeaway I really liked from this chapter. The authors said that if you are a programmer that has a compulsive need to fix any code that isn’t perfectly factored, there’s a simple question you can ask yourself to determine whether it’s time to move on to the next piece of code.

That question is… *Is this code easy to understand?* If so, it’s probably alright to move on. If not, it’s likely worth investing some time now to make the code more readable and avoid accumulating technical debt that will later need to be paid off.