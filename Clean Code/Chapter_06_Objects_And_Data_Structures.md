# Chapter 6 -- Objects and Data Structures

## Data Abstraction

Classes should allow users to manipulate the essence of data without having to have detailed knowledge about the internal implementation of the class (which seems like how we create helper functions in ReactJS projects which other developers may understand how to use without necessarily understanding how said functions work under the hood).

---

## Data/Object Anti-Symmetry

Polymorphism is a concept in object-oriented programming that refers to how objects, function, or variables have the ability to take on multiple forms.

Writing code in an object-oriented fashion and writing procedural code differ because:

> “Procedural code (code using data structures) makes it easy to add new functions without changing the existing data structures. OO code, on the other hand, makes it easy to add new classes without changing existing functions.

---

## The Law of Demeter

The Law of Demeter is used to produce objects that are loosely coupled.

---

### Train Wrecks

It seems a “train wreck” can be identified as when we have to use too many dots to access the internals of an object.

---

### Hybrids

Try to avoid making hybrid structures that are half object and half data structure.

These “hybrids” are problematic because they make it difficult both to add new functions but also to add new data structures.

---

## Data Transfer Objects

A Data Transfer Object (DTO) is a class with public variables and no functions. DTOs are often useful for communicating with databases, parsing messages from sockets, etc.

---

### Active Record

Active Records are a special form of DTO that typically have navigational methods like _save_ and _find_.
