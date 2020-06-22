# Chapter 3 — Managing Dependencies

A single object cannot know everything. For that reason, objects need to talk to each other using messages. For any behavior we desire, an object either knows that behavior, inherits it, or knows another object that knows the behavior.

A dependency can be thought of as one object also having to be changed if the object it depends on changes.

Some degree of dependencies is inevitable when working with objects that must collaborate. With that being said, unnecessary dependencies are a bad design pattern because they make what would normally be minor code tweaks into major undertakings.

Taken to the extreme, unmanaged dependencies can make an application become such an entangled mess that it’s _easier to rewrite_ **everything** than to change _anything_.

A common mistake novice programmers make when writing tests if writing tests that are too tightly coupled to their code.

This makes refactoring their code incredibly costly because the tests will often break, even when the fundamental behavior of the code being tested does not change.

Although it may seem counterintuitive, an object often becomes less useful when it knows too much about other objects. When this happens, reusability goes down, and unnecessary dependencies are created.

Using dependency injection to shape our code can help us to better structure our code. It’s important to recognize that the responsibility of knowing the name of a class, and the responsibility of knowing what message to send that class may exist in two different objects.

Ideally, we would remove all unnecessary dependencies. If that is not possible because of some constraints, however, the next best alternative is to isolate and expose all of our unnecessary dependencies.

This can make our code easier to refactor when circumstances allow, and can also make the code more adaptable to an unknown future.

Metz suggests trying to remove argument-order dependencies. She states that one problem with passing multiple arguments is that if we later decide to switch the order of said arguments, all senders of those arguments will also need to be changed.

For that reason, Metz suggests using hashes to pass our arguments. Similarly, I think in JavaScript we could pass a single object that contains all of our arguments rather than passing a long list of arguments one by one.

Another side benefit of doing this is that our hash or object (in JavaScript) of arguments would also contain some keys that could serve to document what exactly our arguments should contain. This would make our code more readable for both others and our future self! :D

Of course, there are also valid use cases for using a combination of individual arguments passed in conjunction with an object (in JavaScript) or a hash (in Ruby).

In object-oriented programming, a function whose purpose is to create other objects is call a _factory_.

Dependencies always have a direction. In ideal circumstances, we would have our classes depend on things that change less often than they do.

In other words, if dependencies are necessary, we should try to depend on the most stable parts of our application rather than having our dependency direction flow from and rely on the most frequently changed parts of our app.
