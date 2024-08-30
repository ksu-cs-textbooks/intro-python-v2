---
type: "reveal"
hidden: true
---
<section>
    <h3>Testing</h3>
    <div style="float: right; width: 50%">
        <img class="stretch plain" width="100%" src="/intro-python/images/04/control.png">
    </div>
    <div style="float: left; width: 50%">
        <pre><code style="font-size: 32px; line-height: 40px" class="language-python stretch">x = int(input("Enter a number: "))
y = int(input("Enter a number: "))
if x + y > 10:
  print("Branch 1")
else:
  print("Branch 2")
if x - y > 10:
  print("Branch 3")
else:
  print("Branch 4")
</code></pre>
</div>
</section>
<section>
    <h3>x = 6 | y = 6</h3>
    <div style="float: right; width: 50%">
        <img class="stretch plain" width="100%" src="/intro-python/images/04/control.png">
    </div>
    <div style="float: left; width: 50%">
        <pre><code style="font-size: 32px; line-height: 40px" class="language-python stretch">x = int(input("Enter a number: "))
y = int(input("Enter a number: "))
if x + y > 10:
  <mark>print("Branch 1")</mark>
else:
  print("Branch 2")
if x - y > 10:
  print("Branch 3")
else:
  <mark>print("Branch 4")</mark>
</code></pre>
</div>
</section>
<section>
    <h3>x = 6 | y = -6</h3>
    <div style="float: right; width: 50%">
        <img class="stretch plain" width="100%" src="/intro-python/images/04/control.png">
    </div>
    <div style="float: left; width: 50%">
        <pre><code style="font-size: 32px; line-height: 40px" class="language-python stretch">x = int(input("Enter a number: "))
y = int(input("Enter a number: "))
if x + y > 10:
  print("Branch 1")
else:
  <mark>print("Branch 2")</mark>
if x - y > 10:
  <mark>print("Branch 3")</mark>
else:
  print("Branch 4")
</code></pre>
</div>
</section>
<section>
    <h3>Branch Coverage</h3>
    <ul>
        <li>x = 6 | y = 6 -> Branches 1 & 4</li>
        <li>x = 6 | y = -6 -> Branches 2 & 3</li>
    </ul>
</section>
<section>
    <h3>x = 12 | y = 0</h3>
    <div style="float: right; width: 50%">
        <img class="stretch plain" width="100%" src="/intro-python/images/04/control.png">
    </div>
    <div style="float: left; width: 50%">
        <pre><code style="font-size: 32px; line-height: 40px" class="language-python stretch">x = int(input("Enter a number: "))
y = int(input("Enter a number: "))
if x + y > 10:
  <mark>print("Branch 1")</mark>
else:
  print("Branch 2")
if x - y > 10:
  <mark>print("Branch 3")</mark>
else:
  print("Branch 4")
</code></pre>
</div>
</section>
<section>
    <h3>x = 4 | y = 4</h3>
    <div style="float: right; width: 50%">
        <img class="stretch plain" width="100%" src="/intro-python/images/04/control.png">
    </div>
    <div style="float: left; width: 50%">
        <pre><code style="font-size: 32px; line-height: 40px" class="language-python stretch">x = int(input("Enter a number: "))
y = int(input("Enter a number: "))
if x + y > 10:
  print("Branch 1")
else:
  <mark>print("Branch 2")</mark>
if x - y > 10:
  print("Branch 3")
else:
  <mark>print("Branch 4")</mark>
</code></pre>
</div>
</section>
<section>
    <h3>Path Coverage</h3>
    <ul>
        <li>x = 6 | y = 6 -> Branches 1 & 4</li>
        <li>x = 6 | y = -6 -> Branches 2 & 3</li>
        <li>x = 12 | y = 0 -> Branches 1 & 3</li>
        <li>x = 4 | y = 4 -> Branches 2 & 4</li>
    </ul>
