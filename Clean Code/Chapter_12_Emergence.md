# Chapter 12 -- Emergence

## Getting Clean via Emergent Design

The author refers to four rules he recommends adhering to that were created/inspired by Kent Beck:

1. Runs all the tests
1. Contains no duplication
1. Expresses the intent of the programmer
1. Minimizes the number of classes and methods

## Simple Design Rule 1: Runs All the Tests

The more tests we write, the more we'll strive to write code that is easy to test.

As such, ensuring our entire system is testable and taking a TDD approach helps us adhere to better coding practices such as the _Single Responsibility Principle_, _Dependency Inversion Principle_, creating abstractions to minimize coupling, etc.

## Simple Design Rules 2-4: Refactoring

By having our systems be well tested, we don't need to be afraid that refactoring our code will break the existing functionality.

### No Duplication

When subclasses have methods with similar or overlapping functionality, we can often extract that functionality into a superclass with a template method that many/all of its subclasses can use.

### Expressive

You can make your code more expressive and easier to understand for future readers by choosing good names, following design patterns, and having well-written unit tests.

### Minimal Classes and Methods

It's important not to be dogmatic about making our classes and methods small.

Pragmatism is important, as it's also possible (though perhaps less common) to take the SRP and elimination of duplication too far and end up with way too many tiny classes and methods.
