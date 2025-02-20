Below is the combined, well‐formatted markdown file that includes all topics and examples from both files. Feel free to extend or modify any examples as needed!

---

# Python Learning Notes (From Basics to Advanced)

This document covers Python from the basics to advanced topics, complete with one‐liner definitions, detailed examples, and best practices.

---

# 1. Python Basics

### 1.1 Printing & Memory Check
- **Definition:** Print statements display output and the built-in `id()` returns the memory address of an object.
- **Example:**
  ```python
  name = "taha"
  print(id(name))  # Output: Memory address of the variable 'name'
  ```

### 1.2 Comments
- **Single-line comment:**  
  ```python
  # This is a single-line comment
  ```
- **Multi-line comment:**  
  ```python
  """
  This is a multi-line comment.
  It can span multiple lines.
  """
  ```

### 1.3 Data Types & Variables
- **Definition:** Variables store data values; Python supports several built-in types.
- **Common Types:** `int`, `float`, `str`, `bool`, `list`, `tuple`, `set`, `dict`
- **Type Hints & Naming Conventions (PEP-8, snake_case):**
  ```python
  name: str = "Taha"
  age: int = 28
  height: float = 5.9
  is_student: bool = True
  ```
  
### 1.4 Operators
- **Arithmetic:** `+`, `-`, `*`, `/`, `**` (exponent), `//` (floor division), `%` (modulus)
- **Comparison:** `==`, `!=`, `>`, `<`, `>=`, `<=`
- **Logical:** `and`, `or`, `not`
- **Membership:** `in`, `not in`
- **Identity:** `is`, `is not`
- **Example:**
  ```python
  a, b = 5, 10
  print(a ** 2)        # Output: 25 (Exponentiation)
  print(b // a)        # Output: 2  (Floor division)
  print(a < b and a != b)  # Output: True
  ```

### 1.5 Input from User
- **Example:**
  ```python
  name = input("Enter your name: ")
  print(f"Hello, {name}")
  ```

---

# 2. Strings & String Methods

- **Definition:** A string is a sequence of characters enclosed in quotes.
- **Common Methods:**  
  `.lower()`, `.upper()`, `.capitalize()`, `.title()`, `.strip()`, `.index()`, `.count()`, `.replace()`, `.split()`, `.join()`, `.isalnum()`
- **Examples:**
  ```python
  text = "Hello World"
  print(text.upper())                    # Output: HELLO WORLD
  print(text.replace("World", "Python")) # Output: Hello Python
  
  # Using f-strings and checking length
  name = "taha"
  print(f"Hello, {name}")  # Output: Hello, taha
  print(len(name))         # Output: 4
  
  # Rounding a float
  value = 10.5678
  print(round(value, 2))   # Output: 10.57
  ```

---

# 3. Lists (Dynamic Arrays)

- **Definition:** A list is an ordered, mutable collection of items.
- **Common Operations & Methods:**
  - **Creation & Access:**
    ```python
    my_list = [1, 2, 3]
    print(my_list[0])  # Output: 1
    ```
  - **Modifying Lists:**
    ```python
    fruits = ["apple", "banana", "cherry"]
    fruits.append("orange")   # Add element at the end
    fruits.insert(1, "mango") # Insert at a specific index
    fruits.extend(["kiwi", "grape"])  # Merge lists
    fruits.pop()              # Remove last element
    fruits.pop(1)             # Remove element at index 1
    fruits.remove("apple")    # Remove by value
    fruits.sort()             # Sort list
    fruits.reverse()          # Reverse list
    print(fruits)
    ```
  - **Other Methods:** `.count(value)`, `.clear()`, `.copy()`, slicing (`list[start:end]`), and repeating elements (`[value] * number`)

---

# 4. Loops

### 4.1 For Loop
- **Definition:** Iterates over items of a sequence.
- **Example:**
  ```python
  my_list = [1, 2, 3, 4, 5]
  for item in my_list:
      print(item)
  
  # Using enumerate to get index and value
  for index, value in enumerate(my_list):
      print(f"Index {index}: {value}")
  ```

