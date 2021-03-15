# Chapter 11 -- Asynchronous Programming

## Asynchronicity

In a _synchronous_ program things happen one at a time. In an _asynchronous_ program multiple things can happen at the same time. In other words, a given action doesn’t need to finish running before the next action can start running.

## Callbacks

If function “A” works asynchronously, the function that called “A” must also be asynchronous.

## Promises

One of the benefits of using promises is that they can help us write more readable asynchronous code (by avoiding large numbers of nested callback functions).

## Failure

JavaScript can detect when a promise rejection isn’t handled and will report this as an error.

## Networks Are Hard

Promises can be resolved or rejected only once.

## Collections of Promises

If even one promise inside of _Promise.all_ is rejected, _Promise.all_ itself will be rejected.

## Network Flooding

_Flooding_ is a type of network communication in which a piece of information is spread or flooded across every node in the network.

## Message Routing

_Flooding_ is not an effective approach if a given node only needs to talk to a single other node. _Flooding_ is inefficient in this case because it results in many useless data transfers.

## Async Functions

We can use the _Array.from_ method to convert an iterator or iterable value into an array. We can also use _Array.from_ to make a shallow copy of an existing array.

When _async_ functions are called they return a promise. Once something is returned in the body of an _async_ function, that promise is resolved. Otherwise, if at some point a rejection is thrown the promise would instead be rejected.

## Generators

When we call a generator function it returns an iterator. An _async_ function is a special type of generator function.

## The Event Loop

Regardless of the interval given, if we call _setTimeout_ from within a function, the function will have returned by the time _setTimeout_’s callback function is called.

A JavaScript environment will only run one program at a time. Because of this, it’s possible for slow-running code to delay other pieces of code.

## Asynchronous Bugs

The fact that JavaScript uses _explicit_ asynchronicity makes it easier to be aware of bugs caused by asynchronous gaps.
