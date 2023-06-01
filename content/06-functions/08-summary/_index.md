---
title: "Summary"
pre: "8. "
weight: 80
---

In this lab, we introduced several major important topics in Python. Let's quickly review them.

## Python Functions

A function in Python is a piece of code that is given a name, which can then be run by calling it elsewhere in the program.

To create a function, we use the following structure:

```python
def function_name(parameter1, parameter2):
    <block of statements>
```

1. Function names follow the same rules as variable names.
1. Functions may require 0 or more parameters, placed in parentheses after the function name. Multiple parameters are separated by commas.
1. When called, a function will run the lines of code indented beneath the function definition.

To call a function, we use the following structure:

```tex
function_name(argument1, argument2)
```

1. A function call is the function name, followed by parentheses `()`.
1. Inside of the parentheses, a matching argument must be included for each parameter required by the function. Multiple arguments are separated by commas.
1. Each argument may be an expression that evaluates to a value.
1. The values of each argument are copied into the function. When the function ends, the original arguments are unchanged. 

## Returning Data from Functions

* `return expression` will return the value of `expression` to where the function was called from.
* Function calls can be used in assignment statements to store return values, or as part of other expressions.