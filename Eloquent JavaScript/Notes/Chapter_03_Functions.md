# Chapter 3 -- Functions

## Defining a Function

The usage of functions allows us to structure larger programs, reduce repetition, associate names with subprograms, as well as isolate subprograms from each other.

A return _keyword_ without a statement following it returns _undefined_. Likewise a function without a return statement at all will also return undefined.

## Bindings and Scopes

_Global_ variables can be accessed from anywhere within the program.

_Local_ variables on the other hand can only be accessed from within the function or block they were declared in.

Variables defined with _const_ or _let_ are only accessible from the specific block they were declared in.

Variables defined with _var_ are visible throughout the entire function that they appear in (or the global scope if not defined within a function).

If multiple variables are defined using the same name, the code we write will use the innermost variable with said name.

_Lexical scoping_ is the idea that each inner level function/block can access the variables/bindings in outer functions/blocks.

_Hoisting_ is a process that moves function and variable declarations to the top of their respective scopes before the code blocks are run.

## Functions as Values

There is a small difference between declaring a function using the _function_ keyword and declaring a function using a variable.

If we declare a function using a variable we can only call said function after the variable has been initialized.

If we declare a function using the _function_ keyword, however, we can call a function even before it is defined.

This is because _function declarations_ created via the usage of the function keyword are moved to the top of their scope.

## Arrow Functions

Arrow functions were added in ES6 mostly to help us write function expressions in a more concise manner.

## The Call Stack

The call stack is used to provide the computer with context of where the computer should return to after it returns from a function.

When a function returns the top context in the call stack is removed and the computer continues executing based on where that (just removed) context pointed to.

## Optional Arguments

JavaScript is flexible about the number of arguments we pass to a function. If we pass too many arguments to a function the extra arguments will be ignored.

If we pass too few arguments to a function the missing parameters will be assigned a value of undefined.

## Closure

A closure is basically the idea that we can access an outer function’s scope from within an inner function.

## Recursion

A function that calls itself is called _recursive_.

In general, it’s cheaper (i.e. more efficient) to run a single loop multiple times than to call a function multiple times.

## Growing Functions

The difficulty of naming a function is a good indicator of whether said function conforms to the single responsibility principle.

If we can’t easily think of a name for a function, there’s a good chance our function is trying to do multiple things.

## Functions and Side Effects

Here’s a great quote from this section:

> “Functions that create values are easier to combine in new ways than functions that directly perform side effects.”
