---
type: "reveal"
hidden: true
---

<section>
    <pre><code style="font-size: 29px; line-height: 35px" class="language-python stretch">x = float(input("Enter a percentage as a decimal number from 0 to 1: "))
while(x < 0 or x > 1):
    print("Invalid Input!")
    x = float(input("Enter a percentage as a decimal number from 0 to 1: "))
</code></pre>
</section>

<section>
    <pre><code style="font-size: 22px; line-height: 25px" class="language-python stretch">print("This program will compute weighted average for three exam scores")
print("Enter the first exam's score")
x = float(input("Enter a percentage as a decimal number from 0 to 1: "))
while(x < 0 or x > 1):
    print("Invalid Input!")
    x = float(input("Enter a percentage as a decimal number from 0 to 1: "))
exam1_score = x
print("Enter the first exam's weight")
x = float(input("Enter a percentage as a decimal number from 0 to 1: "))
while(x < 0 or x > 1):
    print("Invalid Input!")
    x = float(input("Enter a percentage as a decimal number from 0 to 1: "))
exam1_weight = x
print("Enter the second exam's score")
x = float(input("Enter a percentage as a decimal number from 0 to 1: "))
while(x < 0 or x > 1):
    print("Invalid Input!")
    x = float(input("Enter a percentage as a decimal number from 0 to 1: "))
exam2_score = x
print("Enter the second exam's weight")
x = float(input("Enter a percentage as a decimal number from 0 to 1: "))
while(x < 0 or x > 1):
    print("Invalid Input!")
    x = float(input("Enter a percentage as a decimal number from 0 to 1: "))
exam2_weight = x
print("Enter the third exam's score")
x = float(input("Enter a percentage as a decimal number from 0 to 1: "))
while(x < 0 or x > 1):
    print("Invalid Input!")
    x = float(input("Enter a percentage as a decimal number from 0 to 1: "))
exam3_score = x
print("Enter the third exam's weight")
x = float(input("Enter a percentage as a decimal number from 0 to 1: "))
while(x < 0 or x > 1):
    print("Invalid Input!")
    x = float(input("Enter a percentage as a decimal number from 0 to 1: "))
exam3_weight = x
total = exam1_score * exam1_weight + exam2_score * exam2_weight + exam3_score * exam3_weight
print(f"Your total score is {total}")
</code></pre>
</section>

<section>
	<img class="stretch plain" src="/intro-python/images/05/input.png">
</section>
