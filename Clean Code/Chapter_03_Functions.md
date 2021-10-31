# Chapter 3 —- Functions

## Small

Functions should be short. In fact, if your function is 20+ lines long, it probably needs to be rewritten or have smaller functions extracted out of it.

## Do One Thing

Functions should do only one thing, and they should do that one thing well.

## One Level of Abstraction

We should also be careful to make sure the different statements within our function are operating at the same level of abstraction.

## Use Descriptive Names

A long descriptive function name is better than a short name that doesn’t convey meaning.

## Function Arguments

In most cases, the less arguments we pass into a function, the less our brains will have to strain to understand conceptually how that function works.

Functions with fewer arguments are also generally easier to test.

## Have No Side Effects

Functions should either answer something or do something — NOT both.

## Prefer Exceptions to Returning Error Codes

It’s useful to extract the bodies of _try_ and _catch_ blocks into their own functions. Doing so can reduce confusion that sometimes occurs when mixing the normal flow of the program with error handling in the same block.
