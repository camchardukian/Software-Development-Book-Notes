# Chapter 10 -- Classes

## Class Organization

A class in Java should begin with a list of variables. Public static constants (if any) should come first followed by private static variables, private instance variables, and public functions.

### Encapsulation

When possible you should try to keep your variables and utility functions private. Though there are cases where loosening encapsulation could make sense, you should generally only do so if absolutely necessary.

## Classes Should Be Small

The responsibilities a class fulfills should be made clear by its name. If it's difficult to think of a concise name for a class, the class is likely responsible for too many things.

### The Single Responsibility Principle

Classes should have only one responsibility. Creating small classes is like having a toolbox with many small organized drawers to throw our tools in.

Having large complex classes is like throwing all of our tools into a toolbox that has only a few disorganized drawers.

### Cohesion

We don't need our classes to be maximally cohesive, but their level of cohesion should be high.

### Maintaining Cohesion Results in Many Small Classes

If your class lacks cohesion, it's likely your class should be split up into multiple classes.

Writing a test suite before refactoring a program can help you ensure you don't accidentally introduce bugs or modify the functionality of the program.

## Organizing for Change

Here's a great quote from the author:

> "In an ideal system, we incorporate new features by extending the system, not by making modifications to existing code."

### Isolating from Change

The Dependency Inversion Principle (DIP) states that our classes should depend upon abstractions, not on concrete details.
