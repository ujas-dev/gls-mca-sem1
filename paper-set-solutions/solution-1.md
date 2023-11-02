# Python Practical Exam Paper Set 1 with solutions:

**Question 1: (10 Marks)**

```python
# 1. Find the sum of all even numbers between 1 and 100.

# Initialize a variable to store the sum
even_sum = 0

# Loop through numbers from 1 to 100
for number in range(1, 101):
    if number % 2 == 0:  # Check if the number is even
        even_sum += number

# Display the sum of even numbers
print("Sum of even numbers between 1 and 100:", even_sum)
```

**Question 2: (10 Marks)**

```python
# 2. Create a Python function that calculates the factorial of a positive integer.

def factorial(n):
    if n == 0:
        return 1
    else:
        return n * factorial(n - 1)

# Input from the user
num = int(input("Enter a positive integer: "))

if num < 0:
    print("Factorial is not defined for negative numbers.")
else:
    result = factorial(num)
    print(f"Factorial of {num} is {result}")
```

**Question 3: (10 Marks)**

```python
# 3. Take user input for an integer and handle exceptions for invalid input.

try:
    user_input = int(input("Enter an integer: "))
    print("You entered:", user_input)
except ValueError:
    print("Invalid input. Please enter a valid integer.")
```

**Question 4: (10 Marks)**

```python
# 4. Define a class called Rectangle with attributes length and width. Implement a method to calculate the area.

class Rectangle:
    def __init__(self, length, width):
        self.length = length
        self.width = width

    def calculate_area(self):
        return self.length * self.width

# Input for rectangle dimensions
length = float(input("Enter the length of the rectangle: "))
width = float(input("Enter the width of the rectangle: "))

# Create a Rectangle object
rect = Rectangle(length, width)

# Calculate and display the area of the rectangle
print(f"Area of the rectangle is: {rect.calculate_area()}")
```

**Question 5: (10 Marks)**

```python
# 5. Create a multiline string and perform the specified operations:

multiline_string = """
This is the first line.
This is the second line.
This is the third line with spaces at the end.    
This is the fourth line.
This is the fifth line with "python" in it.
"""

# a. Using slicing, display the string from the 2nd line
lines = multiline_string.split('\n')
second_line_and_beyond = '\n'.join(lines[1:])
print("a. String from the 2nd line:\n", second_line_and_beyond)

# b. Remove whitespace from the end of the string
trimmed_string = multiline_string.rstrip()
print("b. String with trailing whitespace removed:\n", trimmed_string)

# c. Convert the string into a list of words and display the output
word_list = multiline_string.split()
print("c. List of words in the string:\n", word_list)

# d. Check if "python" is present in the string
search_word = "python"
if search_word in multiline_string.lower():
    print("d. 'python' is present in the string.")
else:
    print("d. 'python' is not present in the string.")

# e. Create another string variable with 3 placeholders '{}' and use the format method to replace the placeholders
var1 = "Hello"
var2 = "world"
var3 = "Python"
formatted_string = "Replace the first placeholder ({}), the second ({}), and the third ({}).".format(var1, var2, var3)
print("e. Formatted string with placeholders replaced:\n", formatted_string)
```

# Python Practical Exam Paper Set 2 with solutions:

**Question 1: (10 Marks)**

```python
# 1. Find the sum of all prime numbers between 1 and 50.

def is_prime(num):
    if num <= 1:
        return False
    if num == 2:
        return True
    if num % 2 == 0:
        return False
    for i in range(3, int(num**0.5) + 1, 2):
        if num % i == 0:
            return False
    return True

# Calculate the sum of prime numbers between 1 and 50
prime_sum = sum(num for num in range(1, 51) if is_prime(num))

print("Sum of prime numbers between 1 and 50:", prime_sum)
```

**Question 2: (10 Marks)**

```python
# 2. Create a Python function that takes a list of strings and returns the longest string in the list.

def find_longest_string(strings):
    if not strings:
        return None
    longest = 1
    result = ''
    for string in strings:
        if len(string) >= longest:
            longest = len(string)
            result = string
    return result

# Example list of strings
string_list = ["apple", "banana", "cherry", "date", "elderberry", "fig"]

# Find and display the longest string
longest_string = find_longest_string(string_list)
print("Longest string in the list:", longest_string)
```

**Question 3: (10 Marks)**

```python
# 3. Open a text file and handle exceptions if the file doesn't exist.

file_path = "sample.txt"

try:
    file = open(file_path, 'r')
    print("File open successfully.")
except FileNotFoundError:
    print(f"File '{file_path}' not found.")
```

**Question 4: (10 Marks)**

