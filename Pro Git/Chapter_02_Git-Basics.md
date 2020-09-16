# Chapter 2 – Git Basics

_Note from Cameron_: As of the time I’m writing these notes I have been a full-time software developer for over a year now.

With this chapter dedicating 35+ pages to Git basics, I’m going to focus these notes only on things I'm learning for the first time or personally felt were worth emphasizing.

I’m **not** going to note _every_ basic Git fundamental that I’ve already internalized after my last year on the job.

---

While I’ve long known about the command _git clone \<url>_, I thought it was interesting to note that we can also specify a custom directory name to clone our project into by specifying an additional argument like so:

```
git clone <url> myChosenDirectoryName
```

Moving on, the _git add_ command has several purposes including:

- Tracking new files
- Staging files
- Marking merge-conflicted files as resolved

While the _git status_ command offers pretty comprehensive information about which files are in which state, it’s somewhat verbose. For a more concise explanation of the state of our files we can use _git status -s_

Inside of our _.gitignore_ file we can specify patterns for what files we’d like to avoid adding to Git. The rules for the patterns inside of our _.gitignore_ are as follows (taken straight from the book):

- Blank lines or lines starting with _#_ are ignored.
- Standard glob patterns work, and will be applied recursively throughout the entire working tree.
- You can start patterns with a forward slash (/) to avoid recursivity.
- You can end patterns with a forward slash (/) to specify a directory.
- You can negate a pattern by starting it with an exclamation point (!).

From my understanding and what this chapter says, it seems like _glob patterns_ are more or less simplified regular expressions used to specify file names.
To see the specifics of code we’ve changed but not yet committed, we can use the _git diff_ command.

Alternatively, if we want to see changes we’ve staged that will go into our next commit we can use _git diff —staged_
We can add files, commit, and write a commit message inline using the following syntax:

```
git commit -a -m “your commit message will be here”
```

The _git rm_ command removes a file from both our Git repository as well as our local working directory. In other words, this commands basically deletes our file entirely.

While I’ve used _git log_ countless times before, I wasn’t previously aware that we can also pair this command with a number of arguments to customize exactly what information our log displays.

I think the most useful tip I gained from the _Viewing the Commit History_ section in this chapter is that we can use the _-p_ flag to show the differences introduces in each commit as well as limit how many entries are displayed using what I would call the “number flag”.

Here’s an example of the above syntax in practice:

```
git log -p -2
```

We can also use the _—stat_ option with _git log_ to see abbreviated stats for each commit. Another useful option is _—pretty_ which can change the format of the commits in our log.

For example, if we were viewing many commits and we wanted to keep each commit on a single line we absolutely could!

```
git log —pretty=oneline
```

If we wanted to only see commits our team made within the last two weeks we cold write:

```
git log —since=2.weeks
```

If we wanted to see the last commit that changed the number of occurrences of a string (for example to check the last commit that added or removed a reference to a specific function) we would use the _-S_ filter.
For example:

```
git log -S showConfirmModal
```

To prevent merge commits from cluttering up our log history we can add the following option (no-merges) like so:

```
git log no-merges
```

If we would like to unmodify a file we’ve already modified, we can do so by “checking out” that file. For example if we want to discard the changes we’ve made to _auth.js_ since our last commit we could do so using the following syntax:

```
git checkout — auth.js
```

To see which remote servers we have configured we can use the _git remote_ command.

The _git pull_ command is basically a combination of _git fetch_ and _git merge_.

Git has the ability to tag specific points in a repo’s history as being important. To see all of the existing tags in our project (if any) we can use the following command:

```
git tag
```

Git supports two types of tags:

- Lightweight tags which serve as a pointer to a specific commit.
- Annotated tags which are the more powerful and informative type of tags.

The developer community generally recommends using annotated tags over lightweight tags because of the additional information annotated tags provide.
Annotated tags are stored as full objects in the Git database, are checksummed, and have lots of information and features such as:

- Tagger name, email, and date
- Tagging message
- Able to be signed and verified with GNU Privacy Guard (GPG)

Here’s an example of how we could create an annotated tag:

```
git tag -a -m v1.4 “our tag message here”
```

In the above syntax we could of course specify a different version number than the example (v1.4) as well.

In addition, we can create a lightweight tag with the following syntax:

```
git tag v1.4-lw
```

It’s also possible to tag commits we’ve already made. We simply need to add the commit’s checksum to the commands we just discussed above. For example:

```
git tag -a v1.0 ourDesiredCommitChecksumHere
```

The _git push_ command does not automatically transfer tags to remote servers. We have to do that manually.
We can either push a single tag name:

```
git push origin <tagname>
```

or push all of our tags:

```
git push origin --tags
```

To delete a tag from our local repository we can write:

```
git tag -d <tagname>
```

The above _does not_ delete a tag from our remote repository. The simple way of deleting a remote tag is:

```
git push origin –delete <tagname>
```

While never necessary, Git aliases can make our Git experience more simple and productive.
Here’s an example of setting up an alias for the _git status_ command:

```
git config –global alias.st status
```

Now, instead of having to type _git status_ we could simply type _git st_.
