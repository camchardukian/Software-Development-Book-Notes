# Chapter 8 — Combining Objects with Composition

Just like we can compose music by combining many notes together, we can also compose objects by combining simple objects into more complex objects.

Metz writes,

> “In composition, the larger object is connected to its parts via a has-a relationship. A bicycle has parts. Bicycle is the containing object, the parts are contained within a bicycle.”

It would then seem to me that composition can be described via ‘has-a’ relationships, while inheritance may be described as being an ‘is-a’ relationship.

In OOP, an object that manufactures other objects can be called a ‘factory’.
_Delegation_ is when one object receives a message and then forwards said message to another object.

_Aggregation_ is a term that can be used to discuss a contained object that has an independent life. The example given in this chapter is that while a university department may close, its professors will continue to exist.

Conversely, composition differs in that the contained object dies along with its container. If we destroy a meal, the appetizers of said meal will also be gone.

In general, we should lean towards using composition instead of inheritance. Composition contains fewer built-in dependencies than inheritance. Thus, we should opt to use composition over inheritance unless we can explicitly defend why using inheritance would be better.

One of the biggest benefits of inheritance is that correctly modeled hierarchies are extremely flexible. For example, adding a new subclass to an existing hierarchy rarely, if ever requires changes to existing code.

Another strength of inheritance is that it is by nature exemplary. Correctly modeled hierarchies offer guidance for how we should write code to extend them.

Of course, inheritance isn’t without its own weaknesses.

The first problem with inheritance comes from attempting to use it to solve the wrong problem. If we model a hierarchy incorrectly, we’ll eventually be forced to duplicate or restructure our code.

The other possible issue is that other developers may want to access the behavior we have created, but not be able to tolerate the dependencies our inheritance hierarchy demands.

I feel like this is a great insight:

> “Objects built using composition differ from those built using inheritance in two basic ways. Composed objects do not depend on the structure of the class hierarchy, and they delegate their own messages.”

One benefit of using composition is that well-composed objects are easily usable in new and unexpected situations. Composition is also transparent in that it’s generally easy to see what each small part’s responsibility is.

On the other hand, a composed object may rely on a large number of parts. This may result in an object whose responsibility is unclear — even if the responsibility of each of its individual parts was clearly defined. Composition also fails to provide automatic delegation in the same way inheritance is capable of.

In general, Metz recommends using inheritance for _is-a_ relationships, duck types for _behaves-like-a_ relationships, and composition for _has-a_ relationships.

Finally, it’s important to note that the more parts an object has, the more likely it is that we should use composition to model said object.
