---
title: "Variables Practice"
pre: "8. "
weight: 80
---

Let's try some simple practice problems. These problems are not graded - they are just for you to practice before doing the real exercises in the lab itself. You can find the answers below each question by clicking the button below each question.

#### 1.4 Reading Code

Write the output that is displayed to the user after running the following Python code:

```python
a = "two"
b = a
c = a
print(c, end=" ")
c = "one"
b = c
a = "three"
print(a, end=" ")
print(c)
```

{{% expand "Answer" %}}

{{% notice primary "1.4 Answer" "check" %}}

The correct answer is:

```tex
two three one
```

{{% /notice %}}

{{% /expand %}}

#### 1.5 Constructing Code

We want to write a program that produces the following output:

```tex
and a 1
and a 2
and a 3
```

Rearrange the following Python statements to create a program that produces that output. You may not use all of these statements in your answer.

```python
x = "1"
x = "2"
x = "3"
print(x)
print(x)
print(x)
print("and a", end=" ")
print("and a", end=" ")
print("and a", end=" ")
```

{{% expand "Answer" %}}

{{% notice primary "1.5 Answer" "check" %}}

One possible answer is given below:

```python
x = "1"
print("and a", end=" ")
print(x)
x = "2"
print("and a", end=" ")
print(x)
x = "3"
print("and a", end=" ")
print(x)
```

{{% /notice %}}

{{% /expand %}}

#### 1.6 Writing Code

We wish to write a Python program that displays the following output:

```tex
abba banana bandana
```

We currently have the following code:

```python
a = "abba"
b = "banana"
c = "bandana"

# more code goes here

print(c, end=" ")
print(b, end=" ")
print(a)
```

Complete the Python program by writing code where the `# more code goes here` comment is found so that the desired output is produced. See if you can do it by only using assignment statements and variables, without using any new string values. (_Hint: you'll need to create a least one new variable!_)

{{% expand "Answer" %}}

{{% notice primary "1.6 Answer" "check" %}}

One possible answer is given below:

```python
a = "abba"
b = "banana"
c = "bandana"

# more code goes here
temp = a
a = c
c = temp

print(c, end=" ")
print(b, end=" ")
print(a)
```

This problem demonstrates the typical process for swapping variables!

{{% /notice %}}

{{% /expand %}}
