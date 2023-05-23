---
type: "reveal"
hidden: true
---

<section>
    <h3>Order of Operations</h3>
    <ol>
        <li>Parentheses</li>
        <li>Exponentiation</li>
        <li>Multiplication, Division,<br>Integer Division, Modulo</li>
        <li>Addition, Subtraction</li>
    </ol>
</section>

<section>
    <pre><code style="font-size:60px; line-height: 70px" class="language-pythonstretch">x = 8 / 4 + 5 * (3 + 1) - 7 % 4
<br><br><br></code></pre>
</section>
<section>
    <pre><code style="font-size:60px; line-height: 70px" class="language-pythonstretch">x = 8 / 4 + 5 * <mark>(3 + 1)</mark> - 7 % 4
<br><br><br></code></pre>
</section>
<section>
    <pre><code style="font-size:60px; line-height: 70px" class="language-pythonstretch">x = 8 / 4 + 5 * (3 + 1) - 7 % 4
x = 8 / 4 + 5 *    4    - 7 % 4<br><br><br></code></pre>
</section>
<section>
    <pre><code style="font-size:60px; line-height: 70px" class="language-pythonstretch">x = 8 / 4 + 5 * (3 + 1) - 7 % 4
x = <mark>8 / 4</mark> + <mark>5 *    4</mark>    - <mark>7 % 4</mark><br><br><br></code></pre>
</section>
<section>
    <pre><code style="font-size:60px; line-height: 70px" class="language-pythonstretch">x = 8 / 4 + 5 * (3 + 1) - 7 % 4
x = 8 / 4 + 5 *    4    - 7 % 4
x =  2.0  +    20       -    3<br><br></code></pre>
</section>
<section>
    <pre><code style="font-size:60px; line-height: 70px" class="language-pythonstretch">x = 8 / 4 + 5 * (3 + 1) - 7 % 4
x = 8 / 4 + 5 *    4    - 7 % 4
x =  <mark>2.0  +    20       -    3</mark><br><br></code></pre>
</section>
<section>
    <pre><code style="font-size:60px; line-height: 70px" class="language-pythonstretch">x = 8 / 4 + 5 * (3 + 1) - 7 % 4
x = 8 / 4 + 5 *    4    - 7 % 4
x =  2.0  +    20       -    3
x = 19.0</code></pre>
</section>