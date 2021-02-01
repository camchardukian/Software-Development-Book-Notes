# Chapter 6 -- The Secret Life of Objects

## Encapsulation

Encapsulation is basically the idea that we should separate interface and implementation. Expanding on that, not every piece of our program needs to understand how every other piece of our program works.

## Methods

As I was learning how to code a couple years ago I remember seeing the terms _function_ and _method_ pretty interchangeably.

It seems there is a slight distinction, however. A _method_ is simply a property of an object that’s holding a function value.

Arrow functions are different than functions declared with the _function_ keyword because arrow functions are able to “see” the _this_ of the scope around them.

## Prototypes

In JavaScript we can return the prototype of an object using _Object.getPrototypeOf()_.

The base object prototype, or the foundation most objects in JavaScript are built upon is _Object.prototype_.

It’s also possible to use _Object.create()_ to create an object with a specific prototype.

## Classes

Prototypes are useful for defining properties that all instances of a class share. Of course, properties that differ in separate instances of a class need to be defined separately in each object.

Putting the _new_ keyword in front of a functions turns said function into a constructor.

All functions (constructors included) are automatically given a property called _prototype_. By default this property holds an empty object built upon _Object.prototype_.

## Class Notation

In JavaScript, classes were introduced in 2015 (ES6). Classes are simply constructor functions that have a prototype property.

Both can be used to create equivalent functionality. It’s just that most developers feel classes are more readable than using constructors and the _prototype_ keyword.

This is probably why I’ve heard many software developers on YouTube refer to JavaScript classes as simply providing _syntactic sugar_.

## Overriding Derived Properties

Objects can be assigned properties already present in their prototypes. If this happens, the property held in the prototype will be “hidden” behind the object’s property.

This could be useful in the case an instance of a class needed a prototype to obtain many properties, but this instance had one exceptional property we needed to override.

## Maps

If we pass _null_ to _Object.create()_, it’s possible to create an object not derived from _Object.prototype_.

JavaScript has a built-in class called _Map_ that was written for the purpose of creating an object used for mappings.

The _Map_ object has _set_, _get_, and _has_ methods as part of its interface.

_Object.keys_ returns only an object’s own keys. It doesn’t return any of the object’s prototype’s keys.

## Polymorphism

Polymorphism is the idea that code can work with values of different shapes.

Here’s my best example (this is my own example, the book doesn’t include a concrete example).

We might have an _Animal_ class. We might instantiate 3 instances of this class.

From this parent class (which could be more technically referred to as the superclass) we may have 1 _Dog_ subclass, 1 _Gorilla_ subclass, and 1 _Bird_ subclass.

It’s possible for our objects to be instances of both the parent _Animal_ class as well as one of the subclasses (Dog, Gorilla, or Bird).

Polymorphism enables us a greater ability to reuse code by allowing each of our subclasses to share code from the parent _Animal_ class.

## Symbols

_Symbols_ are a primitive data type in JavaScript. They can be created using the _Symbol(string)_ function. The _Symbol()_ function takes in an optional string argument that may describe it.

Each value returned from the _Symbol()_ function is unique:

> Symbol(“hello”) !== Symbol(“hello”)

## Getters, Setters, and Statics

Getter and setter methods can be used to hide implementation details or secretly call methods when they are accessed. This may be useful for adding validation checks around getting or setting a value.

They may also be useful for ensuring external users cannot access or modify private variables.

## Inheritance

Inheritance is the process of deriving one class’s properties from another class.

## The Instanceof Operator

We can use the _instanceof_ operator to see if an object was derived from a specific class.
