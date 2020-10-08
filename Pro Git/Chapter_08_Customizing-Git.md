# Customizing Git

## Git Configuration

To see all of the configuration options our version of Git supports we can run:

```
man git-config
```

One cool config option we should be aware of is the possibility of configuring the default initial message when we run _git commit_.

By creating a custom template, we can remind our team how they should format their commit messages.

For example we may have a file called _commit-template.txt_ containing the following contents:

```
Commit format:

prefix: feature/fix/hotfix
number: Jira ticket number
Jira ticket title

Example commit message: prefix/number Create a payment list screen to render the customer’s transactions
```

We can configure Git to display the above text whenever the user runs _git commit_. In order to configure this we would run:

```
git config —global commit.template commit-template.txt
```

Another cool feature I never knew Git had available was autocorrect. By setting the configuration of _help.autocorrect_ to the value _30_, Git will run commands we’ve misspelled (but that it can still recognize) 3 seconds after the command was entered.

We can also increase or decrease the waiting duration by changing the value we assign to _help.autocorrect_ (Git will wait 0.1 seconds for each positive integer above 0).

## Server Configuration

We can tell Git to refuse force-pushes on the server with the following command:

```
git config —system receive.denyNonFastForwards true
```

## Git Attributes

### Binary Files

Using Git attributes allows us to customize Git by doing things such as specifying different merge strategies for different files/directories, instructing Git how to diff non-text files, and/or having Git filter content before we check into or out of Git.

If we would like to tell Git to treat a text file (like the .pbxproj file on macOS) as binary data we can do so by adding the following line to our _.gitattributes_ file:

```
.pbxproj binary
```

Of course, we’d replace _.pbxproj_ with the name of whatever file it was we wanted to be treated as binary data.

### Diffing Binary Files

It is possible to diff binary files by specifying the expected file extension (for example .docx) and the name of filter we would like to apply to identify potential diffs:

```
*.docx diff=word
```

Of course, we would also have to define how exactly the “word” filter should work if we were to proceed with the above example.

It’s also possible to set up a filter for “diffing” image files based on their Exif information.

### Exporting Your Repository

We can run _git archive_ to create a tarball of our project. If we have some files or directories we wouldn’t want included in our archive file (for example a test directory "_test/_") we can prevent them from being included using the following command:

```
test/ export-ignore
```

### Merge Strategies

We can use Git attributes to tell Git to use different merge strategies for specific files in our project. For example, if we had a _database.xml_ file that was different in two different branches and we wanted to merge in another branch without any changes happening to our original file we could set up the following attribute:

```
database.xml merge=ours
```

along with a “dummy” _ours_ strategy like so:

```
git config --global merge.ours.driver true
```

## Git Hooks

Git hooks are a way of firing off custom scripts when certain important actions occur.

There are two types of Git hooks:

1. Client-side — Hooks that are triggered by actions such as committing or merging.
1. Server-side — Hooks that run on network operations such as receiving pushed commits.

### Client-Side Hooks

It’s important to note that client-side hooks are **not** copied when we clone a repository.

#### **Committing-Workflow Hooks**

**pre-commit** — This hook is run first before we even have a chance to type a commit message.

It’s used to inspect the snapshot that’s about to be committed to see if we’ve forgotten something, to make sure our unit tests pass, to confirm no linting infractions exist, etc.

**prepare-commit-msg** — This hook is run before the commit message editor launches but after the default message is created. It may be useful to use this hook in conjunction with a commit template to dynamically insert information such as branch names.

**commit-msg** -- This hook can be used to validate that our commit message conforms to a required pattern.

_post-commit_ — This hook is generally used for things like sending notifications.

Some other common client hooks we may want to be aware of include:

- pre-rebase
- post-rewrite
- post-checkout
- post-merge
- pre-push

### Server-Side Hooks

Server-side hooks are scripts that run before and after pushes to the server. Pre-hooks have the ability to reject a push as well as print an error message back to the client.

**pre-receive** — This is the 1st script to run when receiving a push from a client. This hook can help up to make sure none of the updated references are non-fast-forwards.

**update** — This hook is similar to _pre-receive_, but this hook runs once for each branch the pusher is trying to update. This hook is capable of rejecting some references while still accepting others.

**post-receive** — This hook runs after the entire pushing process has been completed. This hook may be used to email a list, update a ticket-tracking system, etc.
