# Chapter 2 -- Meaningful Names

## Use Intention-Revealing Names

Choosing good names requires a small investment of time, but is well worth it.

## Make Meaningful Distinctions

One of the fastest ways a programmer can create problems for themselves is by writing code simply to satisfy the compiler/interpreter. The things in our application should be named in such a way that it is easy for the reader to distinguish differences between the names and know exactly what each name is referring to.

## Use Pronounceable Names

Names should be easily pronounced so that they can be easily discussed in verbal conversations.

## Use Searchable Names

The author gives a great tip for thinking about how long names in our programs should be:

> “The length of a name should correspond to the size of its scope.”

## Avoid Mental Mapping

Being able to remember what unclear variable names refer to makes you smart. Writing clear code that others can easily understand, however, is what makes you a professional.

## Pick One Word per Concept

We should avoid naming things in our program using two words that mean the same thing. For example _fetch_, and _retrieve_ or _controller_ and _manager_.

## Don’t Pun

Our code should read more like a paperback bestseller than an academic research paper. It’s our job to make our code understandable, not the reader’s job to try to parse some meaning out of it.

We should ensure when we use a word that it’s only being used in a certain way. For example, if we have a method with the word _add_ that’s used for performing mathematical operations we should NOT have another method with the word _add_ that puts something into an array.

In this case, a word like _insert_ would be more appropriate.

## Don’t Add Gratuitous Context

Names should be precise, without becoming overly lengthy and providing more context than is actually necessary.
