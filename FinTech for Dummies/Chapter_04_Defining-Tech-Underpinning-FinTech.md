# Chapter 4 — Defining the Tech Underpinning FinTech

## APIs

_APIs_ (application programming interfaces) can be used to speed up the development process and reveal important data to customers/partners without revealing proprietary code.

_REST_ stands for REpresentational State Transfer. RAML stands for Restful API Modeling Language and allows REST APIs to be formally defined. Using RAML we can define every resource and operation exposed by a microservice.

## Events

Event-driven software is easier to write than procedural software, but it can be harder to test. The successor to event-driven software is asynchronous software.

## Agile

The _waterfall approach_ to software development is intuitive and produces a significant amount of documentation.

Unfortunately, the waterfall approach comes with the risk of not detecting risks or other issues until it may be too late.

_Agile_ on the other hand focuses on iterative development which results in potential issues or negative feedback being discovered much earlier.

## Microservices

_Microservices_ adhere to three modes of scalability:

1. Load-balanced distribution
1. Scaling by data partitioning
1. Scaling via functional decomposition

Some of the key benefits of microservices are that they:

- Reduce time to market
- Have continuous delivery and testing
- Errors are easier to isolate and fix
- Each service can be separately maintained, deployed and scaled

Some of the drawbacks of microservices are that they may make it difficult to:

- Maintain data consistency across multiple data stores
- Define the microservices architecture
- Define the correct set of functions in a service
- Coordinate the coupling of services in an application

Microservices rely on _containerization_, a process that involves delivering the complete application with all of its configuration files and dependencies in a clean and efficient release process.

Microservices are highly composable and can be used in various combinations to deliver different business needs.

A typical microservices development team may include a project manager, a lead developer, additional software developers working under the lead, QA resources, and business analysts.

## Rapid Application Development

The _Rapid Application Development_ (RAD) process was developed to shorten time-to-market.

Some feature of the RAD process that contribute to this increased development speed are:

- Less specific spec development
- Rapid review and continuous prototyping
- Adding business-driven functionality to the early stages of requirement gathering

## Batch Processing

It isn’t necessary to convert all _batch processing_ to real-time processing. Doing so isn’t always cost-effective either.

If the data produced is stable and infrequently reviewed or changed, it probably makes sense to keep the existing batch processing processes in place.

## Data Management

The types of data we’re likely to encounter in FinTech are:

- Static data
- Reference data
- Securities data
- Legal entity data
- Trade data
- Position data
- Market data/pricing feeds
- Derived data/results data

The types of data management technologies we may end up using are:

- Relational databases
- Big data technologies
- Time-series databases
- Array databases
- Object databases
- Document databases

## CPUs and GPUs

_CPUs_ (central processing units) and _GPUs_ (graphical processing units) tend to be better at different types of tasks.

A system can get the best performance by splitting the system’s workload between the two based on their strengths.

Very generally speaking, CPUs tend to be more suited for complex operations while GPUs may be better for simple repetitive operations.

## Choosing a Programming Language

### Python

Created in 1980, one appeal of _Python_ is that it doesn’t require standard compiling.

The benefit of this is that it makes debugging easier and more efficient.

Other benefits of using Python for FinTech are that Python is one of the easier languages to learn, it’s often used in AI/ML development (areas seen as being a large part of FinTech’s future), and that Python is already used by many large banks.

Some drawbacks of using Python are that it requires a lot of memory, it’s not very good for creating mobile applications, and errors often are not anticipated until runtime.

### Julia

Created in 2009, _Julia_ is an open language created for the computational science and analytics community.

Some pros of Julia are that it’s faster than Python, and that it was specifically designed to perform well at many of the operations FinTech firms most often need.

The main con of Julia is that it’s a young language with a fairly small user group and community.

### R

Created in 1990, _R_ is an open source language whose strength is statistical and data mining computing.

Its biggest weaknesses are that it has a steep learning curve and that its spectrum of use cases may be narrower than a language like Python.
