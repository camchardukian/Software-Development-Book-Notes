# Chapter 13 -- Concurrency

It is very difficult to write clean concurrent programs. It's easy to write multithreaded code that seems to work on the surface, but that will break when the system is placed under stress.

## Why Concurrency?

Using concurrency can help you decouple _what_ gets done from _when_ it gets done.

### Myths and Misconceptions

Concurrency has the potential to improve a system's performance, but simply using concurrency does not guarantee a system's performance will improve.

Bugs that occur in a concurrent system are often difficult to replicate.

A concurrent program will often require a different design strategy than a single-threaded system.

## Concurrency Defense Principles

### Single Responsibility Principle

Because the design of concurrency-related code can be complex and result in difficult to diagnose bugs, it's recommended you keep our concurrency-related code separate from other code.

### Corollary: Limit the Scope of Data

You should try to limit the number of places shared data can be updated.

### Corollary: Use Copies of Data

The expense of copying objects is often worth not having to share data.

### Corollary: Threads Should Be as Independent as Possible

You should strive to write our threaded code in such a way that each thread is as independent as possible.

For example, you could avoid synchronization requirements by having each thread process one client request, having its required data come from an unshared source, and storing said data as local variables.

## Know Your Library

By understanding your programming language and libraries deeply, you're more likely to be aware of additional features and methods to help you improve the concurrent-related code you write.

## Know Your Execution Models

There are many different ways we could partition behavior in a concurrent application.

### Producer-Consumer

This method of partitioning behavior in a concurrent application involves producer threads creating work and placing it in a queue or buffer.

Consumer threads then consume whatever is in the queue. Both the consumers and the producers signal to each other and both will sometimes have to wait on the other.

### Readers-Writers

It's difficult to balance the needs of a shared resource betweens readers and writers.

If you emphasize the readers' ability to continually access the information, the writer may not be able to update the information and you're left with stale information.

On the other hand, if you never limit the writer's ability to update the information it could impact the readers' ability to consistently access said information.

### Dining Philosophers

Unless a system is carefully designed, it's possible for many problems to occur as a result of different processes competing for resources.

## Beware Dependencies Between Synchronized Methods

Whenever possible, it's recommended to avoid using more than one method on a shared object.

When using multiple methods is unavoidable, you can use _Client-Based Locking_, _Server-Based Locking_, or an _Adapted Server_ to fix the issue.

## Keep Synchronized Sections Small

Locks are expensive because they can add overhead and cause delays.

As a result, you should only lock/guard critical parts of your code, and you should keep those parts that must be locked/guarded as small as possible.

## Writing Correct Shut-Down Code Is Hard

Designing a system that shuts down gracefully can be even more difficult than designing a system intended to run forever.

For that reason, the author recommends you think about shut-down and get it working early on in the process of building a system.

## Testing Threaded Code

Writing good tests can help you detect potential problems as well as minimize risk.

### Treat Spurious Failures as Candidate Threading Issues

While it can be difficult to replicate the occurrence of bugs in threaded systems, it's also dangerous to ignore the bugs. Why?

Because you risk writing additional code and building additional functionality on top of what is actually a faulty approach.

### Get Your Nonthreaded Code Working First

Try to track down and fix bugs in your nonthreaded code before worrying about threaded bugs.

### Make Your Threaded Code Pluggable

Code related to concurrency should be written in such a way that it can be run in several configurations.

### Make Your Threaded Code Tunable

By finding a way to time the performance of your system under different configurations, you can use trial and error to determine the right balance of threads.

### Run with More Threads Than Processors

When tasks swap more frequently, you're more likely to encounter code that causes deadlock or that is missing a critical section.

### Run on Different Platforms

Different operating systems have different threading policies. Because multithreaded code works differently in different environments, you should try to run your code early and often on all target platforms.

### Instrument Your Code to Try and Force Failures

In a language like Java, you can increase your chances of catching rare occurrences (and the rare bugs that may accompany them) by adding calls to methods such as _Object.wait()_, _Object.sleep()_, _Object.yield()_, _Object.priority()_.

### Hand-Coded

One option for executing code instrumentation is inserting calls to methods like _Object.wait()_, _Object.sleep()_, _Object.yield()_, _Object.priority()_ manually.

Unfortunately, this ends up being more or less a shotgun approach and it could also slow down your application in production if you forget to remove those method calls.

In addition to the previous problem, there's the issue of even knowing the appropriate places to insert these methods, and knowing which specific method to choose.

### Automated

There are tools and technologies that allow us to programmatically instrument our code.
