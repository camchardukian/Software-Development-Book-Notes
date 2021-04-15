# Chapter 20 -- Node.js

## Background

Asynchronous programming is useful for sending and receiving data to and from multiple devices without having to have complicated thread management and synchronization.

## The Node Command

We can run the _node_ command along with the name of a file to run said file. If we don’t include a file, we’ll receive a prompt where we can type our JavaScript code that we would like to run.

## Modules

If we do not pass a string that looks like a relative or absolute path to _require_, Node will assume the module we’re trying to load is either a built-in module or a module installed in our node_modules.

## Installing With Npm

Unlike some other package managers, when we install packages with NPM it installs the packages in the current working directory rather in the root directory or another central place.

## Package Files

We can create a _package.json_ either manually or by running _npm init_.

## Versions

The _npm publish_ command is used to publish packages to the NPM registry.

## The File System Module

We can use the _fs_ module for synchronous or asynchronous reading, writing, appending to, and deleting of files.

## The HTTP Module

We can create an HTTP server by using the _createServer_ method from the HTTP module.

## Streams

NodeJS allows us to read and write data in manageable chunks called _streams_. Streams allow us to handle data in a more efficient manner. If we had a video streaming website for example, we could allow the user to download a small chunk of a video and begin consuming it immediately rather than requiring them to download the entire video before they were able to begin watching.

## A File Server

The _mime_ package can help us ensure we set the _Content-Type_ header correctly when returning dynamic file values.

HTTP standards state that quests should be _idempotent_. _Idempotency_ is the idea that the first application of an operation and subsequent operation applications should produce the same result.