### 4.2 While Loop
- **Definition:** Repeats as long as a condition is true.
- **Example:**
  ```python
  count = 1
  while count <= 5:
      print(count)
      count += 1
  ```

### 4.3 Else with Loops
- **Definition:** The `else` block executes if the loop completes normally (without a `break`).
- **Example:**
  ```python
  for i in range(3):
      print(i)
  else:
      print("Loop completed")
  ```

---

# 5. Tuple (Immutable List)

- **Definition:** A tuple is an ordered, immutable sequence of values.
- **Example:**
  ```python
  names: tuple[str, str, str] = ("Taha", "Ahmed", "Alex")
  print(names[0])  # Output: Taha
  # Tuples support slicing like lists.
  print(names[0:2]) # Output: ("Taha", "Ahmed")
  ```


A tuple is an **immutable** sequence, meaning you cannot change its content after creation. Because of its immutability, tuples have only a couple of built-in methods:

- **`index(value)`**  
  Returns the first index of the specified value.
- **`count(value)`**  
  Returns the number of times a specified value appears in the tuple.

### Accessing Tuple Values

Since tuples are ordered, you can access values using **indexing** or **slicing**:

```python
# Creating a tuple
my_tuple = (10, 20, 30, 40, 30)

# Accessing values using indexing
print(my_tuple[2])  # Output: 30

# Using the index() method to find the first occurrence of a value
first_index = my_tuple.index(30)
print(first_index)  # Output: 2

# Counting the occurrence of a value
count_30 = my_tuple.count(30)
print(count_30)  # Output: 2

# Slicing a tuple
print(my_tuple[1:4])  # Output: (20, 30, 40)
```

---

# 6. Set (Unique Unordered Collection)

- **Definition:** A set is an unordered collection of unique items.
- **Example:**
  ```python
  my_set: set[str] = {"a", "b", "c", "a"}
  print(my_set)  # Output: {'a', 'b', 'c'} (duplicates removed)
  
  # Common methods:
  my_set.add("d")
  my_set.remove("b")
  print(my_set)
  ```

A set is an **unordered** collection of unique elements. Because it is unordered, you **cannot access elements via indexing**. Instead, you iterate over the set or use membership tests.

### Common Set Methods

- **`add(element)`**  
  Adds an element to the set.
- **`remove(element)`**  
  Removes the specified element. Raises a `KeyError` if the element is not present.
- **`discard(element)`**  
  Removes the specified element if it exists. Unlike `remove()`, it does not raise an error if the element is missing.
- **`pop()`**  
  Removes and returns an arbitrary element from the set.
- **`clear()`**  
  Removes all elements from the set.
- **`update(other_set)`**  
  Adds elements from another set (or any iterable) to the set.
- **`union(other_set)`**, **`intersection(other_set)`**, **`difference(other_set)`**, and **`symmetric_difference(other_set)`**  
  Return new sets based on set operations.

### Accessing Set Values

Since sets do not support indexing, you typically iterate over them:

```python
# Creating a set
my_set = {1, 2, 3, 4, 5}

# Iterating over a set to access its values
for value in my_set:
    print(value)

# Adding an element
my_set.add(6)
print(my_set)  # Output will include 6 (order is not guaranteed)

# Removing an element using remove() and discard()
my_set.remove(2)  # Raises KeyError if 2 is not present
my_set.discard(3) # Does nothing if 3 is not present

# Popping an element (removes and returns an arbitrary element)
popped_value = my_set.pop()
print(f"Popped: {popped_value}")
print(my_set)
```

Yes, because sets are **unordered collections**, they don’t support direct indexing like lists. However, sets have **specific use cases** where they are extremely useful:

---

#### ✅ **Why Use Sets in Python?**
1. **Uniqueness Guarantee (No Duplicates)**
   - If you need to store unique values and automatically remove duplicates, sets are perfect.
   ```python
   my_set = {1, 2, 3, 3, 4}
   print(my_set)  # Output: {1, 2, 3, 4} (Duplicates are removed)
   ```

2. **Fast Membership Checking (`O(1)` Complexity)**
   - Checking if an element exists in a set is much **faster than lists** because sets use **hashing**.
   ```python
   my_set = {"apple", "banana", "cherry"}
   print("banana" in my_set)  # Output: True (Fast lookup)
   ```
## **Why Do Lists and Sets Have Different Searching Times?**
The key reason lists and sets have different searching times is their underlying data structures.

## **1. Lists (`list`)**  
- Lists are implemented as **dynamic arrays**.
- Searching for an element requires checking each item one by one (**linear search**), making the time complexity **O(n)** in the worst case.

## **2. Sets (`set`)**  
- Sets use a **hash table** (unordered collection).
- When searching for an element, Python computes its **hash value** and looks it up in constant time, making the average time complexity **O(1)**.
- However, in the worst case (when many elements collide in the same hash bucket), lookup time can degrade to **O(n)**.

---

## **What is Hashing?**
Hashing is a technique used to map data (like strings or numbers) to a fixed-size value called a **hash code** or **hash value** using a **hash function**.

## **Understanding Hashing with an Example**
Imagine you are storing names in a dictionary. Instead of searching through the entire list, a **hash function** converts each name into a unique index:

| Name       | Hash Value (Index) |
|------------|------------------|
| "Alice"    | 102              |
| "Bob"      | 215              |
| "Charlie"  | 178              |

When searching for "Charlie," instead of checking each name one by one, the system directly jumps to index **178**, making it much faster.

---

## **What is Non-Hashing?**
Non-hashing refers to data structures that do not use hash functions for lookup, such as:
- **Lists (`list`)** → Use linear search (**O(n)**)

---

## **Key Takeaways**
- **Hashing is fast** but requires extra memory.
- **Lists (non-hashing) are slower** but maintain order.
- If you need **fast lookups**, use a **set** or **dictionary (`dict`)**.
- If **order matters**, use a **list** or **tree-based structures**.

---

## **What is a Bucket?**
A **bucket** is a storage location inside a **hash table** where multiple values can be stored if they share the same **hash code**.

- When inserting a value in a set or dictionary, Python computes a **hash value** using the built-in `hash()` function.
- This **hash value** determines which **bucket** the value will go into.
- Because hash values are mapped to a **limited number of buckets**, multiple values may end up in the same bucket, causing a **hash collision**.

---

## **How Do Multiple Values Share the Same Hash Code?**
Since the number of possible hash values is large but not infinite, and the number of buckets is fixed, **different values can sometimes get the same hash value modulo the number of buckets**.

## **Example of Hash Collisions**
Let's say our hash function maps values to only **5 buckets**:

| Value    | Hash Code | Bucket (Hash Code % 5) |
|----------|----------|----------------------|
| "Alice"  | 102      | 102 % 5 = **2** |
| "Charlie"| 178      | 178 % 5 = **3** |
| "Eve"    | 157      | 157 % 5 = **2** |
| "Tom"    | 45       | 45 % 5 = **0** |

- Here, **"Alice"** and **"Eve"** both go into **bucket 2**, creating a **hash collision**.

---

## **How Does Python Handle Hash Collisions?**
Python resolves hash collisions using **chaining** (linked lists inside buckets):

1. Each bucket starts as **empty**.
2. When inserting an item:
   - If the bucket is empty, the item is placed directly.
   - If the bucket is already occupied (**collision**), Python stores the new value in a **linked list** at that bucket.
3. When searching for an item:
   - Python computes the **hash value** and finds the correct bucket.
   - If multiple values are in the same bucket, it **checks each one sequentially** inside the bucket.

---

## **Example of Hash Table with Buckets**
Imagine we have **3 buckets**, and we insert three names:

| Name     | Hash Code | Bucket (Hash Code % 3) |
|----------|----------|----------------------|
| "Alice"  | 102      | 102 % 3 = **0** |
| "Bob"    | 205      | 205 % 3 = **2** |
| "Charlie"| 306      | 306 % 3 = **0** |

