+++
title = "Cash Register"
hidden = true
pre = "A. "
+++

## Implementing a Cash Register

In the second programming assignment, we're going to build a simple cash register to help us manage simple transactions, calculate tax, and make change. Each of these processes is a great way to practice using conditional statements and boolean logic in our code.

{{% notice note "Learning Objectives" %}}

The goal of this assignment is to demonstrate understanding of the following topics in Python:

* Boolean Logic
* Conditional Statements
* Mathematical Operators

{{% /notice %}}

### Tax-Exempt Status

Many organizations also enjoy tax-exempt status, meaning they do not have to pay any sales tax on the items they purchase. Usually this is reserved for non-profit entities or governmental groups. Our program will first ask the user if they are tax exempt, and if so our program will not charge any sales tax at all. In that case, we'll simply ask the user to input a single value:

* The total amount of goods purchased

We can use that value in the rest of our program.

### Taxable vs. Non-Taxable Goods

For users who are not tax-exempt, we must compute a subtotal that includes sales tax. In many areas, certain goods are taxed at different rates. For example, in many states, most food items are not subject to sales tax at all. So, in this program, we're going to model that by asking the user to input two values:

* The total amount of taxable goods purchased
* The total amount of non-taxable goods purchased

These two values will be used to compute the total amount purchased by the user.

### Computing the Subtotal

Once the user has confirmed whether they are tax-exempt or not, and entered the various totals, our program will compute their subtotal. For users with tax-exempt status, this is simple - the subtotal is simply the amount of goods purchased that the user input.

If the user is not tax-exempt, then the total amount will be computed by this formula:

{{< math >}}$$
\text{taxable} * 1.125 + \text{non-taxable} = \text{total}
$${{< /math >}}

We will be using the tax rate {{< math >}}$ 12.5\% ${{< /math >}} in this program. Since we are adding that to the total of taxable goods, we just multiply that value by {{< math >}}$ 1.125 ${{< /math >}}, since this is the same value as {{< math >}}$ \text{taxable} + \text{taxable} * 0.125 ${{< /math >}}.

### Making Change

Once we've determined the total amount for the user, we will also ask the user to input a cash amount they wish to pay. That amount must be equal to or greater than the amount owed - otherwise the program should simply print an error.

If the user pays more than what is owed, we'll need to make change. So, we can subtract the two amounts to find the change that is owed, and then we need to determine what bills and coins must be given to the user. 

For this program, we'll use the American monetary system with the following bills and coins available:

* {{< math >}}$ \$1.00 ${{< /math >}} bill
* {{< math >}}$ \$0.25 ${{< /math >}} quarter coin
* {{< math >}}$ \$0.10 ${{< /math >}} dime coin
* {{< math >}}$ \$0.05 ${{< /math >}} nickel coin
* {{< math >}}$ \$0.01 ${{< /math >}} penny coin

**While there are other denominations we could use, we're limiting ourselves to just these 5 to simplify the program.**

The process for making change in a computer program is _different_ than the process that most of us have learned for computing change by hand. For most of us, we learned to start with the total amount that the user is being charged, and then add the smallest denomination (the penny) until we reach a multiple of {{< math >}}$ 5 ${{< /math >}}, then add nickels and dimes to get to the next quarter, then add quarters to get to the next whole dollar, and so on, until we reach the amount that the user paid. This process works well mentally, but is difficult to program.

Instead, our program should work in the other direction. We start by computing the amount of change to be given, and then determine how many of the largest denomination fit into that amount. We can do this using the truncated division operator `//` when working with whole dollar amounts. Likewise, we can use the modulo operator `%` to determine how much change is left to be given. 

We can repeat this process for the other denominations. However, because they are not whole numbers, the truncated division operator `//` does not work. To solve this, **we can multiply the amount of change to be given by {{< math >}}$ 100 ${{< /math >}} first, and then convert that value to an `int` value.** In effect, we'll be working with a whole number of pennies instead of dollars and cents.

