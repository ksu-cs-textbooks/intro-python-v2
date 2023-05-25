---
title: "Nesting Practice"
pre: "15. "
weight: 150
---

Let's try some simple practice problems. These problems are not graded - they are just for you to practice before doing the real exercises in the lab itself. You can find the answers below each question by clicking the button below each question.

#### 4.11 Reading Code

Consider the following Python program:

```python
p1 = int(input("Enter a positive integer for player 1: "))
p2 = int(input("Enter a positive integer for player 2: "))
p3 = int(input("Enter a positive integer for player 3: "))

if p1 <= 0 or p2 <= 0 or p3 <= 0:
    print("Error")
else:
    twos = (p1 + p2 + p3) // 2
    threes = (p1 + p2 + p3) // 3
    fours = (p1 + p2 + p3) // 4
    if p1 == p2 or p2 == p3 or p3 == p1:
        print("Tie")
    elif p1 != twos and p2 != threes and p3 != fours:
        print("Draw")
    else:
        if p1 == twos:
            print("Player 1 Wins")
        if p2 == threes:
            print("Player 2 Wins")
        if p3 == fours:
            print("Player 3 Wins")
```

Explain, in your own words, a set of rules for the game that this program is simulating. 

A fully correct answer is a succinct set of rules for the game and what leads to the various outcomes. A partially correct answer is a step-by-step description of each line in the program and the output it will produce based on the input.

_Hint: it is possible for multiple players to win a round in this game._

{{% expand "Answer" %}}

{{% notice primary "4.11 Answer" "check" %}}

One way to express the rules of this game is given below:

> Three players each guess a positive integer greater than {{< math >}}$ 0 ${{< /math >}}, and then share them simultaneously. The winner is chosen following this formula:
> * If any two players have chosen the same number, the game is a tie.
> * Otherwise, compute the sum of the three numbers, and then determine the number of twos, threes, and fours that fit in that number. (Mathematically, perform division and round down.)
>   * If player 1 correctly guesses the number of twos in the sum, they win.
>   * If player 2 correctly guesses the number of threes in the sum, they win.
>   * If player 3 correctly guesses the number of fours in the sum, they win.
>   * _It is possible for multiple players to win._
> * If no players have won, then the game is a draw.

{{% /notice %}}

{{% /expand %}}

#### 4.12 Testing Code

Consider the Python program in the question above. Give a set of inputs that will achieve **branch coverage** for this program. You do not have to achieve **path coverage**!

_Hint: try `3, 2, 1` as one possible input. What branches will that execute?_

{{% expand "Answer" %}}

{{% notice primary "4.12 Answer" "check" %}}

To achieve branch coverage, the following inputs can be used:

* Error: `-1, -1, -1`
* Tie: `1, 1, 1`
* Draw: `2, 1, 3`
* All Win: `3, 2, 1`

_This does not achieve path coverage. To do that, you'd need to come up with a set of inputs that result in all possible combinations of players winning. The rules of this game make that a bit difficult to do easily._

{{% /notice %}}

{{% /expand %}}

#### 4.13 Writing Code

Write a complete Python program that meets the specification below.

A childcare supervisor has developed a set of rules to determine if children under their care may play indoors or outdoors. Here are the rules:

1. If it is raining, then the children must play indoors since they'll get wet. This rule takes precedence over all other rules.
2. If the temperature is below 0&deg; C, then the children must play indoors because it is too cold, unless there is snow on the ground. In that case, children may play both indoors and outdoors.
3. If the temperature is above 40&deg; C, then the children must play indoors because it is too hot, unless the pool is open. In that case, children may play both indoors and outdoors. 
4. If the temperature is between 20&deg; C and 30&deg; C, then the children must play outdoors because it is a nice day.
5. Otherwise, if no other rules are matched, children may choose to play both indoors and outdoors. 

Write a program that will help determine if the children may play indoors, outdoors, or both. The program will prompt the user for four inputs in the following order:

1. The temperature as an integer (measured in degrees Celsius).
1. Whether it is raining: `yes` or `no`.
1. Whether there is snow on the ground: `yes` or `no`.
1. Whether the pool is open: `yes` or `no`.

The program should output either `indoors`, `outdoors`, or `both`, depending on the rules described above. Your program must make use of chained and/or nested conditional statements.

_Hint: after reading input, the `yes` and `no` answers can be converted to Boolean values once and stored in Boolean variables. This will simplify the Boolean expressions used in the conditional statements._

{{% expand "Answer" %}}

{{% notice primary "4.13 Answer" "check" %}}

Below is one possible solution:

```python
temperature = int(input("Enter the temperature in degrees Celsius: "))
raining = input("Is it raining? 'yes' or 'no': ") == "yes"
snow = input("Is there snow on the ground? 'yes' or 'no': ") == "yes"
pool = input("Is the pool open? 'yes' or 'no': ") == "yes"

if raining:
    print("indoors")
else:
    if temperature < 0:
        if snow:
            print("both")
        else:
            print("indoors")
    elif temperature > 40:
        if pool:
            print("both")
        else:
            print("indoors")
    elif 20 < temperature and temperature < 30:
        print("outdoors")
    else:
        print("both")
```

Notice that it immediately checks if the inputs of `yes` or `no` are equal to `yes`, which will convert them to a Boolean value. Then, in the conditional statements, Boolean values can be used without any operators. 

{{% /notice %}}

{{% /expand %}}

