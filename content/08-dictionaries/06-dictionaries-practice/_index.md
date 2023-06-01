---
title: "Dictionaries Practice"
pre: "6. "
weight: 60
---

Let's try some simple practice problems. These problems are not graded - they are just for you to practice before doing the real exercises in the lab itself. You can find the answers below each question by clicking the button below each question.

#### 8.1 Reading Code

Consider the following Python program:

```python
# Same function as the worked example - only accepts letters
def get_input():
    word = input("Enter a single word: ")
    while not word.isalpha():
        print("Error! Invalid Input!")
        word = input("Enter a single word: ")
    return word


# Notice that this returns a new dictionary
def foo(words):
    output = {}
    for key, value in words.items():
        letter = value[0]
        remain = value[1:]
        for i in range(len(key)):
            new = key[0:i] + letter + key[i:]
            output[new] = remain
        output[key + letter] = remain
    return output


def main():
    word = get_input()
    words = {"": word}
    for i in range(len(word)):
        words = foo(words)
    print(words)


main()
```

Explain, in your own words, how the the keys of the dictionary that is printed at the end relates to the original word that is provided as input.

A fully correct answer is a succinct description of the output as it relates to the input. A partially correct answer is a step-by-step description of each line in the program and the output it will produce based on the input.

_Hint: try using short words, some with unique letters such as "cat" and others with repeated letters such as "abba". Why does the requirement that dictionary be unique help with this?_

{{% expand "Answer" %}}

{{% notice primary "8.1 Answer" "check" %}}

This program creates all possible [**permutations**](https://en.wikipedia.org/wiki/Permutation) of a given set of letters. In simpler terms, it creates all possible unique ways the letters in the word can be rearranged. By using a dictionary, we can prevent duplicate entries since keys must be unique.

{{% /notice %}}

{{% /expand %}}

#### 8.2 Reading Code

Consider the following Python program:

```python
def main():
    values = {
        "M": 1000, "CM": -100, "D": 500, "CD": -100,
        "C": 100, "XC": -10, "L": 50, "XL": -10,
        "X": 10, "IX": -1, "V": 5, "IV": -1, "I": 1 
    }
    n = input("Enter a string: ")
    out = 0
    for i in range(len(n)):
        if i + 1 < len(n) and n[i:i+2] in values:
            out = out + values[n[i:i+2]]
        elif n[i] in values: 
            out = out + values[n[i]]
        else:
            print("Error!")
    print(out)


main()
```

Explain, in your own words, how the output that is eventually printed relates to the string that the user inputs.

A fully correct answer is a succinct description of the output as it relates to the input. A partially correct answer is a step-by-step description of each line in the program and the output it will produce based on the input.

_Hint: what numerical system uses letters such as M, D, C, L, X, V, and I?_

{{% expand "Answer" %}}

{{% notice primary "8.2 Answer" "check" %}}

This program uses a database of characters and their associated [Roman Numeral](https://en.wikipedia.org/wiki/Roman_numerals) values. To handle situations where a lower-valued letter is placed before a higher value (which represents subtraction), it first checks the next pair of letters to handle that subtraction, then if that isn't found it will add the value of the current letter. 

{{% /notice %}}

{{% /expand %}}

#### 8.3 Writing Code

Write a complete Python program that meets the specification below.

The program should first prompt the user to input a single positive integer. If the number provided as input is not positive, the program should print an error and prompt for input again until a valid input is received. Then, the program should use a **dictionary** to convert the individual digits of the number to their equivalent names, and then print the result to the terminal. The keys in the dictionary should be the individual digits, either as strings or integers, and the values should be strings containing the name of each digit.

For example, if the user provides the following input:

```tex
1234
```

The program should produce the following output:

```tex
one two three four
```

To receive full credit, your program must make use of a **dictionary** as described above. Your program must also make use of **two additional functions** in addition to the required `main()` function.

_Be careful about data types! You may find it easier to convert the number back to a string once you've determined that it is positive._

{{% expand "Answer" %}}

{{% notice primary "8.3 Answer" "check" %}}

One possible solution is given below:

```python
def positive_input(n):
    x = int(input("Enter a positive integer greater than {}: ".format(n)))
    while x <= n:
        print("Invalid input!")
        x = int(input("Enter a positive integer greater than {}: ".format(n)))
    return x


def convert_digits(n):
    n = str(n)
    digits = {"0": "zero", "1": "one", "2": "two", "3": "three", "4": "four",
              "5": "five", "6": "six", "7": "seven", "8": "eight", "9": "nine"}
    for digit in n:
        print(digits[digit], end=" ")
    print("")


def main():
    convert_digits(positive_input(0))


main()
```
    
There are many other valid approaches. Hopefully it is clear that the two additional functions should handle prompting for input and converting the digits, respectively.

{{% /notice %}}

{{% /expand %}}
