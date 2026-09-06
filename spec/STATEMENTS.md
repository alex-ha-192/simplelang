# Statements

## Basic statements

Basic statements in SIMPLE must be on one line, and are not terminated with any character (or could be said to be terminated with a newline character).

For instance, the following code snippet instantiates the integer `my_integer` with value 5, adds 5 to it, then prints it to the terminal where the code is being run:

```
Create Integer my_integer with value 5
Set my_integer to my_integer + 5
Display my_integer
```

This code, when run, will print the following to the terminal:

`my_integer = 10`

## Variable declaration

All variables not explicitly declared otherwise are mutable.

The following code snippet instantiates an integer variable `my_integer` with value 6:

`Create Integer my_integer with value 6`

By default, integers declared without a value must by default be assigned the value 0.

## Conditional statements

Conditional statements have the following structure:

```
If foo Equals 7 then {
    Display "foo equals 7"
} otherwise {
    Display "foo does not equal 7"
}
```

Curly braces are required around block statements in conditionals. The style above is recommended but not required.

## Iteration

SIMPLE only supports `while` statements.

The following code snippet iterates a counter from 0 to 10, then prints the final value.

```
Create Integer counter with value 0
While (counter Equals 10) is False {
    Set counter to counter + 1
}
Display counter
Display "counter should be equal to 10"
```

The `is True/False` section of the while statement is optional; by default, assume `is True` if this section is absent.

## List access

Accesses to out of bounds in a list is undefined behaviour.

A list with contents `[0, 1, 2, 3]` is zero-indexed and can be accessed as follows:

```
Create List<Integer> my_list with value [0, 1, 2, 3]
Display my_list[0]
Display "my_list[0] should be 0"
```

## Function execution

To execute a function without using its return value, the following syntax can be used:

```
Function print_one takes (Integer x) returns Integer {
    Display 1
    Return 0
}

Create Integer foo with value 7

Run print_one(foo)
```

`Run` throws away the return value of the function, while still making all the other expected changes to program state by otherwise running the function and storing the return value.

## Statements and variables

Variables can be created in any scope, and will not be available in any scope not descended from that scope (save in subroutines when not passed as an argument).

Variables declared in an ancestor scope can be edited in a descendant scope emerging from an `If` or `While` statement in such a way that the ancestor scope will be affected.
