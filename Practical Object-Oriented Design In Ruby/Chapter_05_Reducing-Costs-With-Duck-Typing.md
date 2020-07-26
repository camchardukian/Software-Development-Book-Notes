# Chapter 5 — Reducing Costs with Duck Typing

> “The purpose of object-oriented design is to reduce the cost of change.” -- Sandi Metz

One way we can reduce the cost of changes to our application is through the usage of duck types. Duck types are public interfaces that are not tied to any specific class.

Sequence diagrams should always be more simple than the code they represent. When this is not the case, something is wrong with the design of the application.

Wow! Here’s a really nice takeaway from the Consequences of Duck Typing section of this chapter,

> “This tension between the costs of concretion and the costs of abstraction is fundamental to object-oriented design. Concrete code is easy to understand but costly to extend. Abstract code may initially seem more obscure but, once understood, is far easier to change.

Polymorphism in OOP is the ability of many different objects to respond to the same message. In other words, the sender of a message does not need to be concerned about the class of the receiving object. The “receiver” will take the message received and supply its own appropriate behavior.

Three ways to achieve polymorphism include:

1. Duck typing
1. Inheritance
1. Behavior sharing

We only need to create new duck types when doing so would decrease the cost of producing the application.

Metaprogramming basically refers to code that writes code or a program that has knowledge of itself/is able to manipulate itself.