Now, **bucket 0** contains both "Alice" and "Charlie":

```plaintext
Bucket 0 → ["Alice", "Charlie"]
Bucket 1 → []
Bucket 2 → ["Bob"]
```

If we search for "Charlie":
1. Compute the hash (`306`).
2. Find bucket `0`.
3. Check each item in the bucket to find "Charlie".

---

## **Why Don't We Always Get Collisions?**
Python's hash table is **optimized**:
- It dynamically **resizes** when too many elements are added.
- It increases the number of **buckets**, reducing collisions.
- It uses a **prime number of buckets** for better distribution.

---

## **Key Takeaways**
✔ **Buckets** store values based on their hash codes.  
✔ **Hash collisions** happen when multiple values share the same bucket.  
✔ Python resolves collisions using **chaining** (linked lists inside buckets).  
✔ The more buckets available, the fewer collisions occur.  

Would you like me to show a Python example of how a simple hash table with buckets works?




3. **Set Operations (Union, Intersection, Difference)**
   - Sets allow powerful mathematical operations:
   ```python
   set1 = {1, 2, 3}
   set2 = {3, 4, 5}
   print(set1 | set2)  # Union → {1, 2, 3, 4, 5}
   print(set1 & set2)  # Intersection → {3}
   print(set1 - set2)  # Difference → {1, 2}
   ```

4. **Eliminating Duplicates from a List**
   - If you have a list with duplicates, you can convert it into a set to remove them:
   ```python
   my_list = [1, 2, 2, 3, 4, 4, 5]
   unique_values = set(my_list)
   print(unique_values)  # Output: {1, 2, 3, 4, 5}
   ```

5. **Efficient Data Storage When Order Doesn’t Matter**
   - If you don’t need ordering but require **fast lookups and uniqueness**, sets are ideal.

---

### ❌ **When NOT to Use Sets**
- **If you need to keep elements in order**, use a `list`.
- **If you need indexed access**, use a `list` or `tuple`.

---

### 🔥 **Key Takeaway**
Use a `set` when:
- You need **unique values**.
- You want **fast lookups**.
- You need **set operations** (union, intersection, difference).

---

# 7. Dictionary (Key-Value Pairs)

- **Definition:** A dictionary stores data in key-value pairs.
- **Examples:**
  ```python
  # Creation and basic operations
  my_dict: dict[str, any] = {"name": "Taha", "age": 28}
  print(my_dict["name"])  # Access: Output -> Taha
  
  my_dict["name"] = "Ahmed"  # Modify
  my_dict["city"] = "Cairo"  # Add new key-value pair
  
  # Deletion
  del my_dict["age"]
  # or using pop:
  my_dict.pop("city", None)
  
  # Safe access using get()
  print(my_dict.get("name", "Default Name"))
  
  # Iterating over keys, values, and items
  for key, value in my_dict.items():
      print(f"{key}: {value}")
  ```

The line:

```python
print(my_dict.get("name", "Default Name"))
```

is using the **`.get()` method** of a dictionary to **safely retrieve** the value of the `"name"` key.

---

#### ✅ **Why Use `.get()` Instead of `my_dict["name"]`?**
If the key **exists**, `.get()` returns its value:
```python
my_dict = {"name": "Taha", "age": 28}
print(my_dict.get("name", "Default Name"))  # Output: Taha
```

If the key **does not exist**, `.get()` **does not raise an error** (unlike `my_dict["key"]`); instead, it returns the **default value**:
```python
my_dict = {"age": 28}
print(my_dict.get("name", "Default Name"))  # Output: Default Name
```

---

### ❌ **If You Use `my_dict["name"]` Without `.get()`**
If the key **does not exist**, Python will throw a `KeyError`:
```python
my_dict = {"age": 28}
print(my_dict["name"])  # ❌ KeyError: 'name'
```

---

### 🔥 **Key Takeaway**
Use `.get(key, default_value)` when:
- You want to avoid **errors** if the key is missing.
- You need a **default fallback value** when the key is not found.