### Making Change Example

Let's work through a brief example. Let's assume that the user is owed {{< math >}}$ \$2.94 ${{< /math >}} in change. So, our first step is to multiply that value by {{< math >}}$ 100 ${{< /math >}} and convert it to an `int`:

{{< math >}}$$
2.94 * 100 = 294
$${{< /math >}}

This tells us that we owe the user the equivalent of {{< math >}}$ 294 ${{< /math >}} pennies. Now, we start with the largest denomination, and determine how many of those fit into the given value. Since we've multiplied everything by {{< math >}}$ 100 ${{< /math >}}, we know that a dollar bill is actually worth {{< math >}}$ 100 ${{< /math >}} pennies. So, we'll find the result of dividing {{< math >}}$ 294 ${{< /math >}} by {{< math >}}$ 100 ${{< /math >}} using truncated division:

{{< math >}}$$
294 \text{ // } 100 = 2
$${{< /math >}}

So, we owe the user {{< math >}}$ 2 ${{< /math >}} dollar bills. To find the remaining amount of change to give, we'll use the modulo operator:

{{< math >}}$$
294 \text{ % } 100 = 94
$${{< /math >}}

We still have {{< math >}}$ 94 ${{< /math >}} cents to give. The next denomination is the quarter, which is worth {{< math >}}$ 25 ${{< /math >}} cents. So, we can repeat the same process:

```math
$$
\displaylines{94 \text{ // } 25 = 3 \\ 94 \text{ % } 25 = 19}
$$
```

That means we owe the user {{< math >}}$ 3 ${{< /math >}} quarters, with {{< math >}}$ 19 ${{< /math >}} cents left over. We do this again for the dimes:

{{< math >}}$$
\displaylines{19 \text{ // } 10 = 1 \\ 19 \text{ % } 10 = 9}
$${{< /math >}}

and nickels, which will also give us the number of pennies:

{{< math >}}$$
\displaylines{9 \text{ // } 5 = 1 \\ 19 \text{ % } 5 = 4}
$${{< /math >}}

So, in total, we owe the user {{< math >}}$ 2 ${{< /math >}} dollars, {{< math >}}$ 3 ${{< /math >}} quarters, {{< math >}}$ 1 ${{< /math >}} dime, {{< math >}}$ 1 ${{< /math >}} nickel, and {{< math >}}$ 4 ${{< /math >}} pennies, for a total of {{< math >}}$ \$2.94 ${{< /math >}}

## The Assignment

Write your program in a file named `homework2.py`. This should be a complete Python program consisting of the following elements:

1. A prompt to determine the user's tax-exempt status
2. Prompts to get the total of taxable and non-taxable goods as appropriate
3. Calculation and output of the subtotal including applicable tax
4. A prompt asking the user the amount of money paid
5. Calculation and output of the change to be given by denomination

Each element will be described in detail below.

## Prompts and Calculation for Subtotal

The program should first prompt the user to input whether they are tax-exempt or not:

* If the user inputs either the string `"yes"` or `"true"`, they are considered tax-exempt.
* If the user inputs any other value, they are not tax-exempt.

If the user is determined to be tax-exempt, simply prompt the user to input a total amount of goods purchased as a decimal number. If the user is not tax-exempt, prompt the user to input both the amount of taxable goods purchased as well as the amount of non-taxable goods purchased as two separate decimal numbers.

Once the user has input all required values, this method should compute the subtotal as described above (including applicable tax) and print output in the following format:

```tex
Your total today is ${subtotal}
```

{{% notice info "Formatting Dollar Amounts" %}}

Notice that each dollar amount is formatted using commas if needed, as well as only two digits after the decimal place. You can do this by using the format specifier `,.2f` as part of your f-string placeholder, as shown in this example:

```python
value = 12345.6789
print(f"You have ${value:,.2f} in your account")
```

which will print:

```tex
You have $12,345.68 in your account
```

You can refer to the [Python Documentation](https://docs.python.org/3/library/string.html#formatstrings) for more information these format specifications.

{{% /notice %}}

## Making Change

Once the subtotal is computed, the program should prompt the user to input an amount to pay as a decimal number. 

If the amount to pay is strictly less than the total amount owed, the program should simply print `"Error! Not enough money paid"` and end the program. 

If the amount to pay is exactly equal to the total amount owed, this function should simply print `"No change needed"` and end the function.

Otherwise, this method should compute the change to be given following the method described above, and produce output in the following format:

```tex
You are owed ${change} in change:
{a} dollars {b} quarters {c} dimes {d} nickels {e} pennies
```

However, if any of the values `a`, `b`, `c`, `d`, or `e` in the output above are {{< math >}}$ 0 ${{< /math >}}, that denomination should be omitted from the output. For example, if the user is only owed {{< math >}}$ 2 ${{< /math >}} quarters and {{< math >}}$ 3 ${{< /math >}} pennies, the output should be:

```tex
You are owed $0.53 in change:
2 quarters 3 pennies.
```

{{% notice note "Combining Conditionals and Printing" %}}

We can think of `conditionally` printing output where the condition is `if denomination is not zero` then we will do some printing. There are at least two ways that this can be done. The first way utilizes string concatenation. For example:

```python
a = 37
b = 22
c = 55

output = "The following are greater than 30: "
if a > 30: 
    output = output + str(a) + " "
if b > 30:
    output = output + str(b) + " "
if c > 30: 
    output = output + str(c)
print(output)
```

which will print:

```tex
The following are greater than 30: 37 55
```

The second way utilizes the `end` attribute of the `print` function. For example: 
```python
a = 37
b = 22
c = 55

print("The following are greater than 30: ", end="")
if a > 30: 
    print(str(a), end=" ")
if b > 30:
    print(str(b), end=" ")
if c > 30: 
    print(str(c), end="")
print()
```

which will print:

```tex
The following are greater than 30: 37 55
```

{{% /notice %}}


{{% notice warning "Ending a Program Early" %}}

There are several ways to end a Python program before the end of the code is reached, such as `sys.exit()`. However, we don't recommend using this method, even though many online resources refer to it. 

Instead, we can place the rest of the code for the function in the `else:` branch of the conditional statement:

```python
if <boolean expression>:
    print("Error")
else:
    <remaining code>
```

If the error condition is reached and the `"Error"` message is printed, the interpreter will skip the else branch and reach the end of the code.

{{% /notice %}}

{{% notice info "Floating-Point Precision Errors" %}}

There is a slight chance that you'll run into issues with floating-point precision errors, where your results are off by one penny in either direction. This is due to the imprecise nature of floating-point numbers. Dealing with that appropriately is outside the scope of this class. **You will not be penalized if your program encounters one of these errors while it is being graded.**

You can see examples of this in the two program runs below. Behind the scenes, the program knows the total is actually {{< math >}}$ 2.61375 ${{< /math >}}, so even though it is displayed as {{< math >}}$ 2.61 ${{< /math >}} it is computed using the actual total.

![Sample Run Bad](/images/hw2/hw2c.png?classes=border,shadow)

{{% /notice %}}

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

Below are a couple of screenshots showing a sample execution of the model solution for this homework assignment. Your submission should have similar functionality and output, but the text for input prompts may differ slightly:

![Sample Run 1](/images/hw2/hw2a.png?classes=border,shadow)

![Sample Run 2](/images/hw2/hw2b.png?classes=border,shadow)

## Grading Rubric

Your project will be graded according to the following rubric:

* Getting Totals & Computing Subtotal: 40%
* Not Enough Paid & Exact Amount Paid: 10%
* Making Change & Printing Outputs: 40%
* Documentation Comments: 10%

## Submitting

Once you have completed this program, submit your `homework2.py` file via Codio or the assignment on Canvas.
