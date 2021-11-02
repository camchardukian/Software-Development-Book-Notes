# Chapter 11 -- Systems

## How Would You Build a City?

It's probably not possible for you to manage a large software project entirely on your own.

For that reason, it's important you keep levels of abstraction clean at the system level.

## Separate Constructing a System from Using It

We should note that _construction_ and _use_ are two different processes that should have a separation of concerns.

### Separation of Main

It's possible to separate construction from use by having all of our modules point to a function called "main" that will build all the objects necessary for the system.

_Main_ will then pass those constructed objects to the application which then simply uses them.

### Factories

Factories can be used to dictate _how_ objects are created while still allowing the application itself control of _when_ the objects are created.

### Dependency Injection

We can use _Inversion of Control_ (IOC) to move secondary responsibilities off of one object and instead move those responsibilities to other objects that are dedicated to those responsibilities.

## Scaling Up

It's easier to scale up your system later on if you start with test-driven development, clean code, and proper separation of concerns.

### Cross-Cutting Concerns

_Aspect-oriented programming_ (AOP) is an approach to programming we can use to increase modularity in our programs and better separate cross-cutting concerns.

## Java Proxies

Java Proxies have use cases, but it can also be difficult to produce clean code with them because of the quantity of code and logical complexity that accompany them.

## Pure Java AOP Frameworks

POJO stands for _Plain-Old Java Objects_.

## AspectJ Aspects

AspectJ is an extension of Java that makes it easier to separate concerns through aspects.

## Test Drive the System Architecture

Doing a _Big Design Up Front_ (BDUF) can sometimes be harmful because of the sunk-cost fallacy.

By investing such large amounts of effort upfront trying to design _everything_ before implementing _anything_, it can be difficult to change our design to accommodate evolving circumstances.

## Optimize Decision Making

By designing a system with modularized concerns we're able to make better decisions.

Why? Because decisions can be more easily delayed until a greater quantity of information is available upon which to make the decisions.

## Use Standards Wisely, When They Add Demonstrable Value

Standards can provide a lot of value as long as they do not take too long to create, and they are kept up to date with the needs they are intended to serve.

## Systems Need Domain-Specific Languages

_Domain-Specific Languages_ (DSLs) can help use to write code using the same vocabulary the domain experts would use.

This decreases the likelihood of miscommunications and mistranslations.