```python
# 4. Define a class called Circle with an attribute radius. Implement methods to calculate the area and circumference of the circle.

pi = 3.14

class Circle:
    def __init__(self, radius):
        self.radius = radius

    def calculate_area(self):
        return pi * self.radius**2

    def calculate_circumference(self):
        return 2 * pi * self.radius

# Input for circle radius
radius = float(input("Enter the radius of the circle: "))

# Create a Circle object
circle = Circle(radius)

# Calculate and display the area and circumference of the circle
print(f"Area of the circle is: {circle.calculate_area()}")
print(f"Circumference of the circle is: {circle.calculate_circumference()}")
```

**Question 5: (10 Marks)**

```python
# 5. Create a list of 12 elements with various data types and perform the specified operations:

# Create a list of 12 elements with various data types
my_list = [9, 3.14, "gls", True, [1, 2, 3], (1, 2, 3), {1, 2, 3}, {"name": "Amar"}, None, 2+3j, "apple", "banana"]

# a. Using the range of indexes, display the list from the 3rd to the 8th position
subset_of_list = my_list[2:8]
print("a. List from the 3rd to the 8th position:", subset_of_list)

# b. Remove the 10th position item and insert a new item at the 5th position
del my_list[9]  # Remove the item from the 10th position
my_list.insert(4, "cherry")  # Insert a new item at the 5th position
print("b. List with the 10th item removed and 'cherry' inserted at the 5th position:", my_list)

# c. Create a new list with 5 elements and append it to the existing list
new_elements = [42, "grape", (4, 5, 6), "orange", 99.9]
my_list.extend(new_elements)  # Append the new list to the existing list
print("c. List with the new elements appended:", my_list)

# d. Create a new list of fruits and use list comprehension to display fruits with 'a' in their names
fruits = ["apple", "banana", "cherry", "date", "grape", "kiwi", "lemon", "mango", "orange", "pear"]
fruits_with_a = [fruit for fruit in fruits if 'a' in fruit]
print("d. Fruits with 'a' in their names:", fruits_with_a)
```

#  Python Practical Exam Paper Set 3 with solutions:

**Question 1: (10 Marks)**

```python
# 1. Find the first 10 terms of the Fibonacci sequence.

def fibonacci(n):
    fib_sequence = [0, 1]
    while len(fib_sequence) < n:
        next_term = fib_sequence[-1] + fib_sequence[-2]
        fib_sequence.append(next_term)
    return fib_sequence

# Display the first 10 terms of the Fibonacci sequence
fib_sequence = fibonacci(10)
print("First 10 terms of the Fibonacci sequence:", fib_sequence)
```

**Question 2: (10 Marks)**

```python
# 2. Create a Python function that checks if a string is a palindrome.

def is_palindrome(input_string):
    input_string = input_string.lower().replace(" ", "")
    return input_string == input_string[::-1]

# Input string
user_input = input("Enter a string to check if it's a palindrome: ")

if is_palindrome(user_input):
    print("The input string is a palindrome.")
else:
    print("The input string is not a palindrome.")
```

**Question 3: (10 Marks)**

```python
# 3. Handle multiple exceptions (ZeroDivisionError and FileNotFoundError) in the same try-except block.

try:
    num = 10 / 0  # ZeroDivisionError
    file_path = "nonexistent.txt"
    file = open(file_path, 'r')
    print("File open successfully.")
except ZeroDivisionError:
    print("ZeroDivisionError: Division by zero is not allowed.")
except FileNotFoundError:
    print(f"File not found: The file '{file_path}' does not exist.")
```

**Question 4: (10 Marks)**

```python
# 4. Define a Python class called Person with attributes name and age. Implement a method to display the person's details.

class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def display_details(self):
        print(f"Name: {self.name}, Age: {self.age}")

# Input for person's details
name = input("Enter the person's name: ")
age = int(input("Enter the person's age: "))

# Create a Person object
person = Person(name, age)

# Display the person's details
person.display_details()
```

**Question 5: (10 Marks)**

```python
# 5. Create a tuple of 5 elements with various data types and perform the specified operations:

# Create a tuple of 5 elements with various data types
my_tuple = (42, "apple", 3.14, True, (1, 2, 3))

# a. Using the range of indexes, display the tuple starting from the 3rd position
subset_of_tuple = my_tuple[2:]
print("a. Tuple starting from the 3rd position:", subset_of_tuple)

# b. Remove the item from the 2nd position and display the output
tuple_list = list(my_tuple)
removed_item = tuple_list.pop(1)
result_tuple = tuple(tuple_list)
print("b. Tuple with the item at 2nd position removed:", result_tuple)

# c. Create 3 variables and assign values from the tuple. Display the variables values.
var1, var2, var3 = my_tuple[:3]
print("c. Values of variables var1, var2, and var3:", var1, var2, var3)

# d. Create a new tuple with 2 elements and join it. Display the joined tuple.
new_tuple = (99, "banana")
joined_tuple = my_tuple + new_tuple
print("d. Joined tuple:", joined_tuple)

# e. Multiply each element by 2 and create a new tuple.
multiplied_tuple = tuple(item * 2 for item in my_tuple)
print("e. New tuple with elements multiplied by 2:", multiplied_tuple)
```

