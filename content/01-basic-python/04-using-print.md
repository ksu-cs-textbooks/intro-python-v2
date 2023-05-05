---
title: "Using Print"
pre: "4. "
weight: 40
---

{{% youtube BhpTb-i4ELg %}}

<!-- TODO rewrite -->

The `print(expression)` statement in Python works in much the same way as the `DISPLAY(expression)` statement in pseudocode, but with one major difference. In pseudocode, the `DISPLAY(expression)` statement will print the value from the expression to the user, but it won't add anything like a space or newline to the end. In Python, however, the `print(expression)` statement will add a newline to the end of the output by default. This means that multiple `print(expression)` statements will print on multiple lines. Let's look at some examples!

Throughout this course, we'll show many different code examples and their output here in the lab. To test them out, feel free to copy the code examples to a Python file and run it yourself. You can even tweak them to do something new and see how Python interprets different pieces of code. In the end, the best way to learn programming is to explore, and running these examples on your own is a great way to get started!

## Example 1 - Multiple Statements

First, let's write a simple program that prints 4 letters separated by spaces:

```tex
DISPLAY("a b c d")
```

Just like our "Hello World" program, when we run this program, we'll see that string printed in the user interface:

```tex
a b c d
```

Ok, that makes sense based on what we've previously seen. The `DISPLAY(expression)` statement will simply display any string expression in our user interface.

Of course, programs can consist of multiple statements or lines of code. So, what if we write a program that contains multiple `DISPLAY(expression)` statements, like this one:

```tex
DISPLAY("one")
DISPLAY("two")
DISPLAY("three")
DISPLAY("four")
```

What do you think will happen when we try to execute this program on our "mental model?" Have we learned a rule that tells us what should happen yet? Recall on the previous page we learned that it will print the value on the user interface, but that's it. So, when we execute this program, we'll see the following output:

```tex
onetwothreefour
```

That's a very interesting result! We might expect that four lines of code would produce four lines of output, but in fact they are all printed on the same line! This is very helpful, since we can use this to construct more complex sentences of output by using multiple `DISPLAY(expression)` statements. 

If we want to add spaces between each line, we'll need to include that in our expressions somehow. For example, we could rewrite the program like this:

```tex
DISPLAY("one ")
DISPLAY("two ")
DISPLAY("three ")
DISPLAY("four")
```

Notice that there is now a space inside of the quotation marks on the first three statements? That will result in this output:

```tex
one two three four
```

There are many other ways we could accomplish this, but this is probably the simplest to learn.

## Example 2 - Multiple Lines

What if we want to print output on multiple lines? How can we do that? In this case, we need to introduce a special symbol, the **newline** symbol. In our pseudocode, as in most programming languages, the newline symbol is represented by a backslash followed by the letter "n", like `\n`, in a string. When our user interface sees a newline symbol, it will move to the next line before printing the rest of the string. The newline symbol itself won't appear in our output.

For example, we can update our previous program to contain newline symbols between each letter:

```tex
DISPLAY("a\nb\nc\nd")
```

This might be a bit difficult to read at first, but as we become more and more familiar with reading code, we'll start to see special symbols like the newline symbol just like any other letter. For now, we'll just have to read closely and make sure we are on the lookout for special symbols in our text.

When we run this program in our "mental model" of a computer, we should see the following output on our user interface:

```tex
a
b
c
d
```

There we go! We've now figured out how to print text on multiple lines.

## Example 3 - Multiple Statements on Multiple Lines

We can even extend this to multiple statements! For example, we can update another one of our previous programs to print each statement on a new line by simply adding a newline character to the end of each string:

```tex
DISPLAY("one\n")
DISPLAY("two\n")
DISPLAY("three\n")
DISPLAY("four")
```

When we execute this program, we'll get the following output:

```tex
one
two
three
four
```

That's pretty much all we need to know in order to use the `DISPLAY(expression)` statement to do all sorts of things in our programs!

## Multiple Lines

In Python, we can print multiple lines of output simply by using multiple `print(expression)` statements:

```python
print("a")
print("b")
print("c")
print("d")
```

will result in this output:

```tex
a
b
c
d
```

We can also include a newline symbol `\n` in a `print(expression)` statement in Python. This will add a newline to the output, and then the `print(expression)` statement will add an additional newline at the end of the value that is printed:

```python
print("one\ntwo")
print("three\nfour")
```

will produce this output:

```tex
one
two
three
four
```

## Printing On the Same Line

What if we want to display multiple `print(expression)` statements on the same line? To do that, we must add an additional option to the `print(expression)` statement - the `end` option. 

For example, the following code will produce output all on the same line:

```python
print("Hello ", end="")
print("World!")
```

In this example, we set `end` to be an empty string `""`. When we run this program, we'll get the following output:

```tex
Hello World!
```

In fact, in Python, the `print(expression)` statement is an example of a **function** in Python. **Functions** in Python are like procedures in pseudocode - when we call them, we write the name of the function, followed by a set of parentheses and then arguments separated by commas within the parentheses. So, in actuality, the `expression` in the `print(expression)` statement is just the first argument when we call the `print` function. 

Therefore, the `end` option that we showed above is just a second argument that is optional - it simply let's us choose what to put at the end of the output. By default, the `end` parameter is set to the newline symbol `\n`, so if we don't provide an argument for `end` it will just add a newline at the end of the value.

We can set the value of `end` to be any string. If we want to include a space at the end of the output, we can add `end=" "` to the `print` function call. 

In this course, we won't spend much time talking about optional parameters and default values in Python functions, but it is important to understand that statements like `print` are actually just Python functions behind the scenes!