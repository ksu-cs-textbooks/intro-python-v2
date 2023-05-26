---
type: "reveal"
hidden: true
---

<section>
    <pre><code style="font-size: 35px; line-height: 40px" class="language-python stretch">x = int(input("Enter a positive integer: "))
while x <= 0:
    print("Invalid input!")
    x = int(input("Enter a positive integer: "))<br>
y = int(input("Enter a positive integer: "))
while y <= 0:
    print("Invalid input!")
    y = int(input("Enter a positive integer: "))<br>
while y <= x:
    for i in range(x - y):
        print("*", end="")
        y = y + 2
    print("")<br>
print("Complete!")
</code></pre>
</section>

<section>
	<img class="stretch plain" src="/images/05/output2.png">
</section>

<section>
	<img class="stretch plain" src="/images/05/output3.png">
</section>

<section>
	<img class="stretch plain" src="/images/05/output4.png">
</section>

<section>
	<img class="stretch plain" src="/images/05/output5.png">
</section>

<section>
    <pre><code style="font-size: 35px; line-height: 40px" class="language-python stretch">x = int(input("Enter a positive integer: "))
while x <= 0:
    print("Invalid input!")
    x = int(input("Enter a positive integer: "))<br>
y = int(input("Enter a positive integer: "))
while y <= 0:
    print("Invalid input!")
    y = int(input("Enter a positive integer: "))<br>
while <mark>y <= x</mark>:
    for i in range(<mark>x - y</mark>):
        print("*", end="")
        y = y + 2
    print("")<br>
print("Complete!")
</code></pre>
</section>
