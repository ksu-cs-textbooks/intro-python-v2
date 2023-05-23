---
title: "Math Practice"
pre: "8. "
weight: 80
---

Let's try some simple practice problems. These problems are not graded - they are just for you to practice before doing the real exercises in the lab itself. You can find the answers below each question by clicking the button below each question.

#### 2.1 Reading Code

Write the output that is displayed to the user after running the following Python code:

```python
x = 13
z = "5"
y = int(z)
var = (x + y) % y * y - x
var = var / 2
print(var)
```

_Pay special attention to data types! Make sure the answer is presented as the correct type._

{{% expand "Answer" %}}

{{% notice primary "2.1 Answer" "check" %}}

The correct answer is

```tex
1.0
```

Following order of operations, we do parentheses first:

```python
(x + y) % y * y - x
(13 + 5) % 5 * 5 - 13
18 % 5 * 5 - 13
```

Then we will do multiplication and modulo left to right. Recall that `%` is the modulo operation, so `18 % 5` is the remainder of `18 / 5`, which is `3`:

```python
18 % 5 * 5 - 13
3 * 5 - 13
15 - 13
```

Finally, we do subtraction:

```python
15 - 13
2
```

The last line will compute `2 / 2`, which is just `1.0`. Recall that the division operation always produces a float, not an integer. 

{{% /notice %}}

{{% /expand %}}

#### 2.2 Reading Code

Write the output that is displayed to the user after running the following Python code:

```python
x = 9
y = 3.0
z = 5
ans = (x - z) % 2 // y + z ** (y - 1)
print(ans)
```

_Pay special attention to data types! Make sure the answer is presented as the correct type._

{{% expand "Answer" %}}

{{% notice primary "2.2 Answer" "check" %}}

The correct answer is:

```tex
25.0
```

Following order of operations, we do parentheses first:

```python
(x - z) % 2 // y + z ** (y - 1)
(9 - 5) % 2 // 3.0 + 5 ** (3.0 - 1)
4 % 2 // 3.0 + 5 ** 2.0
```

Then, we'll perform all multiplication, division, modulo, and integer division from left to right:

```python
4 % 2 // 3.0 + 5 ** 2.0
0 // 3.0 + 5 ** 2.0
0.0 + 5 ** 2.0
0.0 + 25.0
```

Finally, we'll perform addition to find the answer of `25.0`.

{{% /notice %}}

{{% /expand %}}

#### 2.3 Writing Code

You are teaching a class and would like to put your students into a number of groups. You know how many students are in the class and the number of groups to create, but you aren't sure how many students should be in each group. 

We'll assume that these values are stored in the `students` and `groups` variables, respectively.

Write a Python program to compute the ideal group size for each group in the class. When divided, the groups in the class should have no fewer than `size` people, and no more than `size+1` people, and there should be exactly `groups` groups total. For example, if there are {{< math >}}$ 15 ${{< /math >}} people and the desired number of groups is {{< math >}}$ 4 ${{< /math >}}, then code should start with the following two variable assignments.

```python
students = 15
groups = 4

# more code goes here
```

Your code should produce the following output for these values:

```tex
groups of 3 or 4
```

This is because the ideal group size for {{< math >}}$ 4 ${{< /math >}} groups out of {{< math >}}$ 15 ${{< /math >}} people is {{< math >}}$ 3 ${{< /math >}}, and all groups should have either {{< math >}}$ 3 ${{< /math >}} or {{< math >}}$ 4 ${{< /math >}} members (in this case, one group of {{< math >}}$ 3 ${{< /math >}} and the rest groups of {{< math >}}$ 4 ${{< /math >}}).

Write the rest of this Python program. Try different values for the `students` and `groups` variables to make sure that your answers are correct!

{{% expand "Answer" %}}

{{% notice primary "2.3 Answer" "check" %}}

One possible answer:


```python
students = 15
groups = 4

# more code goes here
size = students // groups
print("groups of ", end="")
print(size, end="")
print(" or ", end="")
size = size + 1
print(size)
```

The values in the `students` and `groups` variables can be changed. The key is to use the integer division operator to determine the size of each group, though some groups may have 1 more member if there is a remainder. You can even use the modulo operator to determine how many groups will get an extra member!

{{% /notice %}}

{{% /expand %}}