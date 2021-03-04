# Chapter 8 -- Bugs and Errors

## Strict Mode

We can enable _strict mode_ in JavaScript by adding the string “use strict” to the top of a file or function body.

Another feature of _strict mode_ is that it prevents us from giving a function multiple parameters with the same name.

_Strict mode_ also removes some problematic features (such as the _with_ statement) entirely.

## Types

The benefit of using TypeScript is that it allows our computer to find mistakes with how we’re using our functions or variables before we even run our code.

## Testing

The process of writing a program that tests another program is called _automated testing_.

Collections of tests are usually called _test suites_.

A _test runner_ is a tool that allows us to quickly run tests and output informative information when one or many tests fail.

Persistent data structures tend to be easier to test than those that change over time.

## Debugging

Most browsers come with a _debugger_ capability that allows us to set a _breakpoint_ on a specific line of code. Once the execution of the program reaches the _breakpoint_ the program will stop executing.

## Error Propagation

Not all of a program’s problems will come from the person that developed it. However, even if problems come from the network or user’s input, it’s still important for the programmer to proactively account for what the program should do in these situations.

## Exceptions

The _throw_ keyword is used to throw or raise an exception. We can catch an exception by wrapping a block of code within a _try_ block following by a _catch_ block.

## Cleaning Up After Exceptions

Using persistent data structures and reducing the number of side effects in your program are two good ways to reduce the number of exceptions thrown by your app.

## Selective Catching

JavaScript doesn’t provide direct support for selectively catching exceptions. When a _catch_ block runs we only know that an exception was caught. We don’t necessarily know what part of our _try_ expression caused an exception of which exception was caused.

We can intentionally create a loop that will not terminate on its own with the following syntax:

```
for (;;) {
// insert our loop’s logic here.
}
```

We can selectively handle exceptions by defining our own error class that extends the _Error_ constructor, and then use _instanceof_ to see if the exception thrown was of a particular type.

## Assertions

A check inside a program to verify that something is the way it’s supposed to be is called an _assertion_.

We only need to make assertions for common mistakes because trying to write assertions for every possible bad input would result in verbose, more difficult to follow code.
