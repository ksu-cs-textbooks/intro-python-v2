---
title: "Nesting Practice"
pre: "12. "
weight: 120
---

Let's try some simple practice problems. These problems are not graded - they are just for you to practice before doing the real exercises in the lab itself. You can find the answers below each question by clicking the button below each question.

#### 5.7 Reading Code

Consider the following Python program:

```python
x = int(input("Enter a positive integer: "))
while x <= 0:
    print("Invalid input!")
    x = int(input("Enter a positive integer: "))
n = x
for i in range(n - 1):
    for j in range(n - i - 1):
        print(" ", end="")
    for j in range(i + 1):
        print("* ", end="")
    print("")
for i in range(n):
    for j in range(n):
        print("* ", end="")
    print("")
```

Describe the shape that will be printed when this program is executed. Try to do so without running the code directly, but feel free to check your answer after guessing. 

{{% expand "Answer" %}}

{{% notice primary "5.7 Answer" "check" %}}

This program will print a "house" shape, which is a square with a triangle on top. For example, if the user inputs {{< math >}}$ 5 ${{< /math >}}, the output will be:

```tex
    * 
   * * 
  * * * 
 * * * * 
* * * * * 
* * * * * 
* * * * * 
* * * * * 
* * * * * 
```

{{% /notice %}}

{{% /expand %}}

#### 5.8 Debugging Code

Consider the following Python program:

```python
x = 3
y = 5
while x => 0:
    for i in range(y):
        print("* ")
    print("")
    x = x + 1
```

This code is supposed to print a rectangle of asterisks that is `x` rows tall and `y` columns wide. However, it contains multiple syntax and logic errors preventing it from working correctly. Describe how to fix the errors in the given code to produce the desired output.

{{% expand "Answer" %}}

{{% notice primary "5.8 Answer" "check" %}}

There are several errors:
* The while loop uses `=>` as a Boolean operator instead of `>`
* The `print()` statement in the inner for loop should include the optional parameter `end=""` to print all the asterisks on 1 line
* The line incrementing `x` should be decrementing `x` instead: `x = x - 1`

After making those changes, the code should be similar to:

```python
x = 3
y = 5
while x > 0:
    for i in range(y):
        print("* ", end="")
    print("")
    x = x - 1
```

Other valid answers include changing the outer while loop into a for loop. 

{{% /notice %}}

{{% /expand %}}

#### 5.9 Writing Code

Write a complete Python program in that file that meets the specification below.

Write a program that will print a [Parallelogram](https://en.wikipedia.org/wiki/Parallelogram) of asterisks that is `m` rows tall and `n` columns wide, where the topmost row is furthest toward the left. The values `m` and `n` should be provided by the user as input. If the user inputs a value that is {{< math >}}$ 0 ${{< /math >}} or negative, the program should print an error and prompt for input again.

For example, if the user inputs {{< math >}}$ 3 ${{< /math >}} and {{< math >}}$ 5 ${{< /math >}}, the program should provide the following output:

```tex
* * * * *
 * * * * * 
  * * * * * 
```

Notice that each asterisk is separated by a space, and each successive row of the parallelogram begins one space to the right of the previous row.

{{% expand "Answer" %}}

{{% notice primary "5.9 Answer" "check" %}}

One possible solution is given below:

```python
x = int(input("Enter a positive integer for m: "))
while x <= 0:
    print("Invalid input!")
    x = int(input("Enter a positive integer for m: "))
m = x

x = int(input("Enter a positive integer for n: "))
while x <= 0:
    print("Invalid input!")
    x = int(input("Enter a positive integer for n: "))
n = x

for i in range(m):
    for j in range(i):
        print(" ", end="")
    for j in range(n):
        print("* ", end="")
    print("")
```

{{% /notice %}}

{{% /expand %}}