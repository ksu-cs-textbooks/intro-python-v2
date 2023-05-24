---
type: "reveal"
hidden: true
---

<section>
    <h3>String Concatenation</h3>
    <pre><code style="font-size: 70px; line-height: 80px" class="language-python stretch">first = "Hello"
second = "World"
print(first + second)
</code></pre>
    <br>
    <pre><code style="font-size: 70px; line-height: 80px" class="language-plaintext"> 
</code></pre>
</section>
<section>
    <h3>String Concatenation</h3>
    <pre><code style="font-size: 70px; line-height: 80px" class="language-python stretch">first = "Hello"
second = "World"
print(first + second)
</code></pre>
    <br>
    <pre><code style="font-size: 70px; line-height: 80px" class="language-plaintext">Hello World
</code></pre>
</section>
<section>
    <h3>Concatenating Numbers</h3>
    <pre><code style="font-size: 70px; line-height: 80px" class="language-python stretch">text = "Your total is $"
value = 2.75
print(text + str(value))
</code></pre>
    <br>
    <pre><code style="font-size: 70px; line-height: 80px" class="language-plaintext"> 
</code></pre>
</section>
<section>
    <h3>Concatenating Numbers</h3>
    <pre><code style="font-size: 70px; line-height: 80px" class="language-python stretch">text = "Your total is $"
value = 2.75
print(text + str(value))
</code></pre>
    <br>
    <pre><code style="font-size: 70px; line-height: 80px" class="language-plaintext">Your total is $2.75
</code></pre>
</section>
<section>
    <h3>Concatenating Numbers</h3>
    <pre><code style="font-size: 70px; line-height: 80px" class="language-python stretch">text = "Your total is $"
value = 2.75
print(text + <mark>value</mark>)
</code></pre>
    <br>
    <pre><code style="font-size: 70px; line-height: 80px" class="language-plaintext"> 
</code></pre>
</section>
<section>
    <h3>Concatenating Numbers</h3>
    <pre><code style="font-size: 70px; line-height: 80px" class="language-python stretch">text = "Your total is $"
value = 2.75
print(text + <mark style="color:red">value</mark>)
</code></pre>
    <br>
    <pre><code style="font-size: 50px; line-height: 60px" class="language-plaintext">Traceback (most recent call last):
File "tutor.py", line 3, in &lt;module>
    print(text + value)
TypeError: must be str, not float
</code></pre>
</section>

<section>
    <h3>Repeat</h3>
    <pre><code style="font-size: 70px; line-height: 80px" class="language-python stretch">word = "repeat"
print(word * 2)
print(word * 4)
</code></pre>
    <br>
    <pre><code style="font-size: 70px; line-height: 80px" class="language-plaintext"><br>
</code></pre>
</section>

<section>
    <h3>Repeat</h3>
    <pre><code style="font-size: 70px; line-height: 80px" class="language-python stretch">word = "repeat"
print(word * 2)
print(word * 4)
</code></pre>
    <br>
    <pre><code style="font-size: 70px; line-height: 80px" class="language-plaintext">repeatrepeat
repeatrepeatrepeatrepeat
</code></pre>
</section>

<section>
    <h3>Escape</h3>
    <pre><code style="font-size: 50px; line-height: 55px" class="language-python stretch">sentence = "Hello from "the little apple!""
print(sentence)
</code></pre>
    <br>
    <pre><code style="font-size: 50px; line-height: 55px" class="language-plaintext"><br><br><br>
</code></pre>
</section>

<section>
    <h3>Escape</h3>
    <pre><code style="font-size: 50px; line-height: 55px" class="language-python stretch">sentence = "Hello from "the little apple!""
print(sentence)
</code></pre>
    <br>
    <pre><code style="font-size: 50px; line-height: 55px" class="language-plaintext">File test.py, line 1
  sentence = "Hello from "the little apple!""
                          ^
SyntaxError: invalid syntax
</code></pre>
</section>

<section>
    <h3>Escape</h3>
    <pre><code style="font-size: 50px; line-height: 55px" class="language-python stretch">sentence = "Hello from \"the little apple!\""
print(sentence)
</code></pre>
    <br>
    <pre><code style="font-size: 50px; line-height: 55px" class="language-plaintext">
</code></pre>
</section>

<section>
    <h3>Escape</h3>
    <pre><code style="font-size: 50px; line-height: 55px" class="language-python stretch">sentence = "Hello from \"the little apple!\""
print(sentence)
</code></pre>
    <br>
    <pre><code style="font-size: 50px; line-height: 55px" class="language-plaintext">Hello from "the little apple!"
</code></pre>
</section>

<section>
    <h3>Single & Double Quotes</h3>
    <pre><code style="font-size: 50px; line-height: 55px" class="language-python stretch">sentence = 'Hello from "the little apple!"'
print(sentence)
</code></pre>
    <br>
    <pre><code style="font-size: 50px; line-height: 55px" class="language-plaintext">Hello from "the little apple!"
</code></pre>
</section>