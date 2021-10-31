# Chapter 4 —- Comments

## Comments Do Not Make Up for Bad Code

If you know your code is a mess, it’s better to clean up the mess you’ve made than to write comments explaining the mess.

---

## Good Comments

There are many types of comments that can be beneficial.

Even better than leaving helpful comments, however, is finding a responsible way to avoid having to leave comments Unfortunately, that's not always possible.

As such, the authors cite 8 types of comments that can sometimes be useful and I’ve also included an additional piece of advice for each type:

1. Legal Comments

- If possible, refer to a standard license rather than directly placing terms and conditions into your file.

---

2. Informative Comments

- Comments can provide additional info, but often it’s better to rename your function or move blocks of code around for easier understanding.

---

3. Explanations of Intent

- These comments can help others understand why you did something in a certain way, which could help them to avoid modifying the code in harmful ways.

---

4. Clarification

- Be extremely cautious that your clarifications for difficult to understand code are correct because others are likely to take your comments at face value.

---

5. Warning of Consequences

- While there are sometimes better solutions, it’s perfectly reasonable to leave comments warning about potential problems resulting from the code.

---

6. TODO Comments

- A TODO comment is not an excuse to leave bad code in the system.

---

7. Amplifications

- Comments can be used to amplify the importance of something that could be easy to overlook.

---

8. Javadocs in Public APIs

- Public APIs typically need more detailed comments than APIs used only within your team.

## Bad Comments

Unsurprisingly, there are many more bad types of comments than there are good ones.

---

### Mumbling

If a comment was written in a hurry and fails to convey meaning to the reader, it’s a wasted comment.

---

### Redundant Comments

A comment that takes more time or is more difficult to read than the code itself is pointless.

---

### Misleading Comments

Comments that aren’t precise enough or that are just plain wrong can lead others astray.

---

### Mandated Comments

It’s easy for mandated comments to simply add clutter and be forgotten to be updated when users update other parts of the code.

---

### Journal Comments

Now that we have source control systems like GIT, these kind of comments are unnecessary.

---

### Noise Comments

Noise comments are those that restate the obvious. They provide little to no value in the best of cases, and often provide negative value later on as they become outdated.

---

### Scary Noise

When mandated comments, or noise comments are repeatedly copy and pasted there can easily be an accidental paste in the wrong spot that results in a misleading comment.

---

**Now that we’ve talked about the different bad types of comments here are some of the best tips from this chapter you can use to write better comments.**

---

### Position Markers

The more often you leave comments to mark your position in the code, the less attention others will pay these comments while navigating. Use position marker comments sparingly.

---

### Closing Brace Comments

Leaving comments to indicate the closing braces of long functions with deeply nested structures offers some value. Way more value is provided, however, by instead writing code that avoids these monolith functions via the usage of a larger number of short and readable functions.

---

### Attributions and Bylines

You don’t need comments to indicate who created or last edited something. Source control systems will do that for you.

---

### Nonlocal Information

Comments should describe the code they appear near. Comments that discuss systemwide information are both redundant and likely to become outdated.

---

### Inobvious Connection

If your comment needs an additional explanation in order for the reader to understand it, you’ve failed at creating a helpful comment.
