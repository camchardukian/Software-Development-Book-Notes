# Git Tools

_Note from Cam: This chapter is a MONSTER. We’re covering roughly 120 pages of content here so I’m going to separate the notes for this chapter by section just as this chapter in the book is split into 14 sections. Here we go..._

---

## Revision Selection

We can inspect a commit with the _git show_ command followed by that commit’s SHA-1 hash.

For example:

```
git show d132d254646f741d981b2be3d7ae02be45347bc3
```

The cool thing is we don’t necessarily need to include all 40 characters of the SHA-1 hash. We just need to include at least 4 characters and ensure that no other hash in our database has the same prefix.

The following example would produce the same result as the previous code sample:

```
git show d132d254646f
```

_On a quick side note…_

While it’s possible for two object in our repository to randomly hash to the same SHA-1 value, the odds of this happening are so incredibly low (about 1 in 1 million billion billion) that this is an issue that’s trivial to worry about.

### Branch References

If we run the following command:

```
git show feature/login
```

we would see the commit that’s currently at the top of the “login” branch.

### RefLog Shortnames & Ancestry References

A useful tool we always have in our Git tool belt is called _git reflog_. Git reflog is basically a storage log of information that tracks every time the tip of our branch is updated for some reason.

But… it’s important to note that this “reflog” information is strictly local.

In practical terms, it seems like the most practical use of reflog would be to restore commits from a branch we’ve accidentally deleted.

In any case, here’s the basic syntax:

```
git reflog
```

Moving on, Git gives us the power to specify commits via ancestry. For example, if we want to find the parent of a commit we would write “git show” + the SHA-1 hash of the commit in question + a carat symbol:

```
git show dc91ab4^
```

We can also specify a number after the carat to identify whether we want the second parent, third parent, etc:

```
git show dc91ab4^2
```

### Commit Ranges

Here’s a neat trick… We can use the following syntax to see what commits we have on our local branch that are not yet reachable from origin/master:

```
git log origin/master..HEAD
```

---

## Interactive Staging

We can use _git add_ along with the _--i_ option to add files to Git, obtain a lot of information about the files in our staging area, and also gain access to a “What now” prompt that gives us many different command options. Here’s the example syntax:

```
git add --i
```

It’s possible to stage parts of a file by entering “p” after receiving the “What now” prompt from the previous command.

---

---

## Stashing and Cleaning

It seems “git stash save” is being deprecated and we should transition to using “git stash push”.

While these two commands offer the same base functionality, _git stash save_ accepts only a single argument — the stash message.

On the other hand, _git stash push_ accepts two arguments:

1.  A stash message using the _-m_ option.
1.  A list of files to stash.

Normally when we apply a stash previously staged files will not be restaged. If we would like to override this behavior, however, we can!

We just need to include the _—index_ option like so:

```
git stash apply —index
```

While _git stash pop_ will apply a stash and immediately drop it from our stash list, we can also manually drop stashes by running _git stash drop_ plus the number of the stash we would like to drop.

For example, if we wanted to drop the third stash in our list/stack we’d run:

```
git stash drop 2
```

This next trick is really cool! We can add all of our staged content to a stash while still leaving it in the index using the following command:

```
git stash —keep-index
```

This would allow us to save a copy of our staged content while continuing to work on it. We wouldn’t even need to reapply a stash because the staged content would never have been removed from our index in the first place!

We can use the _git clean -f_ command to remove untracked files/directories from our repository.

The most practical usage of this command I imagine would be removing a large number of untracked files at once rather than having to go to each file/directory and delete them individually.

---

## Signing Your Work

While Git is cryptographically secure, having contributors sign their commits with GPG keys can help us verify commits are coming from a trusted source.

We can generate a GPG key with the following command:

```
gpg —gen-key
```

We can configure Git to use our key from the previous step like so:

```
git config —global.user.signingkey [ourKeyNumberHereWithoutBrackets]
```

---

## Searching

### Git Grep

We can use the _git grep_ command to search any committed tree, working directory, or the index for a string or regular expression. If we wanted to search for the string “subtract” we could do so using the following syntax:

```
git grep subtract
```

One benefit of using the _git grep_ command over other search tools is that it enables us to search through any tree in Git (included older versions of our code that we are no longer checked out to).

### Git Log Searching

We can search to see which commits changed the number of occurrences of a given string using the following command:

```
git log -S “ourStringHere”
```

We can search the history of changes made to a function using the following syntax:

```
git log -L :functionName:pathToFileContainingThisFunction
```

---

## Rewriting History

One may enjoy a lot of freedom when rewriting their local commit history. This _isn't_ the case after one has pushed their work, however. In general, we should consider pushed work as final unless there is a good reason to change said work.

Modifying one’s last commit message is as easy as entering the following command:

```
git commit —amend
```

I’ve long known about the ability to amend commits. The thing I didn’t learn until today, however, is that amending changes the SHA-1 of our commit.

This means we may want to avoid amending our latest commit if it has already been pushed.

It’s important to note that when we do an interactive rebase, commits will be listed in reverse order (compared to git log which lists commits in the order the commits were made).

I knew it was possible to “combine” multiple commits into one using _git squash_. I didn’t know, however, that the inverse to _git squash_ also exists in the form of splitting commits!

---

## Reset Demystified

To undo some commits we’ve made locally (but still keep the changes to the files) we can run _git reset —soft HEAD~[number]_ with “number” being the number of commits we want to move **HEAD** back.

For example, if we have three commits we do not want we would write:

```
git reset —soft HEAD~3
```

This would keep our files that were previously committed and move them back one step to the staging area.

Alternatively, using the same command without the “—soft” option would move the files two steps back to our working directory:

