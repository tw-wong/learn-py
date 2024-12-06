# learn-py
Some useful information related with Python.
## Overview
- [Virtual Environment](#virtual-environment)
- [Package installer (pip)](#package-installer-pip)
- [Data Type: List](#data-type-list)
- [Data Type: Tuple](#data-type-tuple)
- [Data Type: Dictionary](#data-type-dictionary)
- [Data Type: Set](#data-type-set)
- [Functions](#functions)
- [Classes](#classes)

## Virtual Environment
```bash
# create virtual environment
python -m venv myenv

# activate virtual environment
source myenv/bin/activate

# deactivate virtual environment
deactivate
```

## Package installer (pip)
```bash
# install package pandas from PyPI
pip install pandas

# install multiple pacakges at once - pytest, sphinx and mypy
pip install pytest sphinx mypy

# install package with optionals
pip install "fastapi[all]"

# install specific version of requests package
install requests==2.26.0

# install from github repository (package must be installable)
pip install 'git+https://github.com/pydantic/pydantic'

# upgrade package
pip install --upgrade requests

# uninstall package
pip uninstall pandas

# list installed packages
pip list

# freeze requirements to file
pip freeze > requirements.txt

# install packages from requirements.txt
pip install -r requirements.txt
```

## Data Type: List
```python
# List example
fruits = ["apple", "banana", "cherry"]

# Adding elements
fruits.append("date")  # Add an item at the end
fruits.insert(1, "blueberry")  # Add at a specific position

# Removing elements
fruits.remove("cherry")  # Remove by value
last_fruit = fruits.pop()  # Remove and return the last item

# Accessing elements
print("First Fruit:", fruits[0])  # Indexing
print("All Fruits:", fruits)

# Output:
# First Fruit: apple
# All Fruits: ['apple', 'blueberry', 'banana']
```

## Data Type: Tuple
```python
# Tuple example
coordinates = (10.5, 20.3, 30.7)

# Accessing elements
print("First Coordinate:", coordinates[0])  # Indexing

# Unpacking
x, y, z = coordinates
print(f"x: {x}, y: {y}, z: {z}")

# Tuples are immutable
# coordinates[0] = 15  # This will raise an error!

# Output:
# First Coordinate: 10.5
# x: 10.5, y: 20.3, z: 30.7
```

## Data Type: Dictionary
Dictionaries store key-value pairs, allowing fast lookups by key.

```python
# Dictionary example
person = {
    "name": "Alice",
    "age": 25,
    "city": "New York"
}

# Accessing values
print("Name:", person["name"])

# Modifying values
person["age"] = 26

# Adding new key-value pairs
person["hobbies"] = ["reading", "gardening"]

# Iterating over a dictionary
for key, value in person.items():
    print(f"{key}: {value}")

# Output:
# Name: Alice
# name: Alice
# age: 26
# city: New York
# hobbies: ['reading', 'gardening']
```

## Data Type: Set
Sets are unordered collections (order may vary) of unique elements.

```python
# Set example
numbers = {1, 2, 3, 4, 5}

# Adding elements
numbers.add(6)

# Removing elements
numbers.remove(3)

# Set operations
even_numbers = {2, 4, 6, 8}
union_set = numbers.union(even_numbers)  # Union
intersection_set = numbers.intersection(even_numbers)  # Intersection

print("Numbers:", numbers)
print("Union:", union_set)
print("Intersection:", intersection_set)

# Output:
# Numbers: {1, 2, 4, 5, 6}
# Union: {1, 2, 4, 5, 6, 8}
# Intersection: {2, 4, 6}
```
Removing Duplicates:
```python
numbers = [1, 2, 2, 3, 4, 4, 5]
unique_numbers = set(numbers)
print("Unique Numbers:", unique_numbers)  # Output: {1, 2, 3, 4, 5}
```

## Functions
```python
def greet(name, greeting="Hello"):
    """
    This function greets a person with a specified greeting.
    :param name: str - The name of the person
    :param greeting: str - The greeting message (default is "Hello")
    :return: str - A greeting message
    """
    return f"{greeting}, {name}!"

# Function calls
print(greet("Alice"))  # Output: Hello, Alice!
print(greet("Bob", "Hi"))  # Output: Hi, Bob!
```

## Classes
```python
class Person:
    """
    A class to represent a person.
    """
    def __init__(self, name, age):
        """
        Constructor to initialize the person's name and age.
        :param name: str - The name of the person
        :param age: int - The age of the person
        """
        self.name = name
        self.age = age

    def greet(self):
        """
        Method to print a greeting message.
        """
        return f"Hello, my name is {self.name} and I am {self.age} years old."

# Create an instance of the Person class
person1 = Person("Alice", 25)

# Access attributes
print("Name:", person1.name) # Output: Name: Alice
print("Age:", person1.age) # Output: Age: 25

# Call the method
print(person1.greet()) # Output: Hello, my name is Alice and I am 25 years old.
```

Inheritance:
```python
class Worker(Person):
    def __init__(self, name, age, job):
        super().__init__(name, age)
        self.job = job

    def work(self):
        return f"{self.name} is working as a {self.job}."
```

Abstract Classes (interface):
```python
from abc import ABC, abstractmethod

# Define the interface using an abstract base class
class Shape(ABC):
    """
    Interface for shapes, requiring implementation of the area and perimeter methods.
    """
    
    @abstractmethod
    def area(self):
        pass  # Must be implemented in subclasses

    @abstractmethod
    def perimeter(self):
        pass  # Must be implemented in subclasses

# Implement the interface in a concrete class
class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def area(self):
        return self.width * self.height
    
    def perimeter(self):
        return 2 * (self.width + self.height)

# Implement the interface in another concrete class
class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return 3.14159 * self.radius * self.radius

    def perimeter(self):
        return 2 * 3.14159 * self.radius

# Using the classes
shapes = [
    Rectangle(5, 10),  # Output: Rectangle with width=5, height=10
    Circle(7)          # Output: Circle with radius=7
]

for shape in shapes:
    print(f"{shape.__class__.__name__}: Area = {shape.area()}, Perimeter = {shape.perimeter()}")

```