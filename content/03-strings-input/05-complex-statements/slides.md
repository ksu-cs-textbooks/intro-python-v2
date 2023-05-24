---
type: "reveal"
hidden: true
---

<section>
    <pre><code style="font-size: 35px; line-height: 40px" class="language-python stretch">text_one = input("Enter the first number: ")
one = int(text_one)
text_two = input("Enter the second number: ")
two = int(text_two)
one = one * one
two = two * two
total = one + two
print(f"The sum of squares of {one} and {two} is {total}")
</code></pre>
</section>

<section>
    <pre><code style="font-size: 35px; line-height: 40px" class="language-python stretch">text_one = input("Enter the first number: ")
one = int(text_one)
text_two = input("Enter the second number: ")
two = int(text_two)
<mark>one = one * one</mark>
<mark>two = two * two</mark>
<mark>total = one + two</mark>
print(f"The sum of squares of {one} and {two} is {total}")
</code></pre>
</section>

<section>
    <pre><code style="font-size: 35px; line-height: 40px" class="language-python stretch">text_one = input("Enter the first number: ")
one = int(text_one)
text_two = input("Enter the second number: ")
two = int(text_two)
<mark>total = (one * one) + (two * two)</mark>
print(f"The sum of squares of {one} and {two} is {total}")
</code></pre>
</section>

<section>
    <pre><code style="font-size: 35px; line-height: 40px" class="language-python stretch"><mark>text_one = input("Enter the first number: ")</mark>
<mark>one = int(text_one)</mark>
<mark>text_two = input("Enter the second number: ")</mark>
<mark>two = int(text_two)</mark>
total = (one * one) + (two * two)
print(f"The sum of squares of {one} and {two} is {total}")
</code></pre>
</section>

<section>
    <pre><code style="font-size: 35px; line-height: 40px" class="language-python stretch"><mark>one = int(input("Enter the first number: "))</mark>
<mark>two = int(input("Enter the second number: "))</mark>
total = (one * one) + (two * two)
print(f"The sum of squares of {one} and {two} is {total}")
</code></pre>
</section>

<section>
    <pre><code style="font-size: 35px; line-height: 40px" class="language-python stretch">one = int(input("Enter the first number: "))
two = int(input("Enter the second number: "))
<mark>total = (one * one) + (two * two)</mark>
print(f"The sum of squares of {one} and {two} is {<mark>total</mark>}")
</code></pre>
</section>

<section>
    <pre><code style="font-size: 35px; line-height: 40px" class="language-python stretch">one = int(input("Enter the first number: "))
two = int(input("Enter the second number: "))
print(f"The sum of squares of {one} and {two} is
        {<mark>(one * one) + (two * two)</mark>}")
</code></pre>
</section>

<section>
    <h3>Style</h3>
    <ul>
        <li>More lines and variables?<br>Simpler?</li>
        <li>Fewer lines and variables?<br>More Complex?</li>
    </ul>
    <br><br>
    <h4>&nbsp;</h4>
</section>
<section>
    <h3>Style</h3>
    <ul>
        <li>More lines and variables?<br>Simpler?</li>
        <li>Fewer lines and variables?<br>More Complex?</li>
    </ul>
    <br><br>
    <h4>Focus on Readability!</h4>
</section>