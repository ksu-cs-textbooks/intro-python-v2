---
type: "reveal"
hidden: true
---

<section>
    <h3>F-Strings</h3>
    <pre><code style="font-size: 70px; line-height: 80px" class="language-python stretch">name = input("Enter your name: ")
print(f"Hello {name}")
</code></pre>
    <br>
    <pre><code style="font-size: 70px; line-height: 80px" class="language-plaintext"><br>
</code></pre>
</section>
<section>
    <h3>F-Strings</h3>
    <pre><code style="font-size: 70px; line-height: 80px" class="language-python stretch">name = input("Enter your name: ")
print(f"Hello {name}")
</code></pre>
    <br>
    <pre><code style="font-size: 70px; line-height: 80px" class="language-plaintext">Enter your name: <mark> </mark><br>
</code></pre>
</section>
<section>
    <h3>F-Strings</h3>
    <pre><code style="font-size: 70px; line-height: 80px" class="language-python stretch">name = input("Enter your name: ")
print(f"Hello {name}")
</code></pre>
    <br>
    <pre><code style="font-size: 70px; line-height: 80px" class="language-plaintext">Enter your name: <mark>Willie Wildcat</mark><br>
</code></pre>
</section>
<section>
    <h3>F-Strings</h3>
    <pre><code style="font-size: 70px; line-height: 80px" class="language-python stretch">name = input("Enter your name: ")
print(f"Hello {name}")
</code></pre>
    <br>
    <pre><code style="font-size: 70px; line-height: 80px" class="language-plaintext">Enter your name: <mark>Willie Wildcat</mark>
Hello Willie Wildcat
</code></pre>
</section>
<section>
    <h3>F-Strings</h3>
    <pre><code style="font-size: 70px; line-height: 80px" class="language-python stretch">name = input("Enter your name: ")
print(f<mark>"Hello {name}"</mark>)
</code></pre>
    <br>
    <pre><code style="font-size: 70px; line-height: 80px" class="language-plaintext">Enter your name: <mark>Willie Wildcat</mark>
Hello Willie Wildcat
</code></pre>
</section>
<section>
    <h3>F-Strings</h3>
    <pre><code style="font-size: 70px; line-height: 80px" class="language-python stretch">name = input("Enter your name: ")
print(f"Hello <mark>{name}</mark>")
</code></pre>
    <br>
    <pre><code style="font-size: 70px; line-height: 80px" class="language-plaintext">Enter your name: <mark>Willie Wildcat</mark>
Hello Willie Wildcat
</code></pre>
</section>
<section>
    <h3>F-Strings</h3>
    <pre><code style="font-size: 70px; line-height: 80px" class="language-python stretch">name = input("Enter your name: ")
print(<mark>f</mark>"Hello {name}")
</code></pre>
    <br>
    <pre><code style="font-size: 70px; line-height: 80px" class="language-plaintext">Enter your name: <mark>Willie Wildcat</mark>
Hello Willie Wildcat
</code></pre>
</section>
<section>
    <h3>F-Strings</h3>
    <pre><code style="font-size: 70px; line-height: 80px" class="language-python stretch">name = input("Enter your name: ")
print(f"Hello {<mark>name</mark>}")
</code></pre>
    <br>
    <pre><code style="font-size: 70px; line-height: 80px" class="language-plaintext">Enter your name: <mark>Willie Wildcat</mark>
Hello Willie Wildcat
</code></pre>
</section>
<section>
    <h3>F-Strings</h3>
    <pre><code style="font-size: 32px; line-height: 40px" class="language-python stretch">text_one = input("Enter the price of one item: ")
price = float(text_one)
text_two = input("Enter the quantity of items: ")
quantity = int(text_two)
cost = price * quantity
print(f"{quantity} items at ${price} each is ${cost} total")
</code></pre>
    <br>
    <pre><code style="font-size: 40px; line-height: 50px" class="language-plaintext"><br><br>
</code></pre>
</section>
<section>
    <h3>F-Strings</h3>
    <pre><code style="font-size: 32px; line-height: 40px" class="language-python stretch">text_one = input("Enter the price of one item: ")
price = float(text_one)
text_two = input("Enter the quantity of items: ")
quantity = int(text_two)
cost = price * quantity
print(f"{quantity} items at ${price} each is ${cost} total")
</code></pre>
    <br>
    <pre><code style="font-size: 40px; line-height: 50px" class="language-plaintext">Enter the price of one item: <mark>2.75</mark>
Enter the quantity of items: <mark>3</mark>
3 items at $2.75 each is $8.25 total
</code></pre>
</section>
