---
title: "Worked Example"
pre: "11. "
weight: 110
---

<!-- EAV raw complete -->

{{% youtube VU6UMrfhkUE %}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

Now that we've explored how to create programs that contain nested loops, let's work through a complete example problem to see how we can convert a problem statement into working code.

Consider the following problem statement:

> Write a program to print the sum of the first `n` prime numbers, where `n` is provided as input from the user. 

This is a very simple problem statement, but it can be very complex to build a program that satisfies it. So, let's go through the steps and see if we can get it to work.

## Handling User Input

The first thing we'll need to do is get input from the user, since we really can't do anything else until we know what our goal is. While the problem statement doesn't include any information about what inputs are acceptable, we can infer that only positive integers should be used as input. So, we can borrow the loop for input from earlier in this module to handle all of our input:

```python
x = int(input("Enter a positive integer: "))
while x <= 0:
    print("Invalid input!")
    x = int(input("Enter a positive integer: "))
n = x
```

Reusing existing code, such as the loop for input we just included here, is a great way to build our programs. We can always think of previous code that we've already written and tested as possible building blocks for future programs, and reusing existing code is a great way to speed up our development process.

## Prime Numbers

Next, we need some way to determine if a number is a prime number. Recall from mathematics that a prime number is a number that is only equally divisible by {{< math >}}$ 1 ${{< /math >}} and itself. For example, {{< math >}}$ 7 ${{< /math >}} is prime, but {{< math >}}$ 8 ${{< /math >}} is not since it can be evenly divided by {{< math >}}$ 4 ${{< /math >}}. 

Thankfully, we know that we can use the modulo operator `%` to determine if a number if evenly divisible by another number. So, all we need to do is check if each number less than our chosen number can equally divide it. If none of them can, then our chosen number is prime.

So, let's write code that performs this operation. We know that we need to check all of the numbers from {{< math >}}$ 2 ${{< /math >}} up to but not including `x`. We can do this using a for loop and the `range()` function:

```python
for i in range(2, x):

```

Inside of the for loop, we want to check and see if the iterator variable `i` can evenly divide the chosen number `n` using the modulo operator:

```python
for i in range(2, x):
    if x % i == 0:
        # i equally divides x
```

Here's where things get a bit tricky - if `i` can equally divide `x`, we know that `x` is not prime. So, let's add a Boolean value to keep track of this. We'll set it initially to `True` before the loop, and then we can set it to `False` as soon as we know the number is not prime:

```python
is_prime = True
for i in range(2, x):
    if x % i == 0:
        is_prime = False
# what if we get here?
```

{{% notice tip "Break Statement" %}}

We might realize that we don't have to check any other values once we have determined that `x` is not prime. So, in our code, we can just use the `break` statement to end the loop early and go to the next part of the code. In effect, we can use this to **shortcut** the rest of the loop.

```python
is_prime = True
for i in range(2, x):
    if x % i == 0:
        is_prime = False
        break
# what if we get here?
```

We don't introduce the `break` and `continue` statements in this class just to simplify things, but you are welcome to use them if you understand them.

{{% /notice %}}

However, what happens if we check all of the values from {{< math >}}$ 2 ${{< /math >}} up to `x` and don't find a single one that will equally divide our chosen number `x`? In that case, we'll reach the end of our for loop, and `is_prime` will still be `True`. So, we've confirmed that `x` is indeed a prime number!

```python
is_prime = True
for i in range(2, x):
    if x % i == 0:
        is_prime = False
# is_prime stores whether nx is prime or not
```

There we go! That's a quick and easy way to determine if a given number is prime. This is a great example of a pattern that we'll see many times as we write complex programs whenever we must determine if a particular situation is true for a given list of numbers. Inside of the loop, we'll check each case and set a value to `False` if it isn't true. If it is true, then we'll complete the entire loop without setting that value to `False`, so we'll know that it is `True` at the end of the code. We'll see this pattern again in a later lab. 

{{% notice info "Efficient Prime Numbers" %}}

The code above is very simple, but not very efficient. With a bit of thought, it is easy to determine that we only have to actually check numbers up to `x /2`, since it is impossible for any number larger than that to evenly divide `x`. Likewise, we can do some quick math to eliminate numbers that end in an even digit or {{< math >}}$ 5 ${{< /math >}}, since those numbers will never be prime. 

Finally, we could use a more advanced mathematical technique such as the [Sieve of Eratosthenes](https://en.wikipedia.org/wiki/Sieve_of_Eratosthenes) to generate all prime numbers more quickly. However, for this example, we'll stick to the simplest approach.

{{% /notice %}}

## Complete Program

Finally, now that we have the code to determine if a number is prime, we can complete our program by simply iterating through all possible numbers until we've found `n` prime numbers, and then print the sum:

```python
x = int(input("Enter a positive integer: "))
while x <= 0:
    print("Invalid input!")
    x = int(input("Enter a positive integer: "))
n = x

count = 0
x = 2
total = 0
while count < n:
    is_prime = True
    for i in range(2, x):
        if x % i == 0:
            is_prime = False
    if is_prime:
        total = total + x
        count = count + 1
    x = x + 1
print(f"The sum of the first {n} prime numbers is {total}")
```

This program requires three additional variables. The variable `count` is used to keep track of the number of prime numbers found, so we'll increment it inside of the `if` statement each time we find a prime number. Likewise, the `total` variable keeps track of the sum of the prime numbers, which we'll print at the end. Finally, we use `x` as our iterator variable, so we must make sure that we increment `x` each time the while loop iterates, outside of the if statement. We'll start `x` at {{< math >}}$ 2 ${{< /math >}}, since {{< math >}}$ 1 ${{< /math >}} is not a prime number mathematically. A _very_ common programming mistake is to forget to increment `x` outside the if statement, resulting in an infinite loop. Also, we chose to use a while loop instead of a for loop since our program's goal is to sum up the first `n` prime numbers, which is better expressed as a while loop instead of a for loop.

Feel free to run this program in Python or using Python Tutor to confirm that it works as expected before continuing.

## Testing

Testing this program is a bit complex, since we can only provide a single input. We can easily provide a negative value or {{< math >}}$ 0 ${{< /math >}} to confirm that the loop handling input is working correctly, but beyond that we have little control over the rest of the program just by changing inputs.

Instead, we have to rely on our ability to read and analyze the code to determine if it is working properly. For example, we can look at the second loop in the main part of the code. It is a while loop, which relies on the `count` variable increasing until it is greater than or equal to `n` before it will terminate. We can see that `count` will be incremented each time the value of `x` is prime, so as long as we are able to find enough prime numbers, and assuming our code to check prime numbers works correctly, this loop should eventually terminate. 

In the code to check if a number is prime, we have a simple for loop, which will always terminate eventually. There is no way to bypass it, so we don't really have to worry about that code not eventually terminating.

However, proving that this program creates the correct answer is a bit trickier. One of the best ways to do this is to simply check a few answers manually. For example, with a bit of searching online, we can find a list of prime numbers. According to [Wikipedia](https://en.wikipedia.org/wiki/List_of_prime_numbers), the first 9 prime numbers are:

```tex
2
3
5
7
11
13
17
19
23
```

The sum of those numbers is easy to calculate using a calculator or other device, and eventually we can be fairly certain that the correct answer is {{< math >}}$ 100 ${{< /math >}}. When we run our program, we should hopefully get the same result:

![Output 6](/images/05/output6.png?classes=border,shadow)

We can test a few other numbers until we are sure that our program is working correctly.

Hopefully this example is a good look at how to build a program using loops that meets a given problem description. We were able to put together various types of loops and conditional statements in our program, and then test it to be sure it works. As you continue to work on projects in this class, feel free to refer back to these examples for ideas and blocks of code that you may want to use in your own programs. Good luck!
