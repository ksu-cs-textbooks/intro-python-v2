---
type: "reveal"
hidden: true
---

<section>
    <h3>Problem Statement</h3>
    <p style="font-size: 55px">Write a program to print the sum of the first <code>n</code> prime numbers, where <code>n</code> is provided as input from the user. </p>
</section>

<section>
	<h3>Handling Input</h3>
    <pre><code style="font-size: 40px; line-height: 45px" class="language-python stretch">x = int(input("Enter a positive integer: "))
while x <= 0:
    print("Invalid input!")
    x = int(input("Enter a positive integer: "))
n = x
</code></pre>
</section>

<section>
	<h3>Prime Numbers</h3>
    <pre><code style="font-size: 40px; line-height: 45px" class="language-python stretch">for i in range(2, x):
</code></pre>
</section>

<section>
	<h3>Prime Numbers</h3>
    <pre><code style="font-size: 40px; line-height: 45px" class="language-python stretch">for i in range(2, x):
    if x % i == 0:
        # i equally divides x
</code></pre>
</section>

<section>
	<h3>Prime Numbers</h3>
    <pre><code style="font-size: 40px; line-height: 45px" class="language-python stretch">is_prime = True
for i in range(2, x):
    if x % i == 0:
        is_prime = False
# what if we get here?
</code></pre>
</section>

<section>
	<h3>Prime Numbers</h3>
    <pre><code style="font-size: 40px; line-height: 45px" class="language-python stretch">is_prime = True
for i in range(2, x):
    if x % i == 0:
        is_prime = False
        <<mark>break</mark>
# what if we get here?
</code></pre>
</section>

<section>
	<h3>Prime Numbers</h3>
    <pre><code style="font-size: 40px; line-height: 45px" class="language-python stretch">is_prime = True
for i in range(2, x):
    if x % i == 0:
        is_prime = False
# is_prime stores whether nx is prime or not
</code></pre>
</section>

<section>
	<h3>Full Program</h3>
    <pre><code style="font-size: 40px; line-height: 45px" class="language-python stretch">x = int(input("Enter a positive integer: "))
while x <= 0:
    print("Invalid input!")
    x = int(input("Enter a positive integer: "))
n = x<br>
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
</code></pre>
</section>

<section>
	<h3>Testing</h3>
	<ul>
	    <li>Input Code</li>
		<li>Outer While Loop</li>
        <li>Inner For Loop</li>
	</ul>
	<br><br>
	<p style="font-size: 60px;" class="fragment">2 + 3 + 5 + 7 + 11 + 13 + 17 + 19 + 23 = 100</p>
</section>

<section>
	<img class="stretch plain" src="/images/05/output6.png">
</section>