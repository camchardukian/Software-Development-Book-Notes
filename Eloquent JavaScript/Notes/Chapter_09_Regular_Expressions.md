# Chapter 9 -- Regular Expressions

## Creating a Regular Expression

A regular expression is a type of object. Regular expressions can be created using the _RegExp_ constructor or by nesting a pattern between slashes.

## Testing For Matches

We can pass the _test_ method a string and it will return a Boolean telling whether our string contains a match of the RegExp or not.

## Sets of Characters

We can use square brackets to indicate a match if any of the characters in the brackets are included in our string being evaluated.

We can use a caret character (^) nested inside of square brackets to indicate a match if there are any characters in the string being evaluated aside from the characters following the caret. For example:

```
Const nonBinary = /[^01]/;
```

## Repeating Parts of a Pattern

Here are how some special characters work in forming RegExps.

(+) -- We put this after another character to indicate said character may be repeated multiple times.
(\*) -- Almost the same as (+), but this also allows the previous character to be matched zero times.
(?) -- Makes part of a pattern optional.
{} -- We can put a number inside, for example {5} to indicate some element should occur exactly five times. We can also provide a range {3, 5} to indicate something should occur 3-5 times, or use a comma to indicate it should occur 5 or more times {5,}.

## Grouping Subexpressions

If we want an operator to be applied on multiple elements/characters at once we need to nest them with parentheses.

## Matches and Groups

Although the _test_ method is the most popular for matching regular expressions, the _exec_, and _match_ methods also have various use cases. Using the _exec_ method along with its _index_ property, we can see where in a given string a match occurred.

## The Date Class

In JavaScript’s date system, months start at 0, and days start at 1.

## Word and String Boundaries

We can set boundaries or indicate that a string must start with a group of characters by using the caret (^) operator or that a string must end with a specific group of characters by using the (\$) operator.

## Choice Patterns

We can use the pipe character (|) to indicate that the element being evaluated matches at least one of multiple options.

## The Mechanics of Matching

The _exec_ and _test_ methods will return either the first match that can be found or they will fail to return any match at all.

## Backtracking

Backtracking often occurs when we use the pipe character (|) or repetition operators such as (+) or (\*)

## The Replace Method

We can combine the usage of regular expressions with the _replace_ method found on string values.

It’s also possible to pass a function instead of a string as the 2nd argument in the _replace_ method.

## Greed

The repetition operators (+, \*, ?, and {}) are "greedy" by default. We can make these operators "lazy" by following them immediately with a question mark.

## Dynamically Creating RegExp Objects

It’s possible to dynamically create regular expressions from data that’s only available once our application is already running.

## The Search Method

We cannot directly use the _indexOf_ method with regular expressions. The _search_ method on the other hand works similarly to the _indexOf_ method and does expect to be used with a regular expression.

## The LastIndex Property

The _LastIndex_ property is an integer that under some circumstances represents where the next match will start.

## Parsing an INI File

The split method is able to accept a regular expression as its argument.

## International Characters

JavaScript’s regular expressions do not work particularly well with characters that do not appear in the English language. They also may behave strangely with code units such as emojis.

Some of these issues can be mitigated by adding a _u_ (Unicode) option.
