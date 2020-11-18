# Chapter 1 — Values, Types, and Operators

Bits are any kind of two-value things, usually described as zeros and ones.

## Values

A chunk of bits that are gathered together and that represent pieces of information can be referred to as values (at least they’d be referred to in this way in a JavaScript environment).

## Numbers

JavaScript uses a fixed number of bits (64 to be exact) to store a single number value. JavaScript is able to accurately work with whole numbers up to about 9 quadrillion.

Unfortunately, JavaScript is much less accurate at dealing with fractions. As a result, we should treat fractional digital numbers as approximations rather than as precise values.

## Arithmetic

When operators appear together without parentheses, the order in which they are executed is determined based on the precedence of the operators.

When multiple operators with the same precedence appear next to each other they are applied from left to write.

The ‘%’ operator is often referred to as the _modulo_ operator.

## Special Numbers

There are three values in JavaScript that are considered numbers, but that don’t behave like normal numbers. These three values are _Infinity_, _-Infinity_, and _NaN_.

Despite _NaN_ standing for “not a number”, _NaN_ is actually of the type number.

## Strings

We can include special characters inside of a string by using a backlack (\). For example a backslack following by an n like so:

> \n

would result in a line break being applied.

JavaScript models strings into series of bits using the _Unicode_ standard.

## Unary Operators

The _typeof_ operator is an example of a unary operator. Operators that take only one values are commonly called unary operators while those that take two values are called binary operators.

## Boolean Values

If strings are compared using the _<_ and _>_ operators, JavaScript will return a boolean value based on the Unicode values of the two strings.

The only value in JavaScript that is not equal to itself is _NaN_.

## Logical Operators

The _conditional_ operator is often referred to as THE _ternary_ operator because it is the only operator that operates on 3 values in JavaScript.

## Automatic Type Conversion

JavaScript’s process of quietly converting values from one type to another when operators are applied to the “wrong” value type is referred to as _type coercion_.

When JavaScript tries to coerce a value that doesn’t map to a number in an obvious way we get the value _NaN_.

Using the triple equals operator instead of the double equals operator can help prevent unexpected or undesired type coercions from occurring.

## Short-Circuiting of Logical Operators

The logical operators _&&_ and | | will return either the value on their left or right side depending on whether the left hand value is true or false. _Short-circuit evaluation_ refers to when we use either of these operators in such a way that the right side of the value is never evaluated.
