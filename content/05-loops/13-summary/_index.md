---
title: "Summary"
pre: "13. "
weight: 130
---

In this lab, we introduced several major important topics in Python. Let's quickly review them.

## Python While Loops

While loops in Python will execute while a Boolean expression evaluates to `true`.

```python
while <boolean expression>:
    <block of statements>
```

## Range Function

The `range()` function in Python is used to generate a list of numbers. It can be used in three ways:

* `range(stop)` - numbers from $0$ up to (but not including) `stop`
* `range(start, stop)` - numbers from `start` up to (but not including) `stop`
* `range(start, stop, step)` - numbers from `start` up to (but not including) `stop`, with `step` between each number.

## Python For Loops

For loops in Python will execute a set number of times.

```python
for <iterator variable> in <list>:
    <block of statements>
```

## Input with Loops

Loops can be used to request new input from the user if invalid input is received.

```python
x = float(input("Enter a percentage as a decimal number from 0 to 1: "))
while(x < 0 or x > 1):
    print("Invalid Input!")
    x = float(input("Enter a percentage as a decimal number from 0 to 1: "))
```

## Testing Loops

Loops can be tested for both **branch** and **path** coverage. In general, achieving path coverage involves writing code that will enter the loop, and also code that will bypass the loop entirely. 

Loops should also be tested for termination and situations that may result in infinite loops. Using a **loop variant** and showing that it is monotonically decreasing is a helpful technique. 

## Nested Loops

Loops in Python can be nested, just like any other statement. While loops and for loops can be nested in any combination.

## Testing Nested Loops

When testing nested loops, it is important to consider situations where a loop will be executed and where it will be bypassed. It is also important to consider the loop variants for while loops to ensure that there aren't situations where a loop will accidentally run infinitely.

## Efficiency

Nested loops can result in programs that execute many individual steps, even using just a few lines of code. It is always helpful to think about the number of times a loop will execute and make sure that it isn't executing more times than necessary. 