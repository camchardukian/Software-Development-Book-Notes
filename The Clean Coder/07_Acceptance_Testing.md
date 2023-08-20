# Chapter 7 - Acceptance Testing

## Communicating Requirements

The _uncertainty principle_ states that when a business (or stakeholder) actually sees what they specified running in a system, they realize that it wasn’t what they wanted at all.

Usually once they see the requirement running, however, they do have a better of what they _actually_ want.

## Acceptance Tests

One way engineers can combat ambiguity is through _acceptance tests_.

Acceptance tests force clear communication, clarity, and precision. Everyone that in good faith agrees to the acceptance tests is indicating that they understand what the planned behavior of the system is.

Acceptance tests should be automated using tools like _Selenium_ and _Cucumber_. While there’s a time for manual testing, at this point in the software development life cycle the cost savings of automation are too large to consider manual testing.

### Acceptance Tests and Unit Tests

Unit tests are written _by_ programmers _for_ programmers while acceptance tests are written _by_ the business _for_ the business.

Unit tests describe the lowest level structure and behavior of the code.

Acceptance tests are formal requirements documents that specify how the system should behavior from the business’ point of view.

### Single Responsibility Principle (SRP)

The _Single Responsibility Principle (SRP)_ states that you should separate things that change for different reasons and group together things that change for the same reasons.

### GUI Tests

GUI tests are fragile. It’s a good idea to try to decouple the GUI from the business rules and replace the business with stubs while testing the GUI itself.

GUI tests should be kept to a minimum. GUI test are fragile because GUIs are volatile, and the more GUI tests we have the less likely we are to keep them.
