# Operators

The SIMPLE language avoids using symbols for operators, instead generally preferring a more verbose, but easier to read, approach.

The exceptions to this are the simple arithmetic operators `+`, `-`, `*`, `/` (add, subtract, multiply, divide respectively).

The modulo/remainder operator (usually represented by `%` in other languages) is represented by the operator `Modulo`.

The equality operator (usually `==`) is replaced with `Equals` between the two arguments.

The inequality operator (`!=`) is replaced with `NotEquals` in the same place as `Equals` can be placed.

Arithmetic operators are not implemented for any types save `Integer` and `Real`.

>[!CAUTION]
> At a later time, this may be extended to `Character`. Ideally, this would require specific syntax so that the user is aware of the under-the-hood implementation of Character. The intended behaviour of this would be similar to adding an `int` to a `char` in C, then casting back as a `char` automatially.

Combining two `List<T>` together can be achieved using the `Append` operator; i.e. given `List<Integer>` `a` [1, 2, 3] and `List<Integer>` `b` [4, 5, 6], `a Append b` would be [1, 2, 3, 4, 5, 6]. Note that this does not apply a sort; the sorted nature of the numbers in this example is purely coincidental.
