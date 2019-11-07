Chapter 5 — Knowing What to Comment

The key idea Boswell & Foucher open this chapter with is that:
> The purpose of commenting is to help the reader know as much as the writer did.

With that being said, Boswell & Foucher caution against putting too many comments into our code as comments both take up screen space and take time away from reading the actual code.

In other words, we should strive to AVOID commenting on facts or ideas that are immediately (or almost immediately) gleaned simply from reading the code itself.

Another idea presented in this chapter is that our comments shouldn’t try to make up for poorly written code. If a variable name is unclear, rather than writing a comment, it’s usually better simply to give said variable a name that better indicates its purpose.

A common rule amongst coders (according to the authors) is that:
> good code > bad code + good comments

Here are some circumstances in which commenting WOULD be beneficial, however…

1. Giving valuable insights about the code (such as ideas for future optimizations, or informing the reader about things they may be surprised about).

1. Identifying problems or placing “markers” such as *TODO*, *FIXME*, *HACK*, or *DANGER*.

1. Explaining what a constant does, or why you gave said constant a certain value (this helps other developers effectively use your constants to avoid duplicating code unnecessarily, and could also prevent them from changing values that are already optimized).

A good general comment making policy is to anticipate whether someone else reading your code would have any questions or whether there is anything that could potentially surprise them about the code you’ve written.

Another thought experiment what will drive you towards documenting your code in an effective manner is to imagine your giving a tour of your code base to a new team member.

The types of things that you would casually explain to your new team member as you gave a tour of the codebase are a good indicator of the type of information that would be useful to leave as high-level comments.