</section>
<section>
    <h3>Edge Cases</h3>
    <div style="float: right; width: 50%">
        <img class="stretch plain" width="100%" src="/intro-python/images/04/control.png">
    </div>
    <div style="float: left; width: 50%">
        <pre><code style="font-size: 32px; line-height: 40px" class="language-python stretch">x = int(input("Enter a number: "))
y = int(input("Enter a number: "))
if <mark>x + y > 10</mark>:
  print("Branch 1")
else:
  print("Branch 2")
if <mark>x - y > 10</mark>:
  print("Branch 3")
else:
  print("Branch 4")
</code></pre>
</div>
</section>
<section>
    <h3>x = 10 | y = 0</h3>
    <div style="float: right; width: 50%">
        <img class="stretch plain" width="100%" src="/intro-python/images/04/control.png">
    </div>
    <div style="float: left; width: 50%">
        <pre><code style="font-size: 32px; line-height: 40px" class="language-python stretch">x = int(input("Enter a number: "))
y = int(input("Enter a number: "))
if x + y > 10:
  print("Branch 1")
else:
  <mark>print("Branch 2")</mark>
if x - y > 10:
  print("Branch 3")
else:
  <mark>print("Branch 4")</mark>
</code></pre>
</div>
</section>
<section>
    <h3>x = 11 | y = 0</h3>
    <div style="float: right; width: 50%">
        <img class="stretch plain" width="100%" src="/intro-python/images/04/control.png">
    </div>
    <div style="float: left; width: 50%">
        <pre><code style="font-size: 32px; line-height: 40px" class="language-python stretch">x = int(input("Enter a number: "))
y = int(input("Enter a number: "))
if x + y > 10:
  <mark>print("Branch 1")</mark>
else:
  print("Branch 2")
if x - y > 10:
  <mark>print("Branch 3")</mark>
else:
  print("Branch 4")
</code></pre>
</div>
</section>
<section>
    <h3>x = 9 | y = 0</h3>
    <div style="float: right; width: 50%">
        <img class="stretch plain" width="100%" src="/intro-python/images/04/control.png">
    </div>
    <div style="float: left; width: 50%">
        <pre><code style="font-size: 32px; line-height: 40px" class="language-python stretch">x = int(input("Enter a number: "))
y = int(input("Enter a number: "))
if x + y > 10:
  print("Branch 1")
else:
  <mark>print("Branch 2")</mark>
if x - y > 10:
  print("Branch 3")
else:
  <mark>print("Branch 4")</mark>
</code></pre>
</div>
</section>
<section>
    <h3>Path Coverage</h3>
    <ul>
        <li>x = 6 | y = 6 -> Branches 1 & 4</li>
        <li>x = 6 | y = -6 -> Branches 2 & 3</li>
        <li>x = 12 | y = 0 -> Branches 1 & 3</li>
        <li>x = 4 | y = 4 -> Branches 2 & 4</li>
    </ul>
    <h3>Edge Cases</h3>
    <ul>
        <li>x = 9 | y = 0 -> False</li>
        <li>x = 10 | y = 0 -> False</li>
        <li>x = 11 | y = 0 -> True</li>
    </ul>
</section>









<section>
    <h3>Testing</h3>
    <pre><code style="font-size: 35px; line-height: 45px" class="language-python stretch">a = int(input("Enter a number: "))
b = int(input("Enter a number: "))
if a // b >= 5:
		# Branch 1
		print(f"{b} goes into {a} at least 5 times")
else:
		# Branch 2
		print(f"{a} is less than 5 times {b}")
if a % b == 0:
		# Branch 3
		print(f"{b} evenly divides {a}")
else:
		# Branch 4
		print(f"{a} / {b} has a remainder")
</code></pre>
</section>
<section>
    <h3>a = 25 | b = 5</h3>
    <pre><code style="font-size: 35px; line-height: 45px" class="language-python stretch">a = int(input("Enter a number: "))
