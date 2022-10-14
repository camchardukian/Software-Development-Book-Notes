# Chapter 17 — Smells and Heuristics

## Comments

Almost anytime you see commented-out code you should simply delete it because if anyone were to eventually need this code they could just find it in the version control history.

## Environment

Building your project should require only a single step.

Likewise, you should be able to run all of your unit tests in only a single step.

## Functions

The less arguments a function takes, the better.

If a function takes in a boolean, it’s likely that function does more than one thing and should be refactored.

## General

### Incorrect Behavior at the Boundaries

Don’t rely on your intuition to declare whether a function or algorithm works in every scenario.

Instead, diligently search for each boundary condition, and edge case, and write tests that prove your code works under those conditions.