#  Python Practical Exam Paper Set 4 with solutions:

**Question 1: (10 Marks)**

```python
# 1. Find the sum of all numbers from 1 to 100 that are divisible by both 3 and 5.

divisible_by_3_and_5 = [num for num in range(1, 101) if num % 3 == 0 and num % 5 == 0]
sum_of_divisible_numbers = sum(divisible_by_3_and_5)

print("Sum of numbers from 1 to 100 divisible by both 3 and 5:", sum_of_divisible_numbers)
```

**Question 2: (10 Marks)**

```python
# 2. Create a function that takes a list of integers and returns a new list with only the even numbers.

def get_even_numbers(input_list):
    return [num for num in input_list if num % 2 == 0]

# Example list of integers
integer_list = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

# Get and display the list of even numbers
even_numbers = get_even_numbers(integer_list)
print("List of even numbers:", even_numbers)
```

**Question 3: (10 Marks)**

```python
# 3. Use the else block to execute code when no exception is raised.

try:
    result = 10 / 2
except ZeroDivisionError:
    print("Division by zero is not allowed.")
else:
    print("No exception was raised. Result:", result)
```

**Question 4: (10 Marks)**

```python
# 4. Define a class called Car with attributes make, model, and year. Implement a method to display the car's details.

class Car:
    def __init__(self, make, model, year):
        self.make = make
        self.model = model
        self.year = year

    def display_details(self):
        print(f"Make: {self.make}, Model: {self.model}, Year: {self.year}")

# Input for car details
make = input("Enter the car's make: ")
model = input("Enter the car's model: ")
year = input("Enter the car's year: ")

# Create a Car object
car = Car(make, model, year)

# Display the car's details
car.display_details()
```

**Question 5: (10 Marks)**

```python
# 5. Create a dictionary of 5 key-value pairs and perform the specified operations:

# Create a dictionary with key-value pairs
my_dict = {"name": "John", "age": 30, "city": "New York", "email": "john@example.com", "phone": "1234567890"}

# a. Display the keys and values from the dictionary.
print("a. Dictionary Keys:", my_dict.keys())
print("   Dictionary Values:", my_dict.values())

# b. Update the key 'name' and remove the last pair.
my_dict["name"] = "Jane"
last_key = list(my_dict.keys())[-1]
del my_dict[last_key]
print("b. Updated dictionary:", my_dict)

# c. Copy the dictionary into a new variable and clear the previous dictionary variable.
new_dict = my_dict.copy()
my_dict.clear()
print("c. New dictionary after copying:", new_dict)
print("   Previous dictionary after clearing:", my_dict)

# d. Create a nested dictionary with name 'student_info' and display the name and age.
student_info = {"student_info": {"name": "Alice", "age": 25}}
print("d. Nested dictionary - Name:", student_info["student_info"]["name"])
print("   Nested dictionary - Age:", student_info["student_info"]["age"])
```

# Python Practical Exam Paper Set 5 with solutions:

**Question 1: (10 Marks)**

```python
# 1. Generate the first 10 square numbers (1, 4, 9, 16, ...).

square_numbers = [i ** 2 for i in range(1, 11)]

print("First 10 square numbers:", square_numbers)
```

**Question 2: (10 Marks)**

```python
# 2. Create a function that finds the largest element in a list of numbers.

def find_largest_element(numbers):
    if len(numbers) == 0:
        return None  # Handle empty list
    return max(numbers)

# Example list of numbers
number_list = [5, 12, 8, 17, 3, 20, 9]

# Find and display the largest element in the list
largest_element = find_largest_element(number_list)
print("Largest element in the list:", largest_element)
```

**Question 3: (10 Marks)**

```python
# 3. Write a python program to use the finally block to execute code when exception is raised.

try:
    result = 10 / 0  # This will raise a ZeroDivisionError
except ZeroDivisionError:
    print("Exception: Division by zero is not allowed.")
finally:
    print("Code in the 'finally' block always executes.")
```

**Question 4: (10 Marks)**

```python
# 4. Define a Python class called Book with attributes title, author, and publication_year. Implement a method to display the book's details.

class Book:
    def __init__(self, title, author, publication_year):
        self.title = title
        self.author = author
        self.publication_year = publication_year

    def display_details(self):
        print(f"Title: {self.title}, Author: {self.author}, Publication Year: {self.publication_year}")

# Input for book details
title = input("Enter the book's title: ")
author = input("Enter the book's author: ")
publication_year = input("Enter the book's publication year: ")

# Create a Book object
book = Book(title, author, publication_year)

# Display the book's details
book.display_details()
```

**Question 5: (10 Marks)**

```python
# 5. Generate a multiplication table from 1 to 5 using nested loops.

for i in range(1, 6):
    print(f"Multiplication table for {i}:")

    for j in range(1, 11):
        product = i * j
        print(f"{i} x {j} = {product}")

    print()  # Separate tables with an empty line
```
