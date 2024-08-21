
1.  **Introduction to Python**

  

    Python is a high-level, interpreted programming language known for its easy-to-read syntax and versatility. It supports multiple programming paradigms, including procedural, object-oriented, and functional programming.

  

2.  **Data Types**

  

    Python has several built-in data types:
-  **Integer**: Whole numbers without a fractional part.

```python
age =  21
```

  
  

-  **Float**: Numbers with a fractional part.

  

```python
price =  19.99
```

  
  

- **String**: A sequence of characters.

```python
name =  "Alice"
```

- **Boolean**: Represents `True` or `False`.

```python 
is_student = True
```


- **List**: An ordered, mutable collection of items.

```python

fruits = ["apple", "banana", "cherry"]
```
- **Dictionary**: A collection of key-value pairs.

```python
person = {"name": "John", "age": 30}
```


3. **Input**

python uses the `input()` function to take user input.

```python
name = input("Enter your name: ")
print("Hello, " + name + "!")
```
4. **Variables**

Variables are used to store data. They can be assigned values using the `=` operator.

```python
x = 10
y = 5
z = x + y
```
5. **Arithmetic Operations**

python supports basic arithmetic operations.

```python

a = 10

b = 3

print("Addition:", a + b)  #13

print("Subtraction:", a - b)  #7

print("Multiplication:", a * b)  #30

print("Division:", a / b)  #3.333...

print("Modulus:", a % b)  #1

print("Exponentiation:", a  b) #1000
```
6. **Conditional Operators**

These are used to compare values.

```python

a = 10

b = 5

print(a > b)  True

print(a < b)  False

print(a == b) False

print(a != b) True
```
7. **If-Else Statements**

Conditional statements allow your program to make decisions.

```python

age = 18

if age >= 18:

print("You are an adult.")

else:

print("You are not an adult.")
```
8. **Else-If (Elif)**

`elif` is used for multiple conditions.

```python

score = 85

if score >= 90:

print("Grade: A")

elif score >= 80:

print("Grade: B")

elif score >= 70:

print("Grade: C")

else:

print("Grade: F")
```
9. **Lists with Functions**

    A list is a mutable collection, and python provides various functions to manipulate them.

1. `append(x)`

    Adds an item `x` to the end of the list.

```python

fruits = ["apple", "banana", "cherry"]

fruits.append("orange")

print(fruits)  Output: ['apple', 'banana', 'cherry', 'orange']
```
2. `extend(iterable)`

    Extends the list by appending elements from the given iterable (like another list).

```python
fruits = ["apple", "banana"]

fruits.extend(["cherry", "orange"])

print(fruits)  Output: ['apple', 'banana', 'cherry', 'orange']
```
3. **`insert(i, x)`**

    Inserts an item `x` at a given position `i`.

```python
fruits = ["apple", "banana", "cherry"]

fruits.insert(1, "orange")

print(fruits)  Output: ['apple', 'orange', 'banana', 'cherry']
```
4. `remove(x)`

    Removes the first item from the list whose value is equal to `x`.

```python
fruits = ["apple", "banana", "cherry"]

fruits.remove("banana")

print(fruits)  Output: ['apple', 'cherry']
```
5. `pop([i])`

    Removes and returns the item at the given position `i` in the list. If no index is specified, `pop()` removes and returns the last item in the list.

```python

fruits = ["apple", "banana", "cherry"]

fruit = fruits.pop(1)

print(fruits)  Output: ['apple', 'cherry']

last_fruit = fruits.pop()

print(fruits)  Output: ['apple']
```
6. `clear()`

    Removes all items from the list, leaving it empty.

```python
fruits = ["apple", "banana", "cherry"]

fruits.clear()

print(fruits)  Output: []
```
7. `index(x, [start], [end])`

Returns the index of the first item whose value is equal to `x`.

```python
fruits = ["apple", "banana", "cherry"]

index = fruits.index("banana")

print(index)  Output: 1

print(fruits)  Output: ['apple', 'banana', 'cherry']
```
8. `count(x)`

Returns the number of times `x` appears in the list.

```python

fruits = ["apple", "banana", "cherry", "apple"]
count = fruits.count("apple")
print(count) 
# Output: 2
print(fruits)  Output: ['apple', 'banana', 'cherry', 'apple']
```
9. `sort(key=None, reverse=False)`

