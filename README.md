# learn-py
Some useful information related with Python.
## Overview
- [Data Type: List](#data-type-list)
- [Data Type: Tuple](#data-type-tuple)
- [Data Type: Dictionary](#data-type-dictionary)
- [Data Type: Set](#data-type-set)

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