```
git reset HEAD~3
```

Finally, running _git reset_ with the “—hard” option will make our working directory equivalent to where HEAD pointed, our specified number of commits ago.

---

## Advanced Merging

If at all possible, we should try to make sure our working directory is clean before attempting a merge that may have conflicts. This allows us to undo any anything we try during the attempted merge.

### Merge Conflicts

We can use the following command to attempt to revert back to the state before we ran our merge:

```
git merge --abort
```

If we want to ignore conflicts that result from whitespace during a merge, it’s possible to ignore whitespace completely:

```
git merge -Xignore-all-space whitespace
```

Otherwise, to treat sequences of one whitespace or multiple whitespace characters as equivalent we can run:

```
git merge -Xignore-space-change whitespace
```

### Undoing Merges

Git gives us the option of making a new commit which undoes all of the changes from an existing commit. We can ‘revert’ a commit using the following syntax:

```
git revert theHashOfTheCommitWeAreReverting
```

### Other Types of Merges

We can pass the _merge_ command either the _Xours_ or _Xtheirs_ option if we would like Git to automatically choose one side or the other instead of us having to manually solve conflicts.

---

## Rerere

Rerere stands for “reuse recorded resolution”. This functionality allows Git to remember how a given conflict was solved so that identical future conflicts can be solved automatically.

To enable the “revere” functionality we can run the following command:

```
$ git config --global rerere.enabled true
```

---

## Debugging with Git

We can run _git blame_ plus a path to the file we want to analyze to see which commit (as well who was the author of the commit) that last modified each line of code in our file.

Here’s an example:

```
git blame src/containers/Calculator/Calculator.tsx
```

Another cool debugging tool Git offers is _git bisect_. The _bisect_ command does a binary search through our commit tree to help us quickly identify which commit introduced an issue.

Basically how this works is we start the process by running _git bisect start_.

We then specify that the current commit is broken by running _git bisect bad_.

Finally, we can provide a tag or hash of the last known commit where everything was working correctly.

Here’s the example syntax straight from the book:

```
git bisect start
git bisect bad
git bisect good v1.0
```

Once we’ve entered the above information, Git will calculate how many commits have occurred between the current broken commit and the last known working commit.

Git will then check out to the middle commit between these two points. If there are no issues, we can enter _git bisect good_, to continue the search — this time between the new final known working commit and our current broken commit.

We can repeat this as many times as necessary until we find a broken commit. We can then run _git bisect bad_ to get more information about which files were modified in the broken commit to get an idea of what may have broken our application.

Finally, we can run _git bisect reset_ to reset our HEAD back to where it was before we started this entire process.

---

## Submodules

### Starting with Submodules

Submodules allow us to keep a Git repository as a subdirectory of another Git repository.

To add a submodule we use the _git submodule add_ command along with a path (absolute or relative) of the project we would like to track. For example, if we would like to add the “DbConnector” library we would enter the following command:

```
git submodule add https://github.com/chaconinc DbConnector
```

The _.gitmodules_ file stores the mapping between the project/library’s URL and the local subdirectory we’ve pulled it into.

One important thing to note is the _.gitmodules_ file will be tracked by Git and pushed/pulled just like the rest of our project. As such, it’s recommended to use a url other users will have access to if possible.

### Cloning a Project with Submodules

When we clone a project that contains submodules we’ll get the directories that contain submodules, but none of the files within those directories.

To get the files, we need to run _git submodule init_ (to initialize our local configuation files) as well as _git submodule update_ (to fetch all the data from that project and check out to the appropriate commit.

### Publishing Submodule Changes

When we push our code, it’s important to also make sure we push any changes we’ve made to our submodules.

It’s possible to check if our submodules have been pushed properly before we push our main project.

There are two different ways of doing this. The “check” approach and the “on-demand” one.

The “check” approach will make our _git push_ fail if any of the committed submodules changes haven’t yet been pushed.

Here’s the example syntax:

```
git push —recurse-submodules=check
```

Alternatively, the “on-demand” approach will try to push our updated submodules to their respective remotes (if necessary) before pushing the main project.

In the event the submodule push were to fail for some reason, the push to the main project would also fail. Here’s the basic syntax for the “on-demand” approach:

```
git push —recurse-submodules=on-demand
```

Another cool thing to note is that it’s possible to config Git to automatically perform either of these approaches before each push of the main project by running either:

> git config push.recurseSubmodules check

or:

> git config push.recurseSubmodules on-demand

### Submodule Tips

There is a submodule _foreach_ command to run a given command on each submodule.

For example, if we wanted to stash all of our submodules we could do so:

```
git submodule foreach ‘git stash’
```

---

## Bundling

Git is capable of “bundling” all of its data into a single file. This file can then be put on a USB stick or sent to someone on our team via email. This could be useful for cases in which our local network is down or we don’t have access to it for some other reason (such as working off-site).

Here’s an example of using this command to create a file called _repo.bundle_ checked out to the head of our master branch:

```
git bundle create repo.bundle HEAD master
```

If we were the receiver of the newly created bundle, we could clone it into a new directory like so:

```
git clone repo.bundle repo
```

We can use the _git bundle verify_ command to verify a file is valid git bundle and that we have the proper ancestors to properly reconstitute it.

---

## Replace

The objects in Git’s database may be unchangeable, but we can use the _replace_ command to instruct Git that every time it refers to a certain object in Git it should pretend it’s referring to another object.

---

## Credential Storage

By using SSH transport for connecting to remotes we can securely transfer data without needing to type in our username and password.

This isn’t possible with HTTP protocols, however which is why Git has a credentials system that can help with this.
