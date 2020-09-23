# Git on the Server

There are four different protocols Git can use to transfer data, Local, Secure Shell (SSH), HTTP, and Git.

### Local Protocol

This type of protocol is often used if everyone on the team has access to a shared file system.

The benefit of using a shared file system is that setting up the repository is very easy, and we can quickly grab others work without them needing to push it to a remote server.

One drawbakc of using local protocol, however, is that it can be difficult to set up shared access across multiple locations.

This type of protocol also has an increased likelihood of accidental damage and a corrupted repository due to each user having full shell access to the “remote” directory.

---

### HTTP Protocols

The author states that _Smart HTTP_ is probably the most popular way to use Git nowadays.

On the other hand, the author states that the Git client will fall back on the _Dumb HTTP_ protocol if the server doesn’t respond with a _Git HTTP_ smart service.

The benefit of dumb HTTP is that it’s very easy to setup using Git Hooks (like the _post-update_ hook).

A big benefit of _Smart HTTP_ is that users can authenticate with a username and password instead of having to generate SSH keys locally and upload their public key to the server.

_HTTP_ and _HTTPS_ are also so commonly used that corporate firewalls are often set up to allow traffic through their ports.

The one main drawback of using Git over _HTTPS_ is that it can be a bit more complicated to set up. Apart from that, other protocols have very few advantages over _HTTPS_.

---

### SSH Protocol

Using Git over SSH offers a fairly painless set up, security (encryption and authentication), and efficiency (making data as compact as possible before transferring it).

The big drawback of SSH is that it doesn’t support anonymous access to our Git repository.

If we want someone else to be able to read or write to our repository they will need to have SSH access to our machine, even if just a limited read-only capacity.

---

### The Git Protocol

The Git protocol is usually the fastest network transfer protocol available.

For very large repositories that don’t require authentication for read access, using this protocol makes a lot of sense.

Unfortunately, this type of protocol lacks authentication, can be difficult to setup, and because of its obscurity is often blocked by corporate firewalls.

---

The rest of this chapter offers instructions on a variety of ways for us to set up our own Git server.

If one doesn’t want to set up their own Git server, however, there are also a number of [hosting sites](https://git.wiki.kernel.org/index.php/GitHosting).

While running one’s own server gives a lot of control and allows one to run the server within one’s own firewall, such a server may have a high set up and maintenance cost.

Using a shared hosting site such as GitHub or Bitbucket may be easier to set up and maintain but many organizations do not allow the storage of code outside of their own servers.
