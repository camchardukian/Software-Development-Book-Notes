# Chapter 10 -- Modules

## Modules

Modules are used to specify which other pieces of the program the module is dependent on, and what functionality the module can provide for other modules.

Relations between different modules are called _dependencies_.

It isn’t necessary to always design a module structure for your program from the beginning.

Often it makes more sense to organize things once you have a better grasp of how the program will work and how different modules will interact with each other.

## Packages

Packages are chunks of code that can be copied and installed.

Packages usually come with documentation explaining what the package does and what other packages are dependencies of the package.

NPM provides the infrastructure the JavaScript community needs to upload and download packages via their online service, as well as a program (bundled with Node) to install and manage packages.

## Improvised Modules

A module system was only first built into JavaScript in 2015.

## Evaluating Data As Code

A good module system should wrap code in a function value so that the wrapped code gets its own scope.

## CommonJS

Node.js as well as most packages on NPM use CommonJS.

## ECMAScript Modules

In 2015 the _import_ keyword was added to JavaScript.

## Building and Bundling

Tools called _bundlers_ are used to roll our programs into a single big file before we publish them to the web. This significantly decreases the time it takes for our program to load.

Tools called _minifiers_ are used to make a JavaScript program smaller by removing comments and whitespaces, renaming variables, and replacing blocks of code with equivalent yet more concise pieces of code.

## Module Design

A well designed module should be both easy to understand, and use data structures in such a way that the module is easy to use with other modules.
