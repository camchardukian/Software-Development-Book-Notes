# Git and Other Systems

**Note from Cam: This chapter seems like more one you’d reference as needed rather than one you’d try acquire knowledge from by reading it cover to cover.**

**As such, in this chapter I focused my attention just on the main concepts, and skimmed over the parts discussing obscure scenarios I’m pretty unlikely to encounter in the next couple years.**

## Git as a Client

Because Git offers such a developer friendly experience, a number of adapters called “bridges” have been created to help developers use Git even if the rest of their team is using a different VCS.

### Git and Subversion

Git has a bidirectional bridge to Subversion called _git svn_. This tool allows developers to use all of the local features of Git locally, but still push to a Subversion server as if the developer was using Subversion locally.

In general, the authors of _Pro Git_ recommend using _git svn_ if we’re stuck with a Subversion server or are otherwise in a development environment that requires running a Subversion server.

If possible, however, the authors recommend using Git over Subversion to help our team enjoy a more productive developer experience.

---

This chapter also discusses using Git with a number of other version control systems such as Mercurial, Perforce, Bazaar, etc.

One important suggestion the authors made in this chapter is that if our team is using multiple version control systems, only one system should be the center of collaboration.

---

## Migrating To Git

There are some established way of migrating to Git from other common version control systems such as Mercurial or Bazaar.

If we’re using some obscure version control system, however, it’s also possible to migrate to Git by creating a custom import process with the _git fast-import_ command.
