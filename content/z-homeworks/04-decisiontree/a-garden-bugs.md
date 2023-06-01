+++
title = "Garden Bug Decision Tree"
hidden = true
pre = "A. "
+++

## Implementing a Decision Tree

In this homework assignment, we're going to build a program to help us identify creatures we might find in our garden using a [Decision Tree](https://en.wikipedia.org/wiki/Decision_tree). Decision trees are an important part of knowledge modeling in the field of artificial intelligence, but they've also been used by scientists for centuries to aid in identifying and classifying everything from species of plants and animals to different types of rocks.

{{% notice note "Learning Objectives" %}}

The goal of this assignment is to demonstrate understanding of the following topics in Python:

* Nested Conditional Statements
* Handling User Input
* Functions, Parameters, Arguments, and Return


{{% /notice %}}

{{% notice info "Identification Keys and Twenty Questions" %}}

This project will actually be implementing a specific type of a decision tree, known as an [Identification Key](https://en.wikipedia.org/wiki/Identification_key). An example for identifying different types of rocks is shown below:

![Rock Identification](/images/hw4/rocks.jpg?classes=border,shadow)[^1]

_Right-click and choose Open Image in New Tab to see larger_


[^1]: https://www.vagabondgeology.com/rocks--rock-identification.html

This identification key is known as a **dichotomous key**, since each decision step has exactly two options. To use this key, simply grab a rock and answer the questions starting at the top, and see if it gives you the correct answer.

A more advanced version of a decision tree is the game [Twenty Questions](https://en.wikipedia.org/wiki/Twenty_questions), where one player chooses a secret object and then one or several other players ask simple "yes" or "no" questions to try and guess the object.

There are many approaches that can be used to simulate this game in a computer. For example, a simple decision tree can be used, with answers hard-coded at the end of each line of questioning. If all twenty questions are used, it is possible to accurately describe {{< math >}}$ 2^{20} ${{< /math >}} or {{< math >}}$ 1048576 ${{< /math >}} unique objects.

There are also many [artificial intelligence](https://www.baeldung.com/cs/decision-trees-20-questions) approaches that can be used. 

{{% /notice %}}

## Identifying Garden Bugs

For this assignment, we'll build a program that implements the following decision tree, which is used to identify bugs you might find in a garden:

![Garden Bugs](/images/hw4/bugs.jpg?classes=border,shadow)[^2]

_Right-click and choose Open Image in New Tab to see larger_

[^2]: https://static.studyladder.com/cdn/course/4d/6bfcae898e3b.jpg

Most of the questions in this tree have two possible answers, but there is at least one question with three possible answers. So, we'll have to take that into account when building our program!

## The Assignment

Write your program in a file named `homework4.py`. This should be a **complete Python program** consisting of the following elements:

1. A `two_inputs(prompt, input_1, input_2)` function
1. A `three_inputs(prompt, input_1, input_2, input_3)` function
1. A `main()` function
1. A call to the `main()` function

Each function will be described in detail below.

## The Two Inputs Function

The `two_inputs()` function requires three parameters:

* `prompt` - the prompt to display to the user for input
* `input_1` - the first possible input the user can choose
* `input_2` - the second possible input the user can choose

This function should first print `prompt` to the terminal. Then, it should allow the user to choose between `input_1` and `input_2` by choosing a number matching the given input. The input should be converted to an integer.

The function should check to see if the integer provided is a valid input. If not, the function should print `"Error!"` and prompt the user for another input. It should repeat this until a valid input is received.

The function should then **return** the value input by the user.

An example of using this function to prompt the user for input to answer the first question on the tree is shown below:

![Question 1](/images/hw4/q1.png?classes=border,shadow)

## The Three Inputs Function

The `three_inputs()` function requires four parameters:

* `prompt` - the prompt to display to the user for input
* `input_1` - the first possible input the user can choose
* `input_2` - the second possible input the user can choose
* `input_3` - the third possible input the user can choose

This function should first print `prompt` to the terminal. Then, it should allow the user to choose between `input_1`, `input_2`, and `input_3` by choosing a number matching the given input. The input should be converted to an integer.

The function should check to see if the integer provided is a valid input. If not, the function should print `"Error!"` and prompt the user for another input. It should repeat this until a valid input is received.

The function should then **return** the value input by the user.

An example of using this function to prompt the user for input to answer the a second question on the tree is shown below:

![Question 2](/images/hw4/q2.png?classes=border,shadow)

## The Main Function

The `main()` function should begin by printing a welcome message to the user explaining the program and its usage. Then, it should use either the `two_inputs()` or `three_inputs()` functions (as needed) and nested conditional statements to walk the user through the decision tree shown above until an answer is found. The `main()` function itself should never prompt the user for input directly, but it should print messages to the user when the type of bug is determined in the decision tree. 

Because the `two_inputs()` and `three_inputs()` functions will confirm that the user always inputs a valid value, the `main()` function should not print any error messages.  

## Documentation & Comments

You may add any comments to your code to help explain how it works. In Python, you can use the hash symbol `#` (also known as a pound sign or octothorpe) in front of a line of text in a Python file to make it a comment:

```python
# This is a code comment
x = 15
y = 7  # comments can be at the end of lines, too
```

## Required Documentation Comment

Your file must include a **documentation comment**, also known as a **docstring** at the top of your file. The **docstring** should be formatted like this:

```python
"""
File Name: <filename>
Author: <your name>
Version: <submission date>
Section: <your section>
Description: <detailed description of this program>
"""
```

Notice that the start and end of the documentation comment uses three double-quotes `"""` on a single line.

## Sample Execution

Below is a screenshot showing several sample executions of the model solution for this homework assignment. Your submission should have similar functionality and output, but the text for input prompts may differ slightly:

![Sample Runs](/images/hw4/examples.png?classes=border,shadow)

## Submitting

Once you have completed this program, submit your `homework4.py` file via Codio or the assignment on Canvas.