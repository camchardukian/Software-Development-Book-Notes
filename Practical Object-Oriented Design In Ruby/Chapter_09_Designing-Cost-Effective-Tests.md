# Chapter 9 — Designing Cost-Effective Tests

## Intentional Testing

Good tests are written in a way such that they can survive code refactorings without the tests themselves needing to be changed.

> “The true purpose of testing, just like the true purpose of design, is to reduce costs.”

The reason many software developers dislike testing is because they write tests that require a disproportionate amount of effort in comparison to the value they provide.

Metz argues, however, that the solution to this problem isn’t to stop testing. The solution is to get better at writing tests.

Five benefits of testing include:

- Finding bugs
- Supplying documentation
- Deferring Design Decisions
- Supporting Abstractions
- Exposing Design Flaws

To elaborate on the last point, bad design results in a situation where testing is difficult. With that being said, it’s also possible to write poor tests for well-designed code. For tests to lower our costs, we need both a well-designed application and well-designed tests.

In the context of OOP we should concentrate on testing the incoming and/or outgoing objects that cross an object’s boundaries.

If an outgoing message has no side effects, the outgoing message does not need to be tested. On the other hand, an outgoing message with side effects should be tested.

As a general guideline, Metz suggests we test our messages like so:

- Incoming messages should be tested for the state they return.
- Outgoing command messages (outgoing messages with side effects) should be tested to ensure they get sent.
- Outgoing query messages (outgoing messages without side effects) should not be tested.

While there are situations in which it may make sense to write code before writing tests, we should err on the side of writing tests before the rest of our code.

---

## Testing Incoming Messages

> “Incoming messages make up an object’s public interface, the face it presents to the world. These messages need tests because other application objects depend on their signatures and on the results they return.”

While Metz opens this section with the above statement, she later provides a caveat to it. Metz informs us that the one exception to the above rule is if an incoming message has no sender.

An incoming message that no one ever sends has no purpose. In fact, an incoming message with no senders should be deleted entirely to avoid adding unnecessary testing and maintenance costs.

Another key takeaway offered in this section is that tests run fastest when they execute the least amount of code. What often leads to testing an unnecessary amount of bad code? You guessed it, poor design.

---

## Testing Private Methods

Private methods should be invoked by public methods that already have tests, and thus the private methods themselves do not need tests.

Another factor to consider is that private methods are unstable. Testing a part of our application that is likely to change means acknowledging that we’re also likely going to need to rewrite our tests.

Overall Metz advises us,

> “The rules-of-thumb for private testing methods are thus: Never write them, and if you do, never ever test them, unless of course it makes sense to do so. Therefore, be biased against writing these tests but do not fear to do so if this would improve your lot.”

---

## Testing Outgoing Methods

Query messages (which are again outgoing messages without side effects) do not need to be tested. Command messages on the other hand _do_ need to be tested.

With that being said, we only need to test that a command message is sent. The responsibility for testing a message’s return value lies with the receiver rather than the sender.

## Testing Duck Types

Typically it is better to write tests before making changes to our code. There are cases, however, where if our code uses some antipattern(s) that it may be better to immediately refactor the code though.

---

## Testing Inherited Code

As far as testing inheritance is concerned, the first goal is proving all objects in the hierarchy honor their contract. In other words, we need to prove that all subtypes should be substitutable for their supertypes.

It’s also important to write shared test(s) to prove that all of the subclasses of a superclass meet any requirements posed by the superclass. This will ensure new subclasses of a superclass do not deviate from the requirements of the superclass.

These tests can also serve as documentation to help newly onboarded developers quickly understand the requirements of a superclass.
