---
title: "Conditionals Practice"
pre: "9. "
weight: 90
---

Let's try some simple practice problems. These problems are not graded - they are just for you to practice before doing the real exercises in the lab itself. You can find the answers below each question by clicking the button below each question.

#### 4.5 Reading Code

Consider the following Python program:

```python
a = int(input("Enter a whole number: "))
b = int(input("Enter a whole number: "))
if (a + b) % 3 == 0:
    print("Branch 1")
else:
    print("Branch 2")
a = a * 2
b = b * 3
if (a + b) % 3 == 0:
    print("Branch 3")
else:
    print("Branch 4")

```

What output is printed when the user inputs the values {{< math >}}$ 2 ${{< /math >}} and {{< math >}}$ 4 ${{< /math >}}?

{{% expand "Answer" %}}

{{% notice primary "4.5 Answer" "check" %}}

This program will produce the following output:

```tex
Branch 1
Branch 4
```

This is because {{< math >}}$ 2 + 4 \text{ % } 3 == 0 ${{< /math >}} is `True`, but {{< math >}}$ 4 + 12 \text{ % } 3 == 0 ${{< /math >}} is `False`.

{{% /notice %}}

{{% /expand %}}

#### 4.6 Testing Code

Consider the program in the previous question. Write a set of possible inputs to the program that will achieve **path coverage**. For each set of inputs, identify which branches will be executed when that input is provided to the program.

_Think carefully! The same if statement is executed twice with different values, but those values are related to each other._

{{% expand "Answer" %}}

{{% notice primary "4.6 Answer" "check" %}}

To achieve path coverage, the following inputs can be used:

```tex
3 and 3 - Branch 1 & 3
2 and 4 - Branch 1 & 4
3 and 2 - Branch 2 & 3
2 and 2 - Branch 2 & 4
```

There are many other possible answers to this question!

{{% /notice %}}

{{% /expand %}}

#### 4.7 Reading Code

Consider the following Python program:

```python
x = int(input("Enter an integer: "))
y = int(input("Enter an integer: "))
if x * 5 > y:
  print("Branch 1")
else:
  print("Branch 2")
if y % 5 == x:
  print("Branch 3")
else:
  print("Branch 4")
```

What output is displayed when the user inputs the values {{< math >}}$ 4 ${{< /math >}} and {{< math >}}$ 29 ${{< /math >}}?

{{% expand "Answer" %}}

{{% notice primary "4.7 Answer" "check" %}}

The program will produce this output:

```tex
Branch 2
Branch 3
```

This is because {{< math >}}$ 4 * 5 > 29 ${{< /math >}} is `False`, but {{< math >}}$ 29 % 5 = 4 ${{< /math >}} is `True`.

{{% /notice %}}

{{% /expand %}}

#### 4.8 Testing Code

Consider the program in the previous question. Write a set of possible inputs to the program that will achieve **path coverage**. For each set of inputs, identify which branches will be executed when that input is provided to the program.

{{% expand "Answer" %}}

{{% notice primary "4.8 Answer" "check" %}}

To achieve path coverage, the following inputs can be used:

```tex
3 and 13 - Branches 1 & 3
4 and 13 - Branches 1 & 4
4 and 29 - Branches 2 & 3
4 and 30 - Branches 2 & 4
```

There are many other possible answers to this question!

{{% /notice %}}

{{% /expand %}}

#### 4.9 Writing Code

Write a complete Python that performs the following actions:

1. Accept a single input from the user and convert it to an integer
1. If the number is even, display "That is an even number". If it is odd, display "That is an odd number".
1. If the number is negative, display "That is a negative number". If it is zero or positive, display "That is a positive number".

Your program should include at least two conditional statements. 

{{% expand "Answer" %}}

{{% notice primary "4.9 Answer" "check" %}}

One possible answer is given below:

```python
x = int(input("Enter an integer: "))
if x % 2 == 0:
  print("That is an even number")
else:
  print("that is an odd number")
if x < 0:
  print("That is a negative number")
else:
  print("That is a positive number")
```

{{% /notice %}}

{{% /expand %}}

#### 4.10 Writing Code

Write a complete Python program in that file that performs the following actions:

1. Accept a single string as input from the user
1. If the string comes before the string "First" in lexicographic order, print "That comes before First". If not, print "That comes after First".
1. If the string comes after the string "last" in lexicographic order, print "That comes after last". If not, print "That comes before last".

Recall that you can use Boolean comparators such as `<` and `>` to compare two strings in Python. Also, pay special attention to the capitalization of the words "First" and "last" in the description above.

Your program should include at least two conditional statements.

_Bonus food for thought: look at your completed answer - is there a path that is not possible to actually test? Why is that?_

{{% expand "Answer" %}}

{{% notice primary "4.10 Answer" "check" %}}

One possible answer is given below:

```python
s = input("Enter a string: ")
if s < "First":
  print("That comes before First")
else:
  print("That comes after First")
if s > "last":
  print("That comes after last")
else:
  print("That comes before last")
```

Notice that it is impossible to provide an input that will come before the string `"First"` **and** after the string `"last"` - therefore one of the four possible paths in this program is impossible to test. In a future lab, we'll see how we can combine these statements in a way that they won't include any impossible paths. 

{{% /notice %}}

{{% /expand %}}