Sorts the items of the list in place (the list itself is modified).

```python

fruits = ["cherry", "banana", "apple"]

fruits.sort()

print(fruits)  Output: ['apple', 'banana', 'cherry']

fruits.sort(reverse=True)

print(fruits)  Output: ['cherry', 'banana', 'apple']
```
10. `reverse()`

Reverses the elements of the list in place.

```python

fruits = ["apple", "banana", "cherry"]

fruits.reverse()

print(fruits)  Output: ['cherry', 'banana', 'apple']
```
11. `copy()`

Returns a shallow copy of the list.

```python

fruits = ["apple", "banana", "cherry"]

new_fruits = fruits.copy()

print(new_fruits)  Output: ['apple', 'banana', 'cherry']

print(fruits)  Output: ['apple', 'banana', 'cherry']
```
12. `len(list)`

Returns the number of items in the list.

```python

fruits = ["apple", "banana", "cherry"]

length = len(fruits)

print(length)  Output: 3

print(fruits)  Output: ['apple', 'banana', 'cherry']
```
13. `max(list)`

Returns the largest item in the list.

```python

numbers = [3, 1, 4, 1, 5, 9]

largest = max(numbers)

print(largest)  Output: 9

print(numbers)  Output: [3, 1, 4, 1, 5, 9]

14. `min(list)`
```
Returns the smallest item in the list.

```python

numbers = [3, 1, 4, 1, 5, 9]

smallest = min(numbers)

print(smallest)  Output: 1

print(numbers)  Output: [3, 1, 4, 1, 5, 9]
```
15. `sum(list)`

Returns the sum of all the items in the list.

```python

numbers = [3, 1, 4, 1, 5, 9]

total = sum(numbers)

print(total)  Output: 23

print(numbers)  Output: [3, 1, 4, 1, 5, 9]
```
10. **Dictionaries with Functions**

A dictionary is a collection of key-value pairs.

1. `get(key, default=None)`

Returns the value for the specified key if the key is in the dictionary; otherwise, it returns the `default` value.

```python

person = {"name": "Alice", "age": 25, "city": "New York"}

value = person.get("age")

print(value)  Output: 25

print(person)  Output: {'name': 'Alice', 'age': 25, 'city': 'New York'}

value = person.get("email", "Not Available")

print(value)  Output: Not Available

print(person)  Output: {'name': 'Alice', 'age': 25, 'city': 'New York'}
```
2. `keys()`

Returns a new view of the dictionary's keys.

```python

person = {"name": "Alice", "age": 25, "city": "New York"}

keys = person.keys()

print(keys)  Output: dict_keys(['name', 'age', 'city'])

print(person)  Output: {'name': 'Alice', 'age': 25, 'city': 'New York'}
```
3. `values()`

Returns a new view of the dictionary's values.

```python

person = {"name": "Alice", "age": 25, "city": "New York"}

values = person.values()

print(values)  Output: dict_values(['Alice', 25, 'New York'])

print(person)  Output: {'name': 'Alice', 'age': 25, 'city': 'New York'}
```
4. `items()`

Returns a new view of the dictionary's key-value pairs.

```python

person = {"name": "Alice", "age": 25, "city": "New York"}

items = person.items()

print(items)  Output: dict_items([('name', 'Alice'), ('age', 25), ('city', 'New York')])

print(person)  Output: {'name': 'Alice', 'age': 25, 'city': 'New York'}
```
5. **`pop(key, default=None)`**

Removes the specified key and returns the corresponding value. If the key is not found, returns the `default` value.

```python

person = {"name": "Alice", "age": 25, "city": "New York"}

age = person.pop("age")

print(age)  Output: 25

print(person)  Output: {'name': 'Alice', 'city': 'New York'}

email = person.pop("email", "Not Available")

print(email)  Output: Not Available

print(person)  Output: {'name': 'Alice', 'city': 'New York'}
```
6. **`popitem()`**

Removes and returns the last inserted key-value pair as a tuple. In ```python versions before 3.7, it removes an arbitrary item instead.

```python

person = {"name": "Alice", "age": 25, "city": "New York"}

item = person.popitem()

