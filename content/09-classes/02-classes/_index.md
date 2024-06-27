---
title: "Classes"
pre: "2. "
weight: 20
---

{{< youtube noid  >}}

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

First, let's look at how we can create our own classes in Python. A **class** is a special construct in programming that forms the blueprint for something that represents a some sort of object, such as real-world objects like a person, car, or even abstract objects such as a user interface in a video game. Classes contain two different types of content, the **attributes**, or variables, that store data related to the class, and the **methods**, or functions, that describe the behavior of the class. 

Let's look at a short example to see how we can build a class that represents a person in Python.

```python
class Person:


    # class variables
    can_drive = true


    # constructor
    def __init__(self, given_name, surname, age):
        # instance variables
        self.given_name = given_name
        self.surname = surname
        self.age = age
    

    # method
    def birthday(self):
        self.age = self.age + 1
    

    # method
    def full_name(self):
        return f"{self.given_name} {self.surname}"
    

    # string method
    def __str__(self):
        return f"{self.full_name()} ({self.age})"
```

There is a lot of new code here that we have not seen before, but we'll go through each part separately and discuss what it means.

## Class Definition

At the top of the class, we see this line:

```python
class Person:
```

Just like a function, a class is defined with the special `class` keyword, followed by the name of the class. Class names also follow the same rules as any other variable name in Python, and typically we capitalize the names of Classes 