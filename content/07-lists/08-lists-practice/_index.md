---
title: "Lists Practice"
pre: "8. "
weight: 80
---

Let's try some simple practice problems. These problems are not graded - they are just for you to practice before doing the real exercises in the lab itself. You can find the answers below each question by clicking the button below each question.

#### 7.1 Reading Code

Consider the following Python program:

```python
def positive_input():
    x = int(input("Enter a positive integer: "))
    while x <= 0:
        print("Invalid input!")
        x = int(input("Enter a positive integer: "))
    return x


def foo(numbers):
    output = []
    for i in range(0, len(numbers) - 1, 2):
        output.append(numbers[i] + numbers[i+1])
    if len(numbers) % 2 == 1:
        output.append(numbers[-1])
    return output


def main():
    print("First, we need the number of inputs.")
    n = positive_input()
    print("Now enter {} numbers:".format(n))
    numbers = []
    for i in range(n):
        numbers.append(positive_input())
    while len(numbers) > 1:
        numbers = foo(numbers)
    print(numbers[0])


main()
```

Explain, in your own words, how the output that is eventually printed relates to the list of numbers that user inputs. 

A fully correct answer is a succinct description of the output as it relates to the input. A partially correct answer is a step-by-step description of each line in the program and the output it will produce based on the input.

_Hint: work through this code as if the user inputs a few unique numbers, and see what is being stored at each step along the way._

{{% expand "Answer" %}}

{{% notice primary "7.1 Answer" "check" %}}

This program will prompt the user to input a list of numbers, then it will print the sum of that list. It does so by repeatedly calling the `foo()` function, which will create a new list of the sums of each pair of adjacent numbers in the original list. 

This is effectively the "reduce" portion of the [MapReduce](https://en.wikipedia.org/wiki/MapReduce) programming model.

{{% /notice %}}

{{% /expand %}}

#### 7.2 Reading Code

Consider the following Python program:

```python
def positive_input():
    x = int(input("Enter a positive integer: "))
    while x <= 0:
        print("Invalid input!")
        x = int(input("Enter a positive integer: "))
    return x


def main():
    n = positive_input()
    numbers = [0, 0, 0, 0, 0, 0, 0, 0, 0, 0]
    while n > 0:
        numbers[n % 10] = numbers[n % 10] + 1
        n = n // 10
    print(numbers)


main()
```

Explain, in your own words, how the output that is eventually printed relates to the number that the user inputs. 

A fully correct answer is a succinct description of the output as it relates to the input. A partially correct answer is a step-by-step description of each line in the program and the output it will produce based on the input.

_Hint: try inputting a number with many digits._

{{% expand "Answer" %}}

{{% notice primary "7.2 Answer" "check" %}}

This program will create a list that contains the count of each digit in the number. Index {{< math >}}$ 0 ${{< /math >}} in the list contains the number of `0`s in the number, index {{< math >}}$ 1 ${{< /math >}} will contain the number of `1`s, and so on.

{{% /notice %}}

{{% /expand %}}

#### 7.3 Writing Code

Write a complete Python program that meets the specification below.

Write a program that will require the user to input {{< math >}}$ 10 ${{< /math >}} positive integers that are in ascending order and stored in a list. If the user inputs a number that is not strictly greater than the previous number stored in the list, the program should simply print an error message and prompt for input again.

Once the list is populated with {{< math >}}$ 10 ${{< /math >}} positive integers in ascending order, it should print the list to the terminal. Then, it should compute and print the difference between the first and last value in the list.

One possible output is shown below:
```tex
[1, 3, 5, 6, 7, 8, 12, 13, 15, 16]
15
```

{{% expand "Answer" %}}

{{% notice primary "7.3 Answer" "check" %}}

One possible solution is shown here:

```
def positive_input(n):
    x = int(input("Enter a positive integer greater than {}: ".format(n)))
    while x <= n:
        print("Invalid input!")
        x = int(input("Enter a positive integer greater than {}: ".format(n)))
    return x


def main():
    nums = []
    nums.append(positive_input(0))
    for i in range(1, 10):
        nums.append(positive_input(nums[i-1]))
    print(nums)
    print(nums[-1] - nums[0])


main()
```

It uses a tweaked version of the `positive_input()` function to prompt for input based on the previous value. To make that work, the first value must be done separately, outside of the for loop, but the other 9 values can be done easily inside of the loop.

To access the last item in the list, we can use negative indexing.
{{% /notice %}}

{{% /expand %}}
