# Chapter 2 — Program Structure

## Expressions and Statements

An _expression_ is a fragment of code that produces a value or is a value in itself.

## Bindings

A program keeps an internal state through the usage of _bindings_ or _variables_.

It’s possible to define multiple variables with a single _let_ statement by separating the definitions with commas. For example:

```
Let firstName = ‘Cameron’, lastName = ‘Chardukian'.
```

## Binding Names

Binding or variable names:

1. May include dollar signs (\$) or underscores (\_).
1. May include numbers.
1. May NOT start with a digit.
1. May NOT include punctuation marks or special characters (apart from dollar signs and underscores).
1. May NOT have the same name as existing keywords or other JavaScript reserved words.

## The Environment

An _environment_ is a set of bindings and values that exist at a given time.

## While and Do Loops

The only difference between a _do loop_ and a _while loop_ is that a _do loop_ is guaranteed to run at least once.

## Breaking Out of a Loop

We can use the _break_ statement to immediately break out of a loop.

The _continue_ keyword is similar to _break_, but instead of terminating the loop cycle the _continue_ keyword will simply result in the next iteration of the loop being run.

## Dispatching On a Value With Switch

While generally recommended, it is NOT required to include a _break_ statement after every case in a switch statement.

If we want to share some code between cases, we can do so. Here’s a good example straight from the book:

```
switch (prompt(“What is the weather like?)) {
  case “rainy”:
    console.log(“Remember to bring an umbrella”);
    break;
  case “sunny”:
    console.log(“Dress lightly.”);
  case “cloudy”:
    console.log(“Go outside.”);
    break;
  default:
    console.log(“Unknown weather type!”);
    break;
}
```

If the user input “sunny” into this program, both “Dress lightly”, and “Go outside” would be logged to the console.