---

# 8. Comprehensions

- **Definition:** A concise way to create lists, sets, or dictionaries.
  
### 8.1 List Comprehension
- **Example:**
  ```python
  squared = [x**2 for x in range(10)]
  print(squared)
  ```
  

### **Example Use Cases:**
#### ✅ Common Use Case 1: Squaring Numbers
```python
squared = [x**2 for x in range(10)]
```

#### ✅ Common Use Case 2: Filtering Even Numbers
```python
even_numbers = [x for x in range(20) if x % 2 == 0]
```
**Output:** `[0, 2, 4, 6, 8, 10, 12, 14, 16, 18]`

#### ✅ Common Use Case 3: Converting Strings to Uppercase
```python
words = ["hello", "world", "python"]
uppercase_words = [word.upper() for word in words]
```
**Output:** `['HELLO', 'WORLD', 'PYTHON']`

---

### **Conclusion**
🔹 **Yes**, list comprehensions are frequently used in Python because they are fast, concise, and readable.  
🔹 However, avoid using them when the logic is too complex, as it can reduce readability. 
  

### 8.2 Set & Dictionary Comprehension
- **Examples:**
  ```python
  unique_nums = {x for x in range(10)}
  print(unique_nums)
  
  squared_dict = {x: x**2 for x in range(5)}
  print(squared_dict)
  ```
### **Example Use Cases:**

#### **1️⃣ Set Comprehension Example: Unique Values**
A **set comprehension** is useful when you need a **collection of unique values**.

```python
unique_nums = {x for x in range(10)}
print(unique_nums)
```
🔹 **Use Case:** Removing duplicates from a list.

```python
numbers = [1, 2, 3, 4, 5, 5, 6, 6, 7]
unique_numbers = {x for x in numbers}  
print(unique_numbers)  
```
**Output:** `{1, 2, 3, 4, 5, 6, 7}`  

✅ **Why use set comprehension?**  
- Removes duplicate values automatically.  
- Faster than converting a list to a set manually.

---

#### **2️⃣ Dictionary Comprehension Example: Mapping Values**
A **dictionary comprehension** is useful when you need to create a key-value mapping.

```python
squared_dict = {x: x**2 for x in range(5)}
print(squared_dict)
```
**Output:** `{0: 0, 1: 1, 2: 4, 3: 9, 4: 16}`

🔹 **Use Case:** Counting word frequency in a sentence.

```python
sentence = "hello world hello python"
word_count = {word: sentence.split().count(word) for word in sentence.split()}
print(word_count)
```
**Output:** `{'hello': 2, 'world': 1, 'python': 1}`

✅ **Why use dictionary comprehension?**  
- Makes key-value pairs efficiently.  
- Useful for transforming or filtering data.

---

### **When to Use These?**
✔ **Set Comprehension:** When you need unique values.  
✔ **Dictionary Comprehension:** When you need to create mappings efficiently.  

---

# 9. Lambda, Map, Filter, Reduce

### 9.1 Lambda (Anonymous Function)
- **Definition:** A small anonymous function defined with the `lambda` keyword.
- **Example:**
  ```python
  add = lambda a, b: a + b
  print(add(2, 3))  # Output: 5
  ```

### 9.2 Map (Apply Function to Iterable)
- **Example:**
  ```python
  numbers = [1, 2, 3, 4]
  squared = list(map(lambda x: x ** 2, numbers))
  print(squared)  # Output: [1, 4, 9, 16]
  ```

### 9.3 Filter (Filter Values)
- **Example:**
  ```python
  even_numbers = list(filter(lambda x: x % 2 == 0, numbers))
  print(even_numbers)  # Output: [2, 4]
  ```

### 9.4 Reduce (Reduce Iterable to Single Value)
- **Example:**
  ```python
  from functools import reduce
  result = reduce(lambda x, y: x + y, numbers)
  print(result)  # Output: 10
  ```

---

# 10. Functions

