# Chapter 1 Object-Oriented Design

> “Object-oriented design (OOD) requires that you shift from thinking of the world as a collection of predefined procedures to modeling the world as a series of messages that pass between objects.

Metz says that the programming techniques that make code a joy to write overlap with those that most efficiently produce software. Suffering while we write code _isn’t_ the most cost-effective way to produce quality software.

The reason design is important when writing software is that things change. Whether its changing requirements from clients or new features demanded from customers, software typically is not stagnant.

Metz suggests that applications that are flexible and easy to change are fun to work with. Likewise, applications where making changes is an expensive and strenuous process… those applications are not much fun to work with.

Design becomes more important as our applications become larger and we’re no longer able to hold the entire application in our head.

Design can be defined as the art of arranging code with the purpose of reducing the costs of future changes.

Some of the most popular design principles include SOLID (Single Responsibility, Open-Closed, Liskov Substitution, Interface Segregation, Dependency Inversion), DRY (Don’t Repeat Yourself), and the Law of Demeter (LoD).

Design patterns can be defined as simple and elegant solutions to specific problems that we can use to make our designs more flexible, modular, reusable, and understandable.

While we may already have design patterns that are nearly perfect for solving object-oriented programming’s most common problems, developers still need to be careful to avoid misapplying patterns.

Novice developers in particular tend to use patterns incorrectly which results in complicated/confusing code.

Metz suggests that the Agile software movement can support the creation of a well-designed OO application because the iterative nature of Agile gives us a regular feedback loop that allows us to regularly adjust our designs.

Agile believes that customers can’t define the software they want before seeing it. For that reason, it’s best to build our software one small bit at a time, collaborating with our customers/clients each step of the way.

Given that this is true, it’s pointless to do a Big Up Front Design (BUFD), and impossible to give an accurate estimate of when an application will be completed (because we can’t know from the start exactly what the application will eventually do).

> “Agile processes _guarantee change_ and your ability to make these changes depends on your application’s design.”

Metrics software that measures the quality of code cannot prove the design of our code is good. They can pretty reliably point out bad design, however.

Making design compromises should be looked at like borrowing time from the future. That’s why the software industry refers to resulting effects of such compromises using the term _technical debt_.

The act of design should minimize the amount of time required to complete/maintain a project over its lifetime while also accepting tradeoffs necessary to ensure the project is delivered on time.

Every possible data type and operation is built into the syntax of a procedural programming language. Procedural programming languages separate data and behavior.

Object-oriented programming languages combine data and behavior into an object. Objects can invoke the behaviors of other objects via the sending of messages.

Class-based object-oriented languages like Ruby allow us to define classes. These classes provide a blueprint and can be used to create or _instantiate_ new instances of objects with said class. Even Ruby’s predefined classes such as the **String** class are objects themselves (because they are instances of the _Class_ class).

In short, the point of this chapter seems to be to emphasize the importance of design in software development projects, while also introducing the idea that simply understanding design theories is not enough.

More important is knowing how to apply said theories in the right situations, at the right times, in the right amounts.
