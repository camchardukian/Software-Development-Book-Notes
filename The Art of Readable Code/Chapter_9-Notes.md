# Chapter 9 Variables and Readability

This chapter basically talks about how the sloppy use of variables makes our application’s code more difficult to understand.

— If a variable is not used multiple times, does not add clarification, nor does it break down a complex expression… that variable probably isn’t worth keeping.

— Whenever possible, “shrink the scope” of your variables. Apart from polluting the global, file, function, etc. "namespace", shrinking the scope of our variables would also reduce the number of variables the reader of our code would have to think about at any given time.

— Declaring variables immediately before they are used for the first time often makes our code more readable than if we were to declare all of our variables at the top of our function.

-- The authors made a great point in this chapter that the more places a variable is manipulated in, the harder it is to reason about the variable’s current value.

— To summarize, this chapter made the following suggestions… We should eliminate unnecessary variables, reduce the scope of our variables whenever possible, and prefer write-once variables (such as *const* in JavaScript) over variables that may change in many places (like *let* in JavaScript).