---
title: "Loops Practice"
pre: "7. "
weight: 70
---

Let's try some simple practice problems. These problems are not graded - they are just for you to practice before doing the real exercises in the lab itself. You can find the answers below each question by clicking the button below each question.

#### 5.1 Reading Code

Consider the following pseudocode program:

```python
x = int(input("Enter a positive integer: "))
while(x <= 0):
    print("Invalid Input!")
    x = int(input("Enter a positive integer: "))
a = 1
for i in range(9):
    if x % a == 0:
        print(f"{a}")
    a = a + 1
```

Explain, in your own words, the output that this program produces in relation to the input provided. 

A fully correct answer is a succinct description of the output as it relates to the input. A partially correct answer is a step-by-step description of each line in the program and the output it will produce based on the input.

{{% expand "Answer" %}}

{{% notice primary "5.1 Answer" "check" %}}

This program receives a positive number as input, and then will check to see if that number is evenly divisible by the numbers {{< math >}}$ 1 ${{< /math >}} through {{< math >}}$ 9 ${{< /math >}}. If so, it will print that number.

For example, if the input provided is {{< math >}}$ 60 ${{< /math >}}, then the output should be:

```tex
1
2
3
4
5
6
```

since {{< math >}}$ 60 ${{< /math >}} is divisible by the first {{< math >}}$ 6 ${{< /math >}} integers. 

{{% /notice %}}

{{% /expand %}}

#### 5.2 Testing Code

Consider the program above. Devise a set of inputs that will cause each of the 9 possible numerical outputs to print at least once, and for each input, list the numbers that will be printed as output.

{{% expand "Answer" %}}

{{% notice primary "5.2 Answer" "check" %}}

There are many ways to answer this. A quick and easy way is to simply provide the numbers {{< math >}}$ 1 ${{< /math >}} through {{< math >}}$ 9 ${{< /math >}} as inputs. In the previous answer, we already know that {{< math >}}$ 60 ${{< /math >}} covers six of the nine possible outputs, so two or three additional inputs can cover the rest.

Mathematically, the number {{< math >}}$ 2520 ${{< /math >}} is the lowest common multiple of the first ten integers, so that single value as input will produce all nine possible outputs.

{{% /notice %}}

{{% /expand %}}

#### 5.3 Reading Code

Consider the following Python program:

```python
x = int(input("Enter a positive integer: "))
while(x <= 0):
    print("Invalid Input!")
    x = int(input("Enter a positive integer: "))
a = ""
while x > 0:
    if x % 2 == 0:
        a = "0" + a
    else:
        a = "1" + a
    x = x // 2
print(a)
```

Explain, in your own words, the output that this program produces in relation to the input provided.

A fully correct answer is a succinct description of the output as it relates to the input. A partially correct answer is a step-by-step description of each line in the program and the output it will produce based on the input.

_Hint: when numbers are stored digitally on a computer, what numerical format is used?_

{{% expand "Answer" %}}

{{% notice primary "5.3 Answer" "check" %}}

Simply put, this program will convert any positive integer into its binary representation. For example, the input {{< math >}}$ 42 ${{< /math >}} will generate the output `101010`, which is in binary is the value {{< math >}}$ 42 ${{< /math >}}.

{{% /notice %}}

{{% /expand %}}

#### 5.4 Testing Code

Consider the Python program above. Devise a set of inputs that you feel are sufficient to test the program, and briefly explain why those inputs are sufficient.

_Hint: Achieving coverage is very simple, but providing enough input to be confident that the program is generating the correct output should also be considered._

{{% expand "Answer" %}}

{{% notice primary "5.4 Answer" "check" %}}

To achieve full coverage, a sufficient set of inputs would be something similar to:

* 0
* 1
* 2

That should be enough to exercise all possible code branches and paths. However, in order to truly determine if the program is producing the correct output, it would be useful to choose a couple of larger inputs. Some good choices would be numbers near a power of {{< math >}}$ 2 ${{< /math >}}, such as:

