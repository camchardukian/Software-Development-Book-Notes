# Chapter 6 — Acquiring Behavior Through Inheritance

Classical inheritance is based on the word class and does not refer to an archaic technique.

An anti-pattern is a common pattern that would appear to be beneficial but is actually detrimental due to a better well-known alternative existing.

Having the last option of an if statement be the default value can be dangerous because you may produce unexpected behaviors if an unexpected input is given.

The purpose of inheritance is to share common behaviors among types that are highly related but still differ in some ways.

Some programming languages allow objects to have multiple inheritance while other languages only allow for single inheritance.

Every class we create is by definition a subclass of something.

If we create a new class but do not specify its subclass, Ruby (or JavaScript as well I think) would set the our class’s superclass to _Object_.

Inheritance allows us to define a relationship between two objects such that if the first object does not understand a message it can automatically forward that message to the second object.

A subclass contains everything its superclasses contain _plus more._

For inheritance to work correctly, the objects that we are modeling must have a generalization-specialization relationship.

When refactoring code into a new inheritance hierarchy we should focus on promoting abstractions rather than demoting concretions.

Writing code that produces unambiguous error messages take a small amount of effort in the present, but can provide value for the remaining duration of the application’s life.

It makes sense that subclasses should know what they contribute to a super class. After all, only a subclass could know additional information beyond its superclass.

Subclasses on the other hand _should not_ need to know how to interact with their abstract superclasses. I believe this is because while software developers can almost always be relied upon to provide the correct specializations for a subclass, they may not always remember how a subclass should interact with its superclass.

Abstract superclasses are best created by pushing code up from concrete subclasses. Ideally, you would have at least three existing concrete subclasses in order to create a superclass, but this isn’t strictly required.

The benefit of well designed inheritance hierarchies is that they are easy to extend with new subclasses even for developers who do not know much about the application.
