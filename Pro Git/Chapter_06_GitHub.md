# GitHub

A quick time saving tip is to name our SSH keys something we can remember (such as “work account” or “My laptop”) so that if we ever need to revoke a key we can easily choose the correct one.

Pull requests and issues are assigned numbers unique to that project so that they are able to be easily referenced.

Instead of using regular Markdown, GitHub uses what is called _GitHub Flavored Markdown_. This seems to be a superset of Markdown that includes additional features such as task lists, and emojis.

Here’s an example task list using _GitHub Flavored Markdown_:

```
- [X] Wrote the code
- [ ] Wrote all the tests
- [ ] Documented the code
```

It’s possible to make a pull request targeting another pull request. One may do this if they have an idea for a change that depends on another pull request.

GitHub has two common types of special files project maintainers should be aware of:

1. README
1. CONTRIBUTING

While I’ve included _READMEs_ in many of my projects before, I hadn’t heard of the _CONTRIBUTING_ file before reading this chapter. It seems pretty cool!

If your repo has a _CONTRIBUTING_ file, a link to said file will be displayed whenever someone is in the process of creating a pull request. This is extremely useful for specifying to potential contributors things we may want to include or avoid including in a pull request.

If you’re maintaining a project, there are a few administrative things you may want to be aware of:

- It’s possible to change a project’s default branch.
- It’s possible to transfer a project from one user on GitHub to another user or organization.

---

## Managing an organization

Apart from single-user accounts, GitHub also has Organizational accounts. These are basically GitHub accounts where groups of people share ownership over projects and there are various tools to manage these different groups of people.

Accounts for organizations can be free if all of the organization’s code is made open source. Well, at least this used to be the case. As of April 2020, GitHub actually made all of the [core GitHub features free for everyone](https://github.blog/2020-04-14-github-is-now-free-for-teams/).

As an organization you can group your individual contributors into teams. This allows you to easily designate which people in your organization have access to which repos.

GitHub also provides organizations with an audit log that allows you to see what events have happened at an organizational level, where in the world these events occurred, and who was responsible for them.

GitHub repository hooks can be used for different purposes such as sending ourselves an email whenever someone pushes to a specific branch in our project.