- **Definition:** A block of reusable code that performs a specific task.
- **Example:**
  ```python
  def greet(name: str) -> str:
      return f"Hello, {name}"
  
  # Calling the function
  print(greet("Taha"))  # Output: Hello, Taha
  
  # Different types of arguments:
  def func(pos1, pos2, *args, **kwargs):
      print(pos1, pos2)
      print(args)
      print(kwargs)
  
  func("first", "second", "extra1", "extra2", key1="value1", key2="value2")
  ```

  Here's a concise example demonstrating all parameter types:

  ```python
  def demo(a, b, *args, greeting="Hello", **kwargs):
      print("Positional:", a, b)         # Required positional arguments
      print("Extra positional:", args)   # Additional positional arguments (*args)
      print("Greeting:", greeting)         # Keyword argument with a default value
      print("Extra keyword:", kwargs)      # Additional keyword arguments (**kwargs)
  
  # Use case: mixing different argument types
  demo(10, 20, 30, 40, greeting="Hi", extra="value")
  ```
  
  **Output:**
  ```
  Positional: 10 20
  Extra positional: (30, 40)
  Greeting: Hi
  Extra keyword: {'extra': 'value'}
  ```
  
  - **`a, b`**: Required positional arguments.
  - **`*args`**: Captures extra positional arguments.
  - **`greeting`**: A keyword parameter with a default value.
  - **`**kwargs`**: Captures extra keyword arguments.
  
  This pattern is useful when you need flexibility in the number and type of arguments your function accepts.

---

# 11. Modules & Imports

- **Definition:** Modules allow you to organize and reuse code across multiple files.
- **Examples:**
  ```python
  # Importing a module
  import math
  print(math.sqrt(25))  # Output: 5.0
  
  # Importing specific functions or using aliases
  from math import pow
  print(pow(2, 3))  # Output: 8
  
  import datetime as dt
  print(dt.datetime.now())
  ```

---

# 12. Error/Exception Handling

- **Definition:** Handling errors gracefully using try-except blocks.
- **Examples:**
  ```python
  try:
      # Code that may raise an exception
      result = 10 / 0
  except ZeroDivisionError:
      print("Cannot divide by zero")
  except Exception as e:
      print(f"An error occurred: {e}")
  else:
      print("No errors occurred")
  finally:
      print("This block always executes")
  ```
  Below is a concise example demonstrating several common error types using a single function. Each branch of the function intentionally triggers a different exception:
  
  ```python
  def error_examples(choice: int):
      try:
          if choice == 1:
              # ZeroDivisionError: dividing by zero
              result = 10 / 0
          elif choice == 2:
              # IndexError: accessing an out-of-range list index
              lst = [1, 2, 3]
              result = lst[5]
          elif choice == 3:
              # KeyError: accessing a non-existent dictionary key
              dct = {"a": 1, "b": 2}
              result = dct["c"]
          elif choice == 4:
              # ValueError: invalid conversion (string to integer)
              result = int("not a number")
          elif choice == 5:
              # FileNotFoundError: trying to open a file that doesn't exist
              with open("non_existent_file.txt", "r") as file:
                  result = file.read()
          else:
              # No error scenario
              result = "No error occurred."
      except ZeroDivisionError:
          print("Caught ZeroDivisionError: Cannot divide by zero.")
      except IndexError:
          print("Caught IndexError: List index is out of range.")
      except KeyError:
          print("Caught KeyError: The key does not exist in the dictionary.")
      except ValueError:
          print("Caught ValueError: Invalid value for conversion.")
      except FileNotFoundError:
          print("Caught FileNotFoundError: File not found.")
      except Exception as e:
          print(f"Caught a general exception: {e}")
      else:
          print("No errors occurred. Result:", result)
      finally:
          print("This block always executes.\n")
  
  # Test each error type
  for i in range(1, 7):
      print(f"Test case {i}:")
      error_examples(i)
  ```
  
  ### **Use Cases for Each Error:**
  
  - **ZeroDivisionError:** When performing arithmetic operations that might involve division by zero.
  - **IndexError:** When accessing list elements using indexes that may be out of bounds.
  - **KeyError:** When trying to access dictionary keys that might not exist.
  - **ValueError:** When converting values (like strings to numbers) that might be formatted incorrectly.
  - **FileNotFoundError:** When attempting file operations on a file that may not be present.
  
  This example uses a loop to test each error scenario, providing clear output for which error was caught, and always executes the `finally` block regardless of the error outcome.
