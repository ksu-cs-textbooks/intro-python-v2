---
title: "Input Practice"
pre: "6. "
weight: 60
---

Let's try some simple practice problems. These problems are not graded - they are just for you to practice before doing the real exercises in the lab itself. You can find the answers below each question by clicking the button below each question.

#### 3.1 Reading Code

Write the output that is displayed to the user after running the following Python code:

```python
x = input("Enter a number: ")
y = x + "00"
z = int(y)
a = int(z + (z / 100))
print(f"The result is {a}")
```

Assume the user inputs the string `"4"` when prompted.

{{% expand "Answer" %}}

{{% notice primary "3.1 Answer" "check" %}}

The correct answer is:

```tex
The result is 404
```

{{% /notice %}}

{{% /expand %}}

#### 3.2 Reading Code

Write the output that is displayed to the user after running the following Python code:

```python
x = int(input("Enter a number: "))
x = x // 100 * 100 + x % 10
print(f"The answer twice is {x * 2}")
```

Assume the user inputs the string `"121"` when prompted.

{{% expand "Answer" %}}

{{% notice primary "3.2 Answer" "check" %}}

The correct answer is:

```tex
The answer twice is 202
```

Notice that the `x * 2` expression results in the value 202 instead of the string `"101101"`. This is because `x` is an integer value, not a string. So, the `*` operator is interpreted as multiplication, not string repetition. We have to carefully keep track of what data type each variable is storing in order to truly understand what the code will do.

{{% /notice %}}

{{% /expand %}}

#### 3.3 Writing Code

Write a Python program that prompts the user to input a verb and a noun that will be stored in separate variables. Then, use those two words to create a simple compliment for the user and print it to the terminal. The compliment should be in the form of:

```tex
You "<verb>" my "<noun>"? That's awesome!
```

For example, if the user inputs `"love"` and `"food"`, then the string printed by the program should be:

```tex
You "love" my "food"? That's awesome!
```

_Hint: Notice that the output includes quotation marks around the two words provided by the user, and an apostrophe (single quote) as well. You'll need to account for this in your code!_

You can expand on this program to prompt the user for additional inputs, and use f-strings to create a [Mad Libs](https://en.wikipedia.org/wiki/Mad_Libs) style game!

{{% expand "Answer" %}}

{{% notice primary "3.3 Answer" "check" %}}

One possible answer is:

```python
verb = input("Enter a verb: ")
noun = input("Enter a noun: ")
print(f"You \"{verb}\" my \"{noun}\"? That's awesome!")
```

The biggest point to remember is that quotation marks need to be escaped. If you try to use single quotes instead of double quotes around the f-string, you'll need to escape the apostrophe (single quote) instead. 

{{% /notice %}}

{{% /expand %}}
