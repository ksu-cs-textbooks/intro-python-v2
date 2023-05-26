---
type: "reveal"
hidden: true
---

<section>
    <pre><code style="font-size: 45px; line-height: 50px" class="language-python stretch">x = int(input("Enter a number: "))
y = int(input("Enter a number: "))
i = 0
line = ""
while i < x + y:
    line = line + "*"
    print(line)
    i = i + 1
while i > x - y:
    print("=", end="")
    i = i - 1
print()
</code></pre>
</section>