# Chapter 7 — Sharing Role Behavior with Modules

Many object-oriented programming languages provide a way to define a named group of methods that are independent of class and can be mixed in to any object. The general term for these names groups of methods is “mix-ins” though Ruby refers to them as modules.

Metz writes that objects should contain their own behavior or put more simply “manage themselves”:

> If your interest is in object B, you should not be forced to know about object A if your only use of it is to find things out about B.

Any time a module sends a message it should provide an implementation, even if the implementation only exists to raise an error informing the developer that users of that module must implement the method.

In classical inheritance, when we want to execute a method we’ll search first for a matching method implementation in an object’s class. If the object’s class has no implementation defined for that method, the search will continue from one superclass to the next until we come to _Object_ itself.

If no matching implementation is found along the way the search may stop in some languages. Other languages such as Ruby, however, may follow the same path once more; this time by sending a new message such as _method-missing_. This entire process can be referred to as ‘method lookup’.

Here’s a great quote from this chapter:

> “The usefulness and maintainability of inheritance hierarchies and modules is in direct proportion to the quality of the code. More so than with other design strategies, sharing inherited behavior requires very specific coding techniques…”

There are a few common antipatterns that indicate our code may benefit from inheritance. The one that stuck out to me, however, was when a sending object checks the class of a receiving object to determine what message to send. This is problematic because our code must change every time we introduce a new potential receiving class.

Instead of this, we should use a duck type and have our receivers implement the duck type’s interface. This will ensure that our original object can send the same message to every receiver with confidence that they will know how to handle the message.

In general, superclasses should only contain code that applies to _all_ of their subclasses. Needing a subclass to override a method from a superclass to say that the subclass “does not implement” is never a good thing.

Needing to say a subclass _does not do something_ implied that a subclass is not truly a suitable instance of the superclass.

In other words, in cases where we are unable to identify the common abstraction(s), inheritance is not the solution to our design problems.

The Liskov Substituion Principle from Barbara Liskov states that,

> “Let q(x) be a property provable about objects x of type T. Then q(y) should be true for objects y of type S where S is a subtype of T.”

In simpler terms, in Ruby an object should act like what it claims to be.

The _template method_ pattern is fundamental for creating inheritable code because it allows you to separate the abstract from the concrete.

When implementing inheritance we should strive to keep our hierarchies shallow and narrow whenever possible. As hierarchies become wider and deeper they become more difficult to understand and more costly to maintain.
