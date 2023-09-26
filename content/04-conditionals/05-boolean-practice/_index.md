---
title: "Boolean Practice"
pre: "5. "
weight: 50
---

Let's try some simple practice problems. These problems are not graded - they are just for you to practice before doing the real exercises in the lab itself. You can find the answers below each question by clicking the button below each question.

#### 4.1 Reading Code

What is printed to the terminal when the following Python program is run?

```python
a = 5
b = 10
c = 15
x = b > a and c < b or (not (a + b > c))
y = b + a >= c or c / a > b / a
z = c - b != a and not c % a == 0
print(x)
print(y)
print(z)
```

Try to work out the solution yourself first before running the code.

{{% expand "Answer" %}}

{{% notice primary "4.1 Answer" "check" %}}

The correct answer is:

```tex
True
True
False
```

{{% /notice %}}

{{% /expand %}}

#### 4.2 Reading Code

What is printed to the terminal when the following Python program is run?

```python
x = 7
y = 42
z = 6
a = x >= z and y <= x * z or not y % z == 0
b = not (y // x <= z or x - z > 0 or y % x != 1)
c = y // (z + x) < z / 2 and not bool(z)
print(a)
print(b)
print(c)
```

Try to work out the solution yourself first before running the code.


{{% expand "Answer" %}}

{{% notice primary "4.2 Answer" "check" %}}

The correct answer is:

```tex
True
False
False
```

{{% /notice %}}

{{% /expand %}}

#### 4.3 Writing Code

Write a Python program that performs the following operations:

1. Prompts the user for four integer inputs and stores them in variables
1. If the first input is strictly smaller than all other inputs, and the last input is strictly larger than all other inputs, print `True`. If not, print `False`.

Your program **may not** use any conditional statements (if statements).

_Hint: what comparisons must be made, and what comparisons do not need to be made, to answer these questions definitively?_

{{% expand "Answer" %}}

{{% notice primary "4.3 Answer" "check" %}}

One possible answer is given below:

```python
a = int(input("Enter an integer: "))
b = int(input("Enter an integer: "))
c = int(input("Enter an integer: "))
d = int(input("Enter an integer: "))
x = a < b and a < c and a < d and b < d and c < d
print(x)
```

Notice that `a` is compared with the other three variables directly, as is `d`. The comparison between `a` and `d` is only included once. 

{{% /notice %}}

{{% /expand %}}

#### 4.4 Writing Code

Write a complete program in Python that performs the following operations:

1. Prompts the user for three integer inputs and stores them in variables.
1. If the second and third inputs are multiples of the first, and the third input is a multiple of the second, print `true`. If not, print `false`.

Your program **may not** use any conditional statements (if statements). 

_Hint: you can use the modulo `%` operator to determine if one number is evenly divisible by another number. Can this also tell you which number is a multiple of another number?_

{{% expand "Answer" %}}

{{% notice primary "4.4 Answer" "check" %}}

One possible solution is given below:

```python
x = int(input("Enter an integer: "))
y = int(input("Enter an integer: "))
z = int(input("Enter an integer: "))
a = y % x == 0 and z % y == 0
print(a)
```

Notice that it only checks if `y % x` and `z % y` are equal to 0. If those are both true, then `z % x` is implied to be true.

{{% /notice %}}

{{% /expand %}}