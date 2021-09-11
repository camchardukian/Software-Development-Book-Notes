# Formatting

## The Purpose of Formatting

Code formatting is important because it helps to make your code more readable and thus easier to change in the future.

Essentially the importance of high standards in code formatting is as follows:

> Even when requirements change and your original code needs to be updated or deleted, the formatting patterns you established from the beginning will likely survive.

---

## Vertical Formatting

Small files are usually easier to understand than larger files.

Though not a hard and fast rule, the authors recommends keeping your files under 500 lines (I’ve heard similar recommendations from other experts to try to keep ReactJS components under 300 lines).

---

### The Newspaper Metaphor

The name of your file should be sufficient for the reader to understand if they are in the correct module or not.

The contents of your file should start with high-level concepts and algorithms and then continue onwards to lower and lower level implementation details.

---

### Vertical Openness Between Concepts

Use vertical lines to separate unique concepts such as import statements, individual functions, etc.

---

### Vertical Density

Likewise, lines of code that are closely related should be presented in a compact manner.

---

### Vertical Distance

Here’s a nice quote that summarizes this section well:

> “For those concepts that are so closely related that they belong in the same source file, their vertical separation should be a measure of how important each is to the understandability of the other.”

Here are a few other key concepts from this section:

- Depending on the circumstances, variables should generally either be declared at the top of the file or as close as possible to where they’re being used.
- If one functions calls another, the two functions should be located in close proximity.
- When possible, “caller” functions should be located above the “callee” functions.

---

### Vertical Ordering

By organizing our code with important concepts coming first, we can easily skim source files and only worry about immersing ourselves in low-level details when doing so is actually necessary.

---

## Horizontal Formatting

For best readability, you should generally limit your code to about 80-120 characters per line.

---

### Horizontal Openness and Density

Horizontal white space (or lack thereof) can be used to associate strongly related things and disassociate things that are only weakly related.

---

### Horizontal Alignment

If you have a long list and you think it needs to be neatly horizontally aligned to be read, the problem probably isn’t the horizontal alignment (or lack thereof).

It’s more likely that the problem is your list is too long.

---

### Indentation

Consistent indentation patterns help you to quickly scan code and identify what is and is not relevant to what you’re currently trying to do.

---

### Dummy Scopes

If the body of a _while_ or _for_ statement is a dummy, the loop may be made more readable with proper indentation, and braces.

---

## Team Rules

Developers working in a team together should agree on a single formatting style. Once the style has been agreed upon, each member of the team should use that style.