* 15
* 16

Many other answers are possible here.

{{% /notice %}}

{{% /expand %}}

#### 5.5 Writing Code

Write a complete Python program that meets the specification below.

The [Fibonacci Sequence](https://en.wikipedia.org/wiki/Fibonacci_number) is a sequence of numbers where the next number is the sum of the previous two numbers. The sequence starts with the numbers {{< math >}}$ 1 ${{< /math >}} and {{< math >}}$ 1 ${{< /math >}}, making the next number {{< math >}}$ 2 ${{< /math >}}. The following number is {{< math >}}$ 3 ${{< /math >}}, since it is the sum of the second and third number of the sequence. The sequence continues indefinitely.

For this program, ask the user to input a number that must be greater than {{< math >}}$ 5 ${{< /math >}}. If the user inputs a number that is {{< math >}}$ 5 ${{< /math >}} or less, display an error and prompt the user for another input until a valid input is received.

Then, determine if the number provided as input is part of the Fibonacci Sequence. This can be done by computing the sequence one number at a time until the desired number is reached or passed. Print either `"In sequence"` or `"Not in sequence"` depending on the result found.

{{% expand "Answer" %}}

{{% notice primary "5.5 Answer" "check" %}}

One possible solution is given below:

```python
x = int(input("Enter a positive integer greater than 5: "))
while(x <= 5):
    print("Invalid Input!")
    x = int(input("Enter a positive integer greater than 5: "))
a = 1
b = 1
while b < x:
    c = a + b
    a = b
    b = c
if b == x:
    print("In sequence")
else:
    print("Not in sequence")
```

There are many other valid approaches as well.

{{% /notice %}}

{{% /expand %}}

#### 5.6 Writing Code

Write a complete Python program that meets the specification below.

Write a program that will print the first {{< math >}}$ 30 ${{< /math >}} multiples of a given number, but only multiples where the last digit is equal to a second given number. 

For this program, ask the user to provide two integers - the first between {{< math >}}$ 1 ${{< /math >}} and {{< math >}}$ 100 ${{< /math >}}, inclusive, and the second between {{< math >}}$ 0 ${{< /math >}} and {{< math >}}$ 9 ${{< /math >}}, inclusive. If the user provides an invalid value for either input, print an error message and prompt the user for another input until a valid input is received.

Then, the program should compute the first {{< math >}}$ 30 ${{< /math >}} multiples of the first given number. This would be equivalent to multiplying the number by {{< math >}}$ 1 ${{< /math >}} all the way through multiplying the number by {{< math >}}$ 30 ${{< /math >}}. Then, if that computed multiple ends with the same digit as the second number, it should be printed. Otherwise, no output is produced for that number.

For example, if the first given number is {{< math >}}$ 9 ${{< /math >}} and the second number is {{< math >}}$ 1 ${{< /math >}}, then the output should be:

```tex
81
171
261
```

Your program should make use of a for loop and the Python `range()` function.

_Hint: what is the value of `81 % 10`? What about `27 % 10`? Does that value help you determine whether the number should be printed or not?_

{{% expand "Answer" %}}

{{% notice primary "5.5 Answer" "check" %}}

One possible solution is given below:

```python
x = int(input("Enter an integer between 1 and 100: "))
while(x < 1 or x > 100):
    print("Invalid Input!")
    x = int(input("Enter an integer between 1 and 100: "))
first = x
x = int(input("Enter an integer between 0 and 9: "))
while(x < 0 or x > 9):
    print("Invalid Input!")
    x = int(input("Enter an integer between 0 and 9: "))
second = x
for i in range(first, first * 30 + 1, first):
    if i % 10 == second:
        print(i)
```

This solution uses the `range()` function directly to compute the multiples. It is also possible to use `range()` to generate a list of numbers from {{< math >}}$ 1 ${{< /math >}} to {{< math >}}$ 30 ${{< /math >}} and compute the multiples using those values.

{{% /notice %}}

{{% /expand %}}