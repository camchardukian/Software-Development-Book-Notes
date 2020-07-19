# Chapter 4 — Creating Flexible Interfaces

By limiting how much objects know about each other, we can make objects easier to reuse. Some methods in a class are more likely to change than others.

Our design should recognize this fact, by limiting which methods of an object are able to be invoked by other objects. Failure to do the above may result in one small change to an object requiring a change to most, if not every other object in our application.

Metz discusses about how our classes should have both public and private interfaces. She says the methods in our public interfaces…

> - "Reveal its primary responsibility
> - Are expected to be invoked by others
> - Will not change on a whim
> - Are safe for others to depend on
> - Are thoroughly documented in the tests"

While private interfaces…

> - "Handle implementation details
> - Are not expected to be sent by other objects
> - Can change for any reason whatsoever
> - Are unsafe for others to depend on
> - May not even be referenced in the tests"

In short, the public parts of a class can be seen as being stable and generally safe to depend on. The private parts of a class, however, should be seen as unstable and more likely to be affected by a distant, seemingly unrelated change.

Test driven development is something that’s often seen as being difficult by novice developers. More mature developers tend to struggle less with TDD, however, because they already have significant design experience.

Thus upon hearing the requirements of an application they may already have some preconceived mental models about how their app may need to be structured.

Sequence diagrams can provide us with insights into how different parts of an application interact. More specifically, in the context of OOP, sequence diagrams can help us to clearly identify which messages are passing through which objects and thus how to define our public interfaces.

Sequence diagrams can also help us to communicate and think about things that would otherwise be extremely difficult to discuss in a strictly verbal manner.

Metz says a turning point in the design career of a developer occurs when they shift from class-based design to message-based design. This is because message-based design results in more flexible applications than class-based design.

Or, as Metz puts it, “You don’t send messages because you have objects, you have objects because you send messages. By focusing on objects rather than messages, we can more easily design an application built upon public interfaces.

In OOP we should try to focus on having our messages focus on the _what_ rather than the _how_. To elaborate, our messages should place importance on **what** the sender wants from the receiver rather than **how** the receiver should behave.

In Ruby, the _private_ and _protected_ keywords indicate the methods they are referring to may not be completely stable while the _public_ keyword indicates that a method is both stable and visible everywhere.

When we create a class we should always explicitly declare which of its interfaces are public and which ones are private.

A dependency on a private method of an external framework (or library I’d say in the case of the javascript world of npm) is a form of technical debt that should be avoided.

We should try to avoid depending on private interfaces as much as possible. In the cases that we need to use a private method, we should try to minimize the number of times it is referenced in our application.

The Law of Demeter is a guideline in Object Oriented Design that encourages loose coupling. In other words, this law states that one object should not know about the inner working of other objects or components.

The benefit of adhering to the Law of Demeter is that it can make our code more maintainable. Observing violations of the Law of Demeter can also help us to identify objects whose public interfaces are lacking.
