# Chapter 9 —- Unit Tests

## The Three Laws of TDD

Here are three laws you should consider adhering to when following a _Test Driven Development_ (TDD) approach (the three rules below are quoted word for word from this chapter):

1. You may not write production code until you have written a failing unit test.
1. You may not write more of a unit test than is sufficient to fail, and not compiling is failing.
1. You may not write more production code than is sufficient to pass the currently failing test.

## Keeping Tests Clean

Failing to write tests in a clean fashion is as bad, if not worse than writing no tests at all.

When tests are dirty, they become difficult to change. As requirements change and features are added it can eventually start becoming so difficult to get your existing tests to pass again that the tests actually become a liability.

### Tests Enable the -ilities

Unit tests help enable us to make changes to our code without the fear of introducing undetected bugs. The higher our unit test coverage, the more flexibile our production code becomes.

## Clean Tests

Clean tests balance clarity, simplicity, and density of expression. They are also structured in a _BUILD-OPERATE-CHECK_ pattern.

This means the the first part of the test builds up the test data, the second part of the test operates on that data, and the final part of that test checks that the operation produced the expected results.

### Domain-Specific Testing Language

Over time we can build up a set of functions and utilities that make our tests easier to read and write.

### A Dual Standard

If code is written for a test environment it should still be clean, but it likely doesn’t need to be as efficient as code written for a production environment.

## One Assert per Test

The number of asserts in a test should be minimized.

### Single Concept per Test

Strive to only test one concept per test function.

## F.I.R.S.T.

Clean tests should be:

**Fast** — Speed is important because if your tests run slow you won’t want to run them frequently enough to detect problems early on.

**Independent** — Tests should be able to be run in any order, and one failing test should not result in the tests following it to fail.

**Repeatable** — Your tests should be able to be run in any environment.

**Self-Validating** — There should be no manual/subjective evaluation to determine whether a test passed or not. Your tests should return only a boolean indicating whether they passed or not.

**Timely** — Unit tests should be written before the production code that makes them pass. If you write your production code before your tests you may design your production code in such a way that it’s difficult to test or you may even decide to give up on testing altogether.
