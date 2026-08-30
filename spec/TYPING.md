# Typing

SIMPLE is a statically typed language. While some believe that dynamic typing is easier for programming novices, I believe that it can lead to the learner not being able to properly figure out what they can and cannot do with a value.

However, some automatic casting is permitted, typically for strict supersets of values.

In the most basic SIMPLE implementation, the only permitted casts are `Integer` to `Real` (i.e. 7 -> 7.0 or -18 -> -18.0), and `Character` to `Text` (i.e. the character `'c'` -> `"c"` as a one-character-long string). It is also permitted to cast a type `T` to be a one-item long `List<T>`.

## Integer

A 64-bit signed integer, or `long` in many other languages.

## Real

A double-precision floating point number (by the IEEE-754 standard, or `double` in most programming languages).

## Character

A UTF-8 character.

## Text

A dynamic array of UTF-8 characters. The under-the-hood implementation may vary for different SIMPLE implementations, but, as exposed to the user (e.g. for indexing into a `Text`), the characters in `Hello` are to be exposed as `H`, `e`, `l`, `l`, `o`, with no null-terminator or similar.

`Text` is a superset of `List<Character>`.

## Boolean

True or False.

## `List<T>`

`List<T>` is a dynamic array of any type `T`, which can of course include `List<T>` itself. As for `Text`, any implementation-specific terminator is not to be exposed to the user when, say, iterating through a `List`.

## Nothing

Nothing is broadly equivalent to the `void` type in C. It is generally intended for the return value of a function that does not return a meaningful value, though a variable can be declared as Nothing.

A variable declared as Nothing cannot be declared with a value (save the output of a function returning Nothing), and the only operator defined on Nothing is that it `Equals` all other variables that are Nothing. There is no type coercion to or from Nothing; it is not intended for any meaningful use.
