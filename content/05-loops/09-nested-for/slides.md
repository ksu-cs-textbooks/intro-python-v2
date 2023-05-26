---
type: "reveal"
hidden: true
---

<section>
    <pre><code style="font-size: 45px; line-height: 50px" class="language-python stretch">for i in range(3):
    for j in range(5):
        print("* ", end="")
    print("")
</code></pre>
<br>
    <pre class="fragment"><code class="language-plaintext">* * * * * 
* * * * * 
* * * * *</code></pre>
</section>

<section>
    <pre><code style="font-size: 45px; line-height: 50px" class="language-python stretch">for i in range(5):
    for j in range(i + 1):
        print("* ", end="")
    print("")
</code></pre>
<br>
    <pre class="fragment"><code class="language-plaintext">* 
* * 
* * * 
* * * * 
* * * * * </code></pre>
</section>

<section>
    <pre><code style="font-size: 45px; line-height: 50px" class="language-python stretch">for i in range(5):
    for j in range(4 - i):
        print("  ", end="")
    for j in range(i + 1):
        print("* ", end="")
    print("")
</code></pre>
<br>
    <pre class="fragment"><code class="language-plaintext">        * 
      * * 
    * * * 
  * * * * 
* * * * * </code></pre>
</section>

<section>
    <pre><code style="font-size: 45px; line-height: 50px" class="language-python stretch">total = 0
count = 0
for i in range(10):
    for j in range(i + 1):
        total = total + (i * j)
        count += 1
print(f"sum: {total}, count: {count}")
</code></pre>
<br>
    <pre class="fragment"><code style="font-size: 45px; line-height: 50px" class="language-python stretch">for i in range(5):
    for j in range(i + 1):
        print("* ", end="")
    print("")
</code></pre>

<img class="fragment plain" src="/images/05/output.png">

</section>

