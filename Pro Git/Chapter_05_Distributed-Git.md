# Distributed Git

## Distributed Workflows

There are a number of distributed workflows. A popular workflow commonly used on GitHub is the _Integration-Manager Workflow_.

The authors of _Git Pro_ describe the _Integration-Manager Workflow_ as having the following steps:

> 1. The project maintainer pushes to their public repository.
> 1. A contributor clones that repository and makes changes.
> 1. The contributor pushes to their own public copy.
> 1. The contributor sends the maintainer an email asking them to pull changes.
> 1. The maintainer adds the contributor’s repository as a remote and merges locally.
> 1. The maintainer pushes merged changes to the main repository.

While this next workflow isn’t super common, it’s sometimes used on very large projects with hundreds of collaborators. The _Dictator and Lieutenants Workflow_ is described as having the following process:

> 1. Regular developers work on their topic branch and rebase their work on top of master. The master branch is that of the reference repository to which the dictator pushes.
> 1. Lieutenants merge the developers’ topic branches in their master branch.
> 1. The dictator merges the lieutenants’ master branches into the dictator’s master branch.
> 1. Finally, the dictator pushes that master branch to the reference repository so the other developers can rebase on it.

## Contributing to a Project

### Commit Guidelines

We can check for whitespace errors by running the following command:

> git diff --check

As a general rule, the authors of _Pro Git_ recommend our commit messages start with a single line of less than 50 characters that describes the change concisely followed by a more detailed explanation that includes the motivation for the change and how the new behavior differs from the previous one.

## Maintaining a Project

### Working in Topic Branches

Apart from simply creating topic branches for new features, some teams also like to include team members’ initials or other short names for individual contributors so that it can be immediately seen who contributed which branches.

### Determining What Is Introduced

We can put three periods after one branch and then the branch we’re currently on to see the _diff_ between the last commit of the branch we’re on and the common ancestor of the branch we’re comparing it to. For example:

> git diff develop...fix/search-debounce

### Rebasing and Cherry-Picking Workflows

Some project maintainers prefer cherry-picking contributed work on top of their master branch rather than merging topic branches.

This may help them to keep a mostly linear history.

A cherry-pick in Git is basically a rebase for a single commit that takes a patch introduced in a commit and attempts to apply that patch to the branch we’re currently on.

### Rerere

Git has a feature called “rerere” that caches merge resolutions so that fixes can automatically be applied if the same conflict were to occur again in the future.