b = int(input("Enter a number: "))
if a // b >= 5:
		<mark># Branch 1</mark>
		print(f"{b} goes into {a} at least 5 times")
else:
		# Branch 2
		print(f"{a} is less than 5 times {b}")
if a % b == 0:
		<mark># Branch 3</mark>
		print(f"{b} evenly divides {a}")
else:
		# Branch 4
		print(f"{a} / {b} has a remainder")
</code></pre>
</section>
<section>
    <h3>a = 21 | b = 5</h3>
    <pre><code style="font-size: 35px; line-height: 45px" class="language-python stretch">a = int(input("Enter a number: "))
b = int(input("Enter a number: "))
if a // b >= 5:
		# Branch 1
		print(f"{b} goes into {a} at least 5 times")
else:
		<mark># Branch 2</mark>
		print(f"{a} is less than 5 times {b}")
if a % b == 0:
		# Branch 3
		print(f"{b} evenly divides {a}")
else:
		<mark># Branch 4</mark>
		print(f"{a} / {b} has a remainder")
</code></pre>
</section>
<section>
    <h3>Branch Coverage</h3>
    <ul>
        <li>a = 25 | b = 5 -> Branches 1 & 3</li>
        <li>a = 21 | b = 5 -> Branches 2 & 4</li>
    </ul>
</section>
<section>
    <h3>a = 31 | b = 5</h3>
    <pre><code style="font-size: 35px; line-height: 45px" class="language-python stretch">a = int(input("Enter a number: "))
b = int(input("Enter a number: "))
if a // b >= 5:
		<mark># Branch 1</mark>
		print(f"{b} goes into {a} at least 5 times")
else:
		# Branch 2
		print(f"{a} is less than 5 times {b}")
if a % b == 0:
		# Branch 3
		print(f"{b} evenly divides {a}")
else:
		<mark># Branch 4</mark>
		print(f"{a} / {b} has a remainder")
</code></pre>
</section>
<section>
    <h3>a = 20 | b = 5</h3>
    <pre><code style="font-size: 35px; line-height: 45px" class="language-python stretch">a = int(input("Enter a number: "))
b = int(input("Enter a number: "))
if a // b >= 5:
		# Branch 1
		print(f"{b} goes into {a} at least 5 times")
else:
		<mark># Branch 2</mark>
		print(f"{a} is less than 5 times {b}")
if a % b == 0:
		<mark># Branch 3</mark>
		print(f"{b} evenly divides {a}")
else:
		# Branch 4
		print(f"{a} / {b} has a remainder")
</code></pre>
</section>
<section>
    <h3>Path Coverage</h3>
    <ul>
        <li>a = 25 | b = 5 -> Branches 1 & 3</li>
        <li>a = 21 | b = 5 -> Branches 2 & 4</li>
        <li>a = 31 | b = 5 -> Branches 1 & 4</li>
        <li>a = 20 | b = 5 -> Branches 2 & 3</li>
    </ul>
</section>
<section>
    <h3>Edge Cases</h3>
    <pre><code style="font-size: 35px; line-height: 45px" class="language-python stretch">a = int(input("Enter a number: "))
b = int(input("Enter a number: "))
if <mark>a // b >= 5</mark>:
		# Branch 1
		print(f"{b} goes into {a} at least 5 times")
else:
		# Branch 2
		print(f"{a} is less than 5 times {b}")
if <mark>a % b == 0</mark>:
		# Branch 3
		print(f"{b} evenly divides {a}")
else:
		# Branch 4
		print(f"{a} / {b} has a remainder")
</code></pre>
</section>
<section>
    <h3>Path Coverage & Edge Cases</h3>
    <ul>
        <li>a = 25 | b = 5 -> Branches 1 & 3</li>
        <li>a = 21 | b = 5 -> Branches 2 & 4</li>
        <li>a = 31 | b = 5 -> Branches 1 & 4</li>
        <li>a = 20 | b = 5 -> Branches 2 & 3</li>
    </ul>
</section>