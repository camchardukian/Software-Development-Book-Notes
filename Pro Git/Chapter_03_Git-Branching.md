# Chapter 3 — Git Branching

Here’s a pretty nice quote from the first page of this chapter before we get into the meat of Git branches:

> “The way Git branches is incredibly lightweight, making branching operations nearly instantaneous, and switching back and forth between branches generally just as fast. Unlike many other VCSs, Git encourages workflows that branch and merge often, even multiple times in a day. ”

While I’m used to creating branches and immediately switching into them using _git checkout -b branchNameHere_, it seems it’s also possible to create a new branch without checking out to it using the following syntax:

```
git branch nameOfBranchWeWantToCreate
```

Git is able to track or remember which local branch we are on by using a special pointer called _HEAD_. We can see where all of our branch pointers are pointing using the _—decorate_ option.

For example, we could write:

```
git log —online —decorate
```

When our commit history has diverged, we can print a visual representation of where our branch pointers are and how our history has diverged with the following command:

```
git log —online —decorate —graph —all
```

---

Beyond simply using _git branch_ to see all of our branches, we can also see the last commit we’ve made on each branch using the following command:

```
git branch -v
```

To see which branches we’ve already merged into the branch we’re currently on we can use the _git branch –merged_ command.

```
git branch --merged
```

Likewise, it’s also possible to see branches we haven’t yet merged in:

```
git branch --no-merged
```

It’s possible to rename a remote branch, though we should generally be cautious when doing this if we’re working with other collaborators. Here are the steps:

```
git branch –move bad-branch-name corrected-branch-name
git push –set-upstream origin corrected-branch-name
git push origin –delete bad-branch-name
```

We should be especially careful when renaming the master branch as there are many things we would need to attend to in such a transition.
We can get a full list of remote references (branches, tags, etc) with the following command:

```
git remote show <remote>
```

It should be noted that a project may in some cases have multiple remote servers. Such a setup may be used if a project has multiple teams for example. If we found ourselves in this situation, instead of simply using _git fetch_ we may instead choose to get our code only from team one like so:

```
git fetch teamone
```

According to the authors of _Pro Git_ the golden rule of rebasing is:

> “Do not rebase commits that exist outside your repository and that people may have based work on.”

Rebasing and merging have different use cases. Beyond even that, some teams feel a commit history should be a **record of what actually happened** while other teams believe a commit history should tell the **story of how the project was created**.
Teams that align with the second philosophy are significantly more likely to use tools like _rebase_ and _filter-branch_.