---

# 13. Object-Oriented Programming (OOP)

- **Definition:** A programming paradigm based on the concept of "objects" that contain data and methods.
  
### 13.1 Class & Object
- **Example:**
  ```python
  class Person:
      def __init__(self, name: str):
          self.name = name
      
      def greet(self) -> str:
          return f"Hello, {self.name}"
  
  p = Person("Taha")
  print(p.greet())  # Output: Hello, Taha
  ```

### 13.2 Inheritance
- **Example:**
  ```python
  class Student(Person):
      def __init__(self, name: str, student_id: int):
          super().__init__(name)
          self.student_id = student_id
  
  student = Student("Ahmed", 101)
  print(student.greet())  # Output: Hello, Ahmed
  ```

### 13.3 Special (Magic) Methods
- **Example:**
  ```python
  class Number:
      def __init__(self, value: int):
          self.value = value
      
      def __add__(self, other):
          return self.value + other.value
  
  n1 = Number(5)
  n2 = Number(10)
  print(n1 + n2)  # Output: 15 (Uses __add__)
  ```

### 13.4 Four Pillars of OOP (Additional Examples)

#### Encapsulation
- **Example:**
  ```python
  class Person:
      def __init__(self, name):
          self.__name = name  # Private attribute
      
      def get_name(self):
          return self.__name
  
  p = Person("Taha")
  print(p.get_name())  # Output: Taha
  ```

#### Polymorphism
- **Example:**
  ```python
  class Animal:
      def sound(self):
          pass
  
  class Dog(Animal):
      def sound(self):
          return "Bark"
  
  class Cat(Animal):
      def sound(self):
          return "Meow"
  
  for animal in (Dog(), Cat()):
      print(animal.sound())
  # Output:
  # Bark
  # Meow
  ```

#### Abstraction
- **Example:**
  ```python
  from abc import ABC, abstractmethod
  
  class Vehicle(ABC):
      @abstractmethod
      def start(self):
          pass
  
  class Car(Vehicle):
      def start(self):
          print("Car started")
  
  my_car = Car()
  my_car.start()  # Output: Car started
  ```

---

# 14. File Handling

- **Definition:** Reading from and writing to files.
- **Examples:**
  ```python
  # Reading from a file
  with open("file.txt", "r") as f:
      content = f.read()
      print(content)
  
  # Writing to a file (this will overwrite if the file exists)
  with open("file.txt", "w") as file:
      file.write("Hello, Python!")
  ```

---

# 15. Advanced Topics

### 15.1 Decorators
- **Definition:** A decorator is a function that wraps another function to extend its behavior.
- **Example:**
  ```python
  def decorator(func):
      def wrapper(*args, **kwargs):
          print("Before function execution")
          result = func(*args, **kwargs)
          print("After function execution")
          return result
      return wrapper
  
  @decorator
  def my_function():
      print("Inside function")
  
  my_function()
  # Output:
  # Before function execution
  # Inside function
  # After function execution
  ```

### 15.2 Generators
- **Definition:** A generator is a function that yields a sequence of values using the `yield` keyword.
- **Example:**
  ```python
  def my_gen():
      for i in range(3):
          yield i
  
  gen = my_gen()
  print(next(gen))  # Output: 0
  print(next(gen))  # Output: 1
  print(next(gen))  # Output: 2
  ```

---

# 16. Conclusion

- This guide has covered the **core concepts** of Python—from variables and data types to advanced topics like decorators and generators.
- **Next steps:** Explore databases, APIs, machine learning, and web development frameworks (e.g., FastAPI, Django, Flask) to further enhance your skills.

---

Happy coding!
