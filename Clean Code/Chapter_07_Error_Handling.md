# Chapter 7 -- Error Handling

A nice quote to start the chapter:

> "Error handling is important, _but if it obscures logic, it's wrong_."

## Use Exceptions Rather Than Return Codes

Throwing exceptions, such as those that have the potential to be produced by a _try-catch_ statement generally is a cleaner way of handling errors than using return codes.

## Write Your _Try-Catch-Finally_ Statement First

When using TDD, we can try to write tests that force exceptions and then add behaviors to our handlers to satisfy our tests.

## Use Unchecked Exceptions

In general application development, the costs of checked exceptions generally outweigh the benefits. As a result, unchecked exceptions should usually be used instead.

## Provide Context with Exceptions

When you throw an exception it should provide you with sufficient information about the source and location of an error.

## Define Exception Classes in Terms of a Caller's Needs

Wrapping third-party APIs is a best practice because doing do can help to minimize our dependencies upon them.

## Define the Normal Flow

By creating a class or configuring an object that handles special cases, our client code itself doesn't need to deal with exceptional behaviors.

## Don't Return Null

Consider throwing exceptions or returning a _SPECIAL CASE_ object whenever you are tempted to return _null_ from a method.

## Don't Pass Null

To prevent careless mistakes, you should generally not allow for _null_ to be able to be passed in as an argument to your functions.
