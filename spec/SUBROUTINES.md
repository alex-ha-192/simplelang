# Subroutines

Like C/C++, all SIMPLE subroutines must return some type.

This function signature is for a function `AddTwoNumbers` that takes integer `a` by value, integer `b` by reference, and returns some integer:

`function AddTwoNumbers takes (Copyof Integer a, Integer b) returns Integer`

This function signature for the function `Foo` takes some string `user_input` by value as an argument and returns a null, or void:

`function Foo takes (Copyof Text user_input) returns Nothing`