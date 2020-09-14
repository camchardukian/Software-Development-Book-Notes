# Chapter 1 – Getting Started

> “Version control is a system that records changes to a file or set of files over time so that you can recall specific versions later.”

Some of the benefits of version control include:

- Reverting selected files back to a previous state
- Reverting the project back to a previous state
- Comparing changes over time
- Seeing who last modified something
- Seeing who introduced an issue and when it was introduced

_Centralized Version Control Systems_ (CVCSs) were developed to help developers collaborate with developers on other systems.

This was an improvement over _local version control systems_ but also had many downsides.

For example, if the central server went down nobody would be able to save versioned changes to anything they’d been working on until the server was back up.

It would also be possible to lose the entire history of the project if the central database became corrupted.

_Distributed Version Control Systems_ (DVCSs) mirror the full history of a repository rather than simply mirroring the most recent snapshot of files.

The Linux development community (especially Linux’s founder Linus Torvalds) created GIT in 2005. The goals of GIT were:

- Speed
- Simplicity
- Strong support for non-linear development
- Fully distributed
- Able to handle large projects efficiently

SHA-1 hashes are 40-character strings GIT uses to ensure we never lose information in transit or corrupt files without GIT being able to detect it.

GIT has three main states our files can reside in:

- **Modified** – a file has been changed but not yet committed to the database.
- **Staged** – a modified file has been marked in its current version to go into our next commit snapshot.
- **Committed** – a file’s data is safely stored in our local database.

The three main sections of a GIT project are:

1. The working tree
1. The staging area (or in technical terms the “index”)
1. The Git directory.

We can use **git config** to configure different aspects of how GIT looks and operates. Using the _git config_ command we can configure the username/email associated with our commits, our default text editor, our default branch name and more!

To get help for how to use a git command, we can use the following syntax:

```
git help <verb>
```

For example, if we want more information about _git config_ we would write:

```
git help config
```

Otherwise, if we understand what a command does and simply want a refresher on what options are available we can use:

```
git <verb> -h
```
