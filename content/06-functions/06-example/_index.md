---
title: "Worked Example"
pre: "6. "
weight: 60
---

{{% youtube VU6UMrfhkUE %}}

<!-- Old: VU6UMrfhkUE -->
<!-- EAV: rerecord this one -->

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

Now that we've explored how to create functions, let's work through a one of our previous worked examples to see how we could approach building that same program, but this time using some functions to simplify our code a bit.

Consider the following problem statement:

> Write a program to print the sum of the first `n` prime numbers, where `n` is provided as input from the user. 

This is a very simple problem statement, but it can be very complex to build a program that satisfies it. So, let's go through the steps and see if we can get it to work.

## Handling User Input

Now that we've learned about functions and the `main()` function, we can start with that structure. It is always good practice to include a `main()` function and a call to the `main()` function to our code, as shown here:

```python
def main():


main()
```

Inside of the `main()` function, the first thing we'll need to do is get input from the user, since we really can't do anything else until we know what our goal is. While the problem statement doesn't include any information about what inputs are acceptable, we can infer that only positive integers should be used as input. So, we can borrow the loop for reading a positive input from earlier to handle all of our input. This time, we'll put it in a function called `positive_input()`, and this function will return the value input by the user once it is accepted:

```python
def positive_input():
    x = int(input("Enter a positive integer: "))
    while x <= 0:
        print("Invalid input!")
        x = int(input("Enter a positive integer: "))
    return x


def main():
    n = positive_input()


main()
```

We'll also add a call to that function in our `main()` function, and store the input provided by the user in the variable `n` inside of our `main()` function. Notice that the variable `x` in the `positive_input()` function is the value that is returned, but we are storing it in a different variable inside of the `main()` function. We'll have to keep track of the location of that value as we think about our program. Thankfully, Python Tutor can help us learn how to do this, so feel free to follow along and build this program in Python Tutor and run it there to see how it works. 

Building reusable functions, such as the `positive_input()` function we just created here, is a great way to build our programs. We can always think of previous code that we've already written and tested as possible building blocks for future programs, and reusing existing code is a great way to speed up our development process.

## Prime Numbers

Next, we need some way to determine if a number is a prime number. Recall from mathematics that a prime number is a number that is only equally divisible by {{< math >}}$ 1 ${{< /math >}} and itself. For example, {{< math >}}$ 7 ${{< /math >}} is prime, but {{< math >}}$ 8 ${{< /math >}} is not since it can be evenly divided by {{< math >}}$ 4 ${{< /math >}}. 

Thankfully, we know that we can use the modulo operator `%` to determine if a number if evenly divisible by another number. So, all we need to do is check if each number less than our chosen number can equally divide it. If none of them can, then our chosen number is prime.

So, let's write another function that performs this operation. We'll start by creating a function that accepts our chosen number as a parameter:

```python
def is_prime(n):

```

Next, we know that we need to check all of the numbers from {{< math >}}$ 2 ${{< /math >}} up to but not including `n`. We can do this using a for loop and the `range()` function:

```python
def is_prime(n):
    for i in range(2, n):

```

Inside of the for loop, we want to check and see if the iterator variable `i` can evenly divide the chosen number `n` using the modulo operator:

```python
def is_prime(n):
    for i in range(2, n):
        if n % i == 0:
            # i equally divides n
```

Here's where things get a bit tricky - if `i` can equally divide `n`, we know that `n` is not prime and we don't have to check any other values. So, in our function, we can just use the `return False` statement to return the value `False` from this function. As soon as the function reaches a `return` statement, even if it is inside of a loop, it will immediately stop the function and go back to where it was called from. In effect, we can use this to **shortcut** the rest of the loop.

```python
def is_prime(n):
    for i in range(2, n):
        if n % i == 0:
            return False
    # what if we don't return false?
```

However, what happens if we check all of the values from {{< math >}}$ 2 ${{< /math >}} up to `n` and don't find a single one that will equally divide our chosen number `n`? In that case, we'll reach the end of our for loop, but our function hasn't returned anything. So, we'll need to add one extra line to the end of the function to `return True` if we get to that point.

```python
def is_prime(n):
    for i in range(2, n):
        if n % i == 0:
            return False
    return True
```

There we go! That's a quick and easy function to determine if a given number is prime. This function is a great example of a pattern that we'll see many times as we write complex programs whenever we must determine if a particular situation is true for a given list of numbers. Inside of the loop, we'll check each case and return `False` if it isn't true. If it is true, then we'll complete the entire loop without returning `False`, so we'll need to return `True` at the end of the function. We'll see this pattern again in a later lab. 

## Complete Program

Finally, now that we have the `is_prime()` function, we can complete our `main()` function by simply iterating through all possible numbers until we've found `n` prime numbers, and then print the sum:

```python
def main():
    n = positive_input()
    count = 0
    i = 2
    sum = 0
    while count < n:
        if is_prime(i):
            sum = sum + i
            count = count + 1
        i = i + 1
    print(f"The sum of the first {n} prime numbers is {sum}")
```

This program requires three additional variables. The variable `count` is used to keep track of the number of prime numbers found, so we'll increment it inside of the `if` statement each time we find a prime number. Likewise, the `sum` variable keeps track of the sum of the prime numbers, which we'll print at the end. Finally, we use `i` as our iterator variable, so we must make sure that we increment `i` each time the while loop iterates, outside of the if statement. We'll start `i` at {{< math >}}$ 2 ${{< /math >}}, since {{< math >}}$ 1 ${{< /math >}} is not a prime number mathematically. A _very_ common programming mistake is to forget to increment `i` outside the if statement, resulting in an infinite loop. Also, we chose to use a while loop instead of a for loop since our program's goal is to sum up the first `n` prime numbers, which is better expressed as a while loop instead of a for loop.

The full program is shown below:

```python
def positive_input():
    x = int(input("Enter a positive integer: "))
    while x <= 0:
        print("Invalid input!")
        x = int(input("Enter a positive integer: "))
    return x


def is_prime(n):
    for i in range(2, n):
        if n % i == 0:
            return False
    return True


def main():
    n = positive_input()
    count = 0
    i = 2
    sum = 0
    while count < n:
        if is_prime(i):
            sum = sum + i
            count = count + 1
        i = i + 1
    print(f"The sum of the first {n} prime numbers is {sum}")


main()
```

Finally, notice that this program doesn't contain a loop nested within another loop in the same function, but because we are calling the `is_prime()` function, which contains a loop, from within a loop inside of the `main()` function, it actually has a nested loop structure inside of it! Feel free to run this program in Python or using Python Tutor to confirm that it works as expected.