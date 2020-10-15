# Git Internals

_Note from Cam: This chapter basically just discusses how Git works under the hood._

## Plumbing and Porcelain

Git has around 30 or so popular subcommands such as _checkout_, _branch_, _add_, etc.

These user-friendly commands are usually called “porcelain” commands.

Subcommands that do low-level work and were originally designed to be chained together or called using scripts, however, are generally referred to as “plumbing” commands.

---

## Git Objects

Git is a content-addressable filesystem which basically means that for any content we insert into a Git repository, Git will give us a unique key which we can later use to retrieve that content.

By using the _git hash-object_ command, we can create a new data object and manually store it in our Git database.

### Tree Objects

A tree allows us to store a group of files together.

### Commit Objects

When we use the _git add_ and _git commit_ commands, Git basically creates a history for us under the hood by storing blobs for files that have changes, updating the index, writing out trees, and writing commit objects that reference top-level trees.

### Object Storage

All Git objects are stored in the same way (the only difference is whether they’re stored as blobs, commits, trees, or more rarely… tags).

---

## Git References

Because it can be difficult to remember SHA-1 values, Git also allows us to run subcommand by using references or “refs” that refer to these SHA-1 hashes.

If we want to update Git’s reference files we can do so using the _git update-ref_ command.

### Tags

The difference between the tag object and a regular commit object, is that a tag object generally points to a commit rather than pointing to a tree.

---

## Packfiles

Git occasionally packs up several objects into a single binary file called a “packfile” in order to save space and be more efficient.

---

## The Refspec

We can instruct Git on whether fetching should fetch all of the branches from our remote server or only some subset of them.

---

## Transfer Protocols

The “dumb” protocol is pretty rarely used these days as it’s difficult to secure or make private.

The “smart” protocol is a more common method of transferring data, but it requires the remote end be intelligent about Git — being able to read local data, figuring out what the client has and needs, etc.

---

## Maintenance and Data Recovery

Git will automatically run a command called “auto gc” on ocassion. The “gc” stands for garbage collect, and this command basically serves to gather up loose objects and place them into packfiles, consolidate small packfiles into one large packfile, and perhaps most notably remove old objects (roughly a few months old) that aren’t reachable from any commit.

If a commit isn’t recoverable via the _reflog_ command, that doesn’t necessarily mean all hope is lost.

We can run the following command to display all objects in our database that aren’t pointed to by another object:

```
git fsck —full
```

One potential issue with Git is that if someone accidentally adds a large file to our project that file will increase the size of our repository even if it’s later removed.

Why? Because Git stores the entire history of every revision of every file in our project (while not all other version control systems work in the same way).`

It’s possible to remove specific files from our history, however, in a case like this (see the actual book for more details).

---

## Environment Variables.

This section just describes some of the different variables we may be able to set or override when using Git.