print(item)  Output: ('city', 'New York')

print(person)  Output: {'name': 'Alice', 'age': 25'}
```
7. **`update([other])`**

Updates the dictionary with elements from another dictionary object or from an iterable of key-value pairs. If a key already exists in the dictionary, its value is updated.

```python

person = {"name": "Alice", "age": 25}

person.update({"age": 26, "city": "New York"})

print(person)  Output: {'name': 'Alice', 'age': 26, 'city': 'New York'}
```
8. **`clear()`**

Removes all items from the dictionary, leaving it empty.

```python

person = {"name": "Alice", "age": 25, "city": "New York"}

person.clear()

print(person)  Output: {}
```
11. **Loops**

- For Loop: Used to iterate over a sequence.

The `for` loop with `range()` is commonly used in python to iterate over a sequence of numbers. Below are examples demonstrating how `range()` works in a `for` loop.

1. Basic `range(stop)`

When `range()` is called with a single argument `stop`, it generates numbers from `0` to `stop - 1`.

```python

for i in range(5):

print(i)
```
```python
# Output:
0
1
2
3
4
```
2. **`range(start, stop)`**

When `range()` is called with two arguments, it generates numbers from `start` to `stop - 1`.

```python
for i in range(2, 6):

print(i)
```
```python
#Output:
2
3
4
5
```
3. **`range(start, stop, step)`**

When `range()` is called with three arguments, it generates numbers from `start` to `stop - 1`, incrementing by `step`. If `step` is negative, it decrements the value.

```python

# Incrementing by 2

for i in range(1, 10, 2):

print(i)
```
```python
#Output:
1
3
5
7
9
```
```python
# Decrementing by 1

for i in range(5, 0, -1):

print(i)
```
```python
#Output:

5
4
3
2
1
```
4. **Looping Over an Empty Range**

If the `start` value is greater than or equal to the `stop` value when `step` is positive (or the opposite with a negative `step`), the `range()` will produce an empty sequence, and the loop will not execute.

```python

for i in range(5, 5):

print(i)  This will not print anything

for i in range(5, 0):

print(i)  This will not print anything

for i in range(5, 0, -1):

print(i)
```
```python
#Output:
5
4
3
2
1
```
5. **Using `range()` in Reverse Order**

You can create a descending sequence by setting a negative `step`.

```python

for i in range(10, 0, -2):

print(i)
```
```python
#Output:
10
8
6
4
2
```
6. **Using `range()` to Generate Indexes for Lists**

`range()` is often used to loop through the indexes of a list.

```python

fruits = ["apple", "banana", "cherry"]

for i in range(len(fruits)):

print(i, fruits[i])
```
```python
#Output:

0 apple

1 banana

2 cherry
```
These examples show how `range()` can be used in different scenarios with a `for` loop to iterate over a sequence of numbers, either in ascending or descending order, and with varying step sizes.

```python

for fruit in fruits:

print(fruit)
```
- While Loop: Repeats as long as a condition is true.

```python

count = 0

while count < 5:

print(count)

count += 1
```
12. **Functions**

Functions are blocks of reusable code that perform a specific task.

Example 1: A Function that Prints a Message

```python

def greet(name):

print(f"Hello, {name}!")

Calling the function

greet("Alice")

Output:

Hello, Alice!

def greet(name):

return "Hello, " + name + "!"

print(greet("Alice"))
```
13. **Object-Oriented Programming (OOP)**

OOP is a programming paradigm based on the concept of objects. python supports OOP with classes and objects.

- Class: A blueprint for creating objects.

```python

class Dog:

	def __init__(self, name, breed):

	self.name = name

	self.breed = breed

	def bark(self):

	return "Woof!"
```
- Object: An instance of a class.

```python

my_dog = Dog("Buddy", "Golden Retriever")

print(my_dog.name)  # Buddy

print(my_dog.bark())  # Woof!
```
14. **Inheritance**

Inheritance allows a class to inherit attributes and methods from another class.

```python

class Animal:

def __init__(self, name):

self.name = name

def speak(self):

return "Some sound"

class Dog(Animal):

def speak(self):

return "Woof!"

my_dog = Dog("Buddy")

print(my_dog.speak())  
```
```python
#Output
Woof!
```