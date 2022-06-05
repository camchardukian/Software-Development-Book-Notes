# Chapter 16 — Refactoring SerialDate

## Then Make It Right

Redundant comments not only take up additional space, they also are prone to collect misinformation over time as programmers neglect to update them.

Base classes generally should not know about information from instances of their derivatives.

It’s sometimes better to write or add unit tests to tell you where/why your code is failing rather than trying to rely on error throwing.

The usage of “explaining temporary variables” can help clarify how algorithms are working.

Sometimes refactoring your code can actually lead to decreased test coverage even though you’re still testing the same amount of actual functionality. Why?

Because by removing large amount of unnecessary code, any remaining lines of uncovered code are weighted more heavily.
