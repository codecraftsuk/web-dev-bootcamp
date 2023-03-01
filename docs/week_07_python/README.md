<script src="//cdn.jsdelivr.net/npm/prismjs@1/components/prism-bash.min.js"></script>
<script src="//cdn.jsdelivr.net/npm/prismjs@1/components/prism-php.min.js"></script>

# 1. Introduction to Python

## 1.1 What is Python

Python is a high-level, interpreted programming language that was first released in 1991. It is widely used in various domains, such as web development, scientific computing, data analysis, machine learning, and artificial intelligence. Python's syntax emphasizes code readability and simplicity, which makes it an ideal choice for beginners and experienced programmers alike.

Python is an interpreted language, which means that the code is executed line by line, and you don't need to compile the code before running it. This makes Python an ideal language for prototyping and development.

Python has two major versions: Python 2 and Python 3. The primary difference between the two is that Python 2 is no longer supported and has been officially deprecated. Python 3, on the other hand, is the latest version and has many new features and improvements over Python 2.

## 1.2 Downloading Python

Firstly, check if you have python installed on your computer by opening up your command prompt/git bash (Windows) or terminal (Mac/Linux) and simply typing `python` or `python3` depending on the way your computer is set up.

<p align="center">
  <img src="https://raw.githubusercontent.com/codecraftsuk/web-dev-bootcamp/main/docs/_media/week_07_python/pythoncheck.png">
</p>

If Python is not installed onto your machine, it can be done as follows:

1. Go to the official Python website at https://www.python.org/downloads/

2. Click on the `Download Python` button.

3. Select the appropriate installer for your operating system. For example, if you're using Windows, you should select the "Windows x86-64 executable installer" if you're running a 64-bit version of Windows, or the "Windows x86 executable installer" if you're running a 32-bit version of Windows.

4. After selecting the appropriate installer, click on the link to download it.

5. Once the download is complete, open the installer and follow the on-screen instructions to install Python on your machine.

6. During the installation process, you will be prompted to choose various options. The default options are usually sufficient for most users, but you may wish to customize your installation by selecting or deselecting certain features.

7. Once the installation is complete, open a command prompt/git bash (Windows) or terminal (Mac/Linux) and type python to start the Python interpreter. If Python is installed correctly, you should see the version number displayed in the console.


## 1.2 First Line of Code

Let’s start where we start with many programming languages: Hello, world. The first thing to do is to open up Visual Studio Code and create a new file with the python extension `.py` e.g. `hello.py`. Then, the first line of code can be written as follows:

```python
print("Hello, World!")
```

To run the python code, simply open up your terminal in Visual Studio Code which will be in the corerct file location by default, or any other terminal where in that case, you would have to locate to the folder in which you saved the file. Then in the console, type:

```bash
python hello.py
```

When you type `python hello.py` in your console, a program called an interpreter, which you downloaded together with Python, reads through your file line by line, and executes each line of the code. This is different than languages like C or Java, which need to be compiled into machine code before they can be run.

The `"Hello, World!"` program is a simple program that is often used as a first example when learning a new programming language. The purpose of the program is to output the string `"Hello, World!"` to the console, which is a basic way to demonstrate that the language is working correctly.

In our `"Hello, World!"` program, we pass a single argument to the print function: the string `"Hello, World!"`.

Strings are a fundamental data type in Python, and they are used to represent text. A string is a sequence of characters that are enclosed in quotes, either single quotes (') or double quotes ("). In our program, we use double quotes to enclose the string `"Hello, World!"`.

When we run the `"Hello, World!"` program in Python, the print function outputs the string `"Hello, World!"` to the console. The console is a text-based interface where we can interact with the Python interpreter, and it is often used for debugging and testing programs.

Overall, the `"Hello, World!"` program is a simple and effective way to demonstrate the basic syntax and functionality of Python. It provides a foundation for learning more advanced concepts, such as variables, data types, and control structures, which are essential for writing more complex programs.

# 2. Fundamentals

## 2.1 Variables

In programming, a variable is a container that stores a value. The value can be of different types, such as numbers, text, or other data. We can give a name to the variable, which allows us to refer to the value stored in the variable by that name.

Think of a variable as a labeled box that can store different things. Just like a box, a variable can store different types of things, like numbers, text, or other data. The name of the variable is like a label on the box, which allows us to easily find and access the value stored inside.

For example, let's say we want to store the number 10 in a variable called `my_variable`. We can do that with the following code:

```python
my_variable = 10
```

This assigns the value of 10 to the variable `my_variable`. Now, if we want to use that value in our code, we can simply refer to it by its variable name, like this:

```python
print(my_variable)
```

This will output the value of `my_variable`, which is 10.

Variables are important because they allow us to store and manipulate data in our programs. By giving a name to a value, we can easily refer to it later in our code, and we can update or change the value as needed. In this way, variables make our code more flexible and easier to manage.

Now lets look at an example where we eant to store more variables where we store different types of data.

```python
x = 100
y = 1.742
z = "This is a string."
a = True
b = None
```

Each variable is being stored, where the value on the left is is the variable name and the value on the right is the value that is being stored, and this is called variable declaration.

In Python, we don't have to explicitly state the data type of a variable when we create it. The Python interpreter can usually determine the data type based on the value that we assign to the variable. This is known as "type inference".

## 2.2 Data Types

 Data types are a way to classify different types of data that can be used in a program. They help us understand how data can be stored, processed, and manipulated in our programs. We have briefly discussed it when looking at the declaring variables, but now we look at more data types.

 The most common types of data are as follows:

 1. **Integer**: An integer is a whole number, such as 1, 2, 3, -4, or 0. In Python, integers have no decimal point and can be positive or negative.
 
 2. **Float**: A float is a decimal number, such as 3.14, 2.5, or -0.5. In Python, floats have a decimal point and can be positive or negative.

 3. **String**: A string is a sequence of characters, such as "hello", "world", or "123". In Python, strings are enclosed in quotes, either single quotes ('...') or double quotes ("...").

 4. **Boolean**: A boolean is a binary value that is either true or false. In Python, the boolean values are represented as True and False.

 5. **NoneType** The NoneType data type represents the absence of a value, and it is often used to indicate that a variable or function has no value or that a value has not been initialized.


Looking at the variable declaration above i.e. values `x`, `y`, `z`, `a` and `b`, the data types of these variables are as follows:

1. `x` int: An integer
2. `y` float: A decimal number
3. `z` str: A string, or sequence of characters.
4. `a` bool: A value that is either True or False
5. `b` NoneType: A special value (None) indicating the absence of a value

Now, lets take these ideas and create a simple python script that prints some information to the console.

```python
# Declare integer variable
age = 25

# Declare floating-point variable
weight = 65.4

# Declare string variable
name = "Alice"

# Declare boolean variable
is_sunny = True

# Print variables to console
print("My name is", name)
print("I am", age, "years old and weigh", weight, "kilograms.")
print("It is sunny today:", is_sunny)
```

When we run this code, we should see output like this:

```bash
My name is Alice
I am 25 years old and weigh 65.4 kilograms.
It is sunny today: True
```

Looking at the code above, the first thing that is new is `#`. The `#` character is used in Python to indicate a comment in your code. Comments are notes that you can include in your code to explain what the code is doing, why you wrote it that way, or to provide any other relevant information to yourself or other programmers who may read your code.

When Python encounters a # character in your code, it ignores everything on that line after the # character. This means that you can write anything you want after the #, and Python will not interpret it as code. Instead, it will treat it as a comment that is only there to provide information to the person reading the code.

Additionally, the variables that we declared have been used in the print function alongside some text that has been put in quotation marks i.e. a string. One way of including a variable in a print function is to use a comma to separate it from the string as seen above and simply typing the variable name. 

## 2.3 Formatting Strings

A better way to format strings is to use a **formatted string**, also known as an **f-string** for short. Here is an example of how it works:

```python
name = "John Smith"
age = 21
height = 1.95

# Using f-strings to format a string with variables
print(f"My name is {name}, I am {age} years old, and I am {height:.2f} meters tall.")
```

In this example, we are using an f-string to create a formatted string that includes the values of several variables: `name`, `age`, and `height`.

The f-string starts with an `f` character before the opening quotation mark, which tells Python to treat the string as a formatted string. We can then include curly braces `{}` in the string, which will be replaced with the values of the variables we specify.

In this example, we are using `{}` to insert the values of `name`, `age`, and `height` into the string. We are also using `:.2f` to format the height variable as a floating-point number with two decimal places. 

When we run this code, we should see output like this:

```bash
My name is Alice, I am 25 years old, and I am 1.68 meters tall.
```

## 2.4 Operators and Expressions

In Python, operators and expressions are important concepts that allow you to perform various calculations and operations in your code. Here's an overview of some of the main topics you'll learn about:

**Arithmetic Operators** are used to perform mathematical calculations on numbers. The basic arithmetic operators in Python are:

- `+` addition
- `-` subtraction
- `*` multiplication
- `/` division
- `%` modulus (returns the remainder of division)
- `**` exponentiation (raises a number to a power)

**Comparison Operators** are used to compare values and return a boolean (True or False) result. Some common comparison operators are:

- `==` equal to
- `!=` not equal to
- `<` less than
- `>` greater than
- `<=` less than or equal to
- `>=` greater than or equal to

**Logical Operators** are used to combine multiple boolean expressions together. The main logical operators in Python are:

- `and` returns True if both expressions are True
- `or` returns True if either expression is True
- `not` negates the expression (True becomes False, and vice versa)

**Expressions** are combinations of operators, variables, and values that evaluate to a single value. Expressions can be simple, like `5 + 3`, or more complex, like `x > 5 and y < 10`.

**Conditional Statements** are used to control the flow of your code based on certain conditions. The most common conditional statement in Python is the `if` statement, which allows you to execute different code blocks based on whether a condition is True or False.

**Loops** are used to repeat code multiple times. The two main types of loops in Python are `for` loops and `while` loops. `for` loops are used to iterate over a collection of values, like a list or tuple. `while` loops are used to repeat code while a certain condition is True.

Overall, understanding these concepts is essential for writing effective Python code and we will dive into those step by step.

### 2.4.1 Arithmetic Operators

As mentioned above, **arithmetic Operators** are used to perform mathematical calculations on numbers. Here are some examples to demonstrate how they can be used:

```python
# Addition
x = 5
y = 3
result = x + y
print(result) # Output: 8

# Subtraction
x = 7
y = 2
result = x - y
print(result) # Output: 5

# Multiplication
x = 4
y = 6
result = x * y
print(result) # Output: 24

# Division
x = 8
y = 2
result = x / y
print(result) # Output: 4.0 (Note: division always returns a float)

# Modulus
x = 11
y = 3
result = x % y
print(result) # Output: 2 (Note: modulus returns the remainder of division)

# Exponentiation
x = 2
y = 3
result = x ** y
print(result) # Output: 8 (Note: exponentiation raises x to the power of y)
```

In these examples, you can see how arithmetic operators can be used to perform basic mathematical calculations. By assigning values to variables and using arithmetic operators, you can create more complex expressions to perform more advanced calculations.


### 2.4.2 Shorthand Notation

Python provides shorthand notation for arithmetic operations that allows for more concise code. These shorthand notations use the assignment operator (`=`) along with one of the arithmetic operators (`+`, `-`, `*`, `/`, `%`, `**`). Here's an example of shorthand notation in action:

```python
x = 5
x += 3 # equivalent to x = x + 3
print(x) # Output: 8

y = 10
y *= 2 # equivalent to y = y * 2
print(y) # Output: 20
```

In this example, we first set the variable `x` to 5. We then use the `+=` shorthand notation to add 3 to `x` and reassign the result to `x`. This is equivalent to writing `x = x + 3`. Similarly, we set the variable `y` to 10 and then use the `*=` shorthand notation to multiply `y` by 2 and reassign the result to `y`. This is equivalent to writing `y = y * 2`.

Shorthand notation can be useful for making code shorter and more concise. It also often makes the code easier to read and understand, as it can make the intent of the code clearer. However, it's important to use shorthand notation judiciously and make sure that it doesn't make the code less clear or harder to understand.


### 2.4.3 Comparative Operators

**Comparative operators** are used to compare values and return a boolean value (`True` or `False`) depending on whether the comparison is true or false. Here are some examples of how they work:

```python
# Declare some variables
x = 5
y = 3

# Greater than
print(x > y)  # True

# Less than
print(x < y)  # False

# Greater than or equal to
print(x >= y)  # True

# Less than or equal to
print(x <= y)  # False

# Equal to
print(x == y)  # False

# Not equal to
print(x != y)  # True
```

In this example, we've declared two variables `x` and `y`, and then used each of the comparison operators to compare their values.

Note that the result of each comparison is a boolean value (`True` or `False`). This is because comparison operators return a boolean value that indicates whether the comparison is true or false.

You can use comparison operators in a variety of contexts in Python, such as in **conditional statements** (`if`, `else`, `elif`) and loops (`while`, `for`) for a more practical use case, which we will look into.

### 2.4.4 Logical Operators

**Logical operators** are used to combine multiple conditions and return a boolean value based on whether the combined conditions are true or false. Here are some examples of how they work:

```python
# Declare some variables
x = 5
y = 3
z = 7

# Using "and" operator
print(x > y and z > x)  # True

# Using "or" operator
print(x < y or z < y)  # False

# Using "not" operator
print(not x < y)  # True
```

In this example, we've declared three variables `x`, `y`, and `z`, and then used each of the logical operators to combine multiple conditions. Note that the result of each combination is a boolean value (True or False). This is because logical operators return a boolean value that indicates whether the combined conditions are true or false.


You can see every possible outcome of the and/or operator in its truth table below:

| Expression | Evaluates to… |
| -----------|-----------|
| True and True | True |
| True and False | False | 
| False and True | False |
| False and False | False |


| Expression | Evaluates to… |
| -----------|-----------|
| True or True | True |
| True or False | True | 
| False or True | True |
| False or False | False |

Additionally, you can also have the `not` Operator’s Truth Table:

| Expression | Evaluates to… |
| -----------|-----------|
| not True | False |
| not False | True |


You can use logical operators in a variety of contexts in Python, such as in **conditional statements** (`if`, `else`, `elif`) and loops (`while`, `for`) for a more practical use case, which we will look into.

### 2.4.5 Conditional Statements

Conditional statements are used in programming to execute certain blocks of code only if a particular condition is met. In Python, conditional statements are created using the `if`, `elif` (short for "else if"), and `else` keywords. Here's an example:

```python 
x = 5
if x < 0:
    print("x is negative")
elif x == 0:
    print("x is zero")
else:
    print("x is positive")
```

In this example, we're checking the value of the variable `x` and printing out a different message depending on whether it's negative, zero, or positive. The `if` statement checks whether `x` is less than zero, and if it is, it prints the message `"x is negative"`. If `x` is not less than zero, the program moves on to the next statement, `elif x == 0`. This checks whether `x` is equal to zero, and if it is, it prints the message `"x is zero"`. If neither of these conditions is true, the program moves on to the `else` statement, which simply prints the message `"x is positive"`.

Note that the `elif` and `else` statements are optional - you can have just an `if` statement, or an `if` statement followed by any number of `elif` statements, followed by an optional `else` statement. Here's an example with just an `if` statement:

```python
age = 15
if age < 18:
    print("Sorry, you are not old enough to vote yet.")
```

In this example, we're checking whether a variable `age` is less than 18, and if it is, we're printing a message telling the user they can't vote yet.

Conditional statements can also be nested, meaning that you can put one inside another. Here's an example:

```python
x = 5
if x > 0:
    if x < 10:
        print("x is a positive single-digit number.")
    else:
        print("x is a positive number with more than one digit.")
else:
    print("x is not a positive number.")
```

In this example, we're checking whether `x` is a positive single-digit number, a positive number with more than one digit, or not a positive number at all. If `x` is greater than 0, we check whether it's less than 10 using another `if` statement inside the first one. If it is, we print the message `"x is a positive single-digit number."`. If `x` is not less than 10, we print the message `"x is a positive number with more than one digit."`. If `x` is not greater than 0 at all, we print the message `"x is not a positive number."`.

These are just a few examples of how conditional statements can be used in Python. They are a fundamental part of programming, and are used in many different contexts to control the flow of a program based on various conditions.

### 2.4.6 Loops

Loops are a way to repeat a block of code multiple times. In Python, there are two types of loops: `for` loops and `while` loops.

**For Loops**


A `for` loop is used to iterate over a sequence of elements, such as a list or a string. The syntax of a `for` loop is as follows:

```python
for variable in sequence:
    # code to execute
```

Here, `variable` is a variable that will take on the value of each element in the sequence, and sequence is the `sequence` of elements to iterate over. For example:

```python
for i in range(1, 11):
  print(i)
```
Output:

```bash
1
2
3
4
5
6
7
8
9
10
```

- The `range(1, 11)` function generates a sequence of integers from 1 to 10 (inclusive of 1 but exclusive of 11) that can be iterated over.
- The `for` loop iterates through each value in the sequence generated by `range(1, 11)`.
- For each value of `i` in the sequence, the `print(i)` statement is executed, which prints the value of `i` to the console.

Therefore, this code will print the numbers 1 to 10, each on a separate line, in the console output.

Additionally, you could also iterate over a data structure such as a list as demonstrated below:

```python
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
    print(fruit)
```

Output:

```bash
apple
banana
cherry
```
Here, the `fruit` variable takes on the value of each element in the `fruits` list, and the `print(fruit)` statement is executed for each element in the list.


**While Loops**

A `while` loop is used to execute a block of code repeatedly as long as a certain condition is true. The syntax of a `while` loop is as follows:

```python
while condition:
    # code to execute
```
Here, `condition` is the condition that is checked before each iteration of the loop. For example:

```python
count = 0
while count < 5:
    print(count)
    count += 1
```
Output:

```bash
0
1
2
3
4
```

Here, the `count` variable starts at 0, and the `while` loop executes as long as `count` is less than 5. Inside the loop, the value of `count` is printed and then incremented by 1.


Additionally, you can use `break` and `continue` statements as flow control in loops to alter the normal flow of control. 

- `break`: It is used to terminate the loop early, even if the loop condition has not become false or the iterable has not been fully traversed. When a `break` statement is executed inside a loop, the loop is terminated, and the control is transferred to the next statement after the loop.

- `continue`: It is used to skip a particular iteration of the loop and move to the next iteration. When a `continue` statement is executed inside a loop, the current iteration is stopped, and the control is transferred back to the beginning of the loop for the next iteration.

The following examples demonstate this:

```python
# This program prints the even numbers between 1 and 10

i = 1
while i <= 10:
    if i % 2 == 0:
        print(i)
        i += 1
        break
    i += 1
```

Output:

```bash
2
```

- This while loop starts with `i = 1`.
- The loop continues as long as `i` is less than or equal to 10.
- The `if` statement checks if `i` is even (i.e. divisible by 2). If it is, it prints `i`, increments `i` by 1, and then exits the loop using the `break` statement.
- If `i` is odd, the loop continues without printing anything, and `i` is incremented by 1.
- The loop stops executing once the `break` statement is executed.

```python
# This program prints the odd numbers between 1 and 10

i = 1
while i <= 10:
    if i % 2 == 0:
        i += 1
        continue
    print(i)
    i += 1
```

Output:

```bash
1
3
5
7
9
```


- This while loop starts with `i = 1`.
- The loop continues as long as `i` is less than or equal to 10.
- The `if` statement checks if `i` is even (i.e. divisible by 2). If it is, it skips the remaining code in the loop and jumps back to the top of the loop using the `continue` statement.
- If `i` is odd, it prints `i` to the console and then increments `i` by 1.
- The loop then goes back to the top and checks the condition again.



That's a brief introduction to loops in Python. There are many different ways to use loops and we will look at more complex examples as we go along. 

## 2.5 Data Structures

A data structure is a way of organizing and storing data in a computer program so that it can be accessed and manipulated efficiently. It provides a standard way of representing data that is easy to work with, making it easier for programmers to write code and for computers to execute that code quickly.

There are several types of data structures in Python, some of which include:

1. Lists: A list is a collection of items that are ordered and changeable. Lists are created using square brackets and individual items are separated by commas. For example:

```python
fruits = ['apple', 'banana', 'orange']
```

2. Tuples: A tuple is similar to a list, but it is immutable, meaning that its values cannot be changed once it is created. Tuples are created using parentheses and individual items are separated by commas. For example:

```python
colors = ('red', 'green', 'blue')
```

3. Dictionaries: A dictionary is a collection of key-value pairs where each key is unique. Dictionaries are created using curly braces and individual items are separated by commas. For example:

```python
person = {'name': 'John', 'age': 30, 'gender': 'male'}
```

4. Sets: A set is a collection of unique items that are unordered. Sets are created using curly braces or the set() function. For example:

```python
numbers = {1, 2, 3, 4, 5}
```

Each of these data structures has its own strengths and weaknesses and can be used in different ways depending on the specific needs of the program. For example, lists can be used to store and manipulate large amounts of data, while dictionaries are often used to represent objects or entities with multiple attributes.

Lets have a deeper look into lists, tuples and dictionaries as they are the most commonly used.

### 2.5.1 Lists

**Creating a List:**

To create a list, you can use square brackets [] and separate each element with a comma. For example, to create a list of numbers, you can use the following code:

```python
numbers = [1, 2, 3, 4, 5]
```

**Accessing Elements:**

You can access individual elements in a list using indexing. Indexing starts from 0, so the first element in a list has an index of 0, the second element has an index of 1, and so on. For example, to access the second element in the list above, you can use the following code:

```python
second_number = numbers[1]
```

You can also use negative indexing to access elements from the end of the list. For example, to access the last element in the list, you can use the following code:

```python
last_number = numbers[-1]
```

**Modifying Elements:**

You can modify elements in a list by using indexing to access the element and then assigning a new value to it. For example, to change the second element in the list to 10, you can use the following code:

```python
numbers[1] = 10
```

**Adding Elements:**

You can add elements to a list using various methods. The append() method adds an element to the end of the list, while the insert() method adds an element at a specific index. For example, to add the number 6 to the end of the list, you can use the following code:

```python
numbers.append(6)
```

To add the number 0 to the beginning of the list, you can use the insert() method as follows:

```python
numbers.insert(0, 0)
```

**Removing Elements:**

You can remove elements from a list using various methods. The remove() method removes the first occurrence of a specified element, while the pop() method removes an element at a specific index. For example, to remove the number 3 from the list, you can use the following code:

```python
numbers.remove(3)
```

To remove the last element from the list, you can use the pop() method as follows:

```python
last_number = numbers.pop()
```

**Slicing:**

You can create a new list that contains a subset of elements from an existing list by using slicing. Slicing allows you to select a range of elements from the list. For example, to create a new list that contains the first three elements of the original list, you can use the following code:

```python
subset = numbers[0:3]
```

**Iterating through a List:**

You can iterate through all the elements in a list using a for loop. For example, to print all the numbers in the list, you can use the following code:

```python
for number in numbers:
    print(number)
```

**List Comprehension:**

List comprehension is a concise way of creating a new list by performing operations on existing elements. It is a powerful feature of Python. For example, to create a new list that contains the square of each element in the original list, you can use the following code:

```python
squares = [number**2 for number in numbers]
```

**Nested Lists**

A nested list is a list that contains one or more other lists as elements. This means that each element of a list can itself be a list. Nested lists can be used to represent a wide variety of data structures, such as matrices, tables, and trees. Look at the example below:

```python
nested_list = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
```

In this example, `nested_list` is a list of three lists, each containing three integers. You can access individual elements of a nested list using indexing. For example, `nested_list[0][1]` would give you the value `2`, which is the second element of the first inner list.

You can also use loops to iterate over the elements of a nested list. For example, here's how you could use a nested loop to print out each element of the `nested_list`:

```python
for inner_list in nested_list:
    for element in inner_list:
        print(element)
```

Output:

```bash
1
2
3
4
5
6
7
8
9
```

**Strings:**

A string in Python is similar to a list in that both are sequences of elements. However, the elements in a string are characters, whereas the elements in a list can be any data type. Both strings and lists can be indexed and sliced, and can be iterated over using loops.

For example, you can access individual characters in a string using an index just like you would with a list:

```python
my_string = "Hello"
print(my_string[0]) # Output: H
```

Similarly, you can slice a string just like you would a list:

```python
my_string = "Hello, World!"
print(my_string[0:5]) # Output: Hello
```

You can also iterate over a string using a for loop:

```python
my_string = "Hello, World!"
for char in my_string:
    print(char)
```

Output:

```bash
H
e
l
l
o
,
 
W
o
r
l
d
!
```


**In and Not Operators:**

The `in` and `not` in operators are used to check if a value is a member of a sequence (in this case a list). Here's an example of how you might use them without a list:

```python
# Using "in" without a list
my_string = "hello world"
if "h" in my_string:
    print("The letter h is in the string.")
else:
    print("The letter h is not in the string.")
```

In this example, we check if the letter "h" is in the `my_string` variable. Since it is, we print "The letter h is in the string."

Similarly, we can use `not in` to check if a value is not in a sequence:

```python
# Using "not in" without a list
my_string = "hello world"
if "z" not in my_string:
    print("The letter z is not in the string.")
else:
    print("The letter z is in the string.")
```

In this example, we check if the letter "z" is not in the `my_string` variable. Since it is not, we print "The letter z is not in the string."



**More Complex Examples**

Here is an example which includes everything we have discussed:

```python
# create a list
my_list = [10, 20, 30, 40, 50]

# add an element to the end of the list
my_list.append(60)
print(my_list) # output: [10, 20, 30, 40, 50, 60]

# insert an element at a specific position
my_list.insert(2, 15)
print(my_list) # output: [10, 20, 15, 30, 40, 50, 60]

# remove an element from the list
my_list.remove(15)
print(my_list) # output: [10, 20, 30, 40, 50, 60]

# remove the last element from the list and return it
last_element = my_list.pop()
print(last_element) # output: 60
print(my_list) # output: [10, 20, 30, 40, 50]

# reverse the order of the elements in the list
my_list.reverse()
print(my_list) # output: [50, 40, 30, 20, 10]

# sort the elements in the list in ascending order
my_list.sort()
print(my_list) # output: [10, 20, 30, 40, 50]

# create a new list by slicing the original list
new_list = my_list[1:4]
print(new_list) # output: [20, 30, 40]

# check if an element is in the list
if 20 in my_list:
    print("20 is in the list")
else:
    print("20 is not in the list")

# get the length of the list
print(len(my_list)) # output: 5
```

### 2.5.2 Tuples

A tuple is another built-in data structure in Python that is similar to a list, but with some key differences. Like a list, a tuple is a collection of values, but unlike a list, a tuple is immutable, which means that once it is created, its values cannot be changed. Tuples are created using parentheses () and commas to separate the values.

Here are some examples of tuples:

```python
# creating a tuple
my_tuple = (1, 2, 3)
print(my_tuple)  # output: (1, 2, 3)

# creating a tuple with different data types
my_tuple2 = ('apple', 2, True)
print(my_tuple2)  # output: ('apple', 2, True)
```

Once a tuple is created, its values cannot be changed, which means you cannot add, remove or modify its elements. However, you can access its elements using indexing and slicing just like you would with a list. Here are some examples:


```python
# accessing tuple elements
my_tuple = ('apple', 'banana', 'cherry')
print(my_tuple[0])  # output: 'apple'
print(my_tuple[-1])  # output: 'cherry'

# slicing tuples
print(my_tuple[1:])  # output: ('banana', 'cherry')
```

In addition to accessing the elements of a tuple, you can also use some built-in functions and methods to work with tuples. Here are a few examples:

```python
# getting the length of a tuple
my_tuple = (1, 2, 3, 4, 5)
print(len(my_tuple))  # output: 5

# concatenating tuples
tuple1 = (1, 2, 3)
tuple2 = (4, 5, 6)
new_tuple = tuple1 + tuple2
print(new_tuple)  # output: (1, 2, 3, 4, 5, 6)

# checking if an element exists in a tuple
my_tuple = ('apple', 'banana', 'cherry')
print('banana' in my_tuple)  # output: True

# counting the occurrence of an element in a tuple
my_tuple = ('apple', 'banana', 'cherry', 'banana')
print(my_tuple.count('banana'))  # output: 2

# getting the index of an element in a tuple
my_tuple = ('apple', 'banana', 'cherry')
print(my_tuple.index('banana'))  # output: 1
```

In summary, tuples are similar to lists in that they are both collections of values, but tuples are immutable, which means they cannot be modified after they are created. Tuples are created using parentheses and commas, and their elements can be accessed using indexing and slicing just like with lists. Tuples also have some built-in functions and methods that can be used to work with them.


### 2.5.3 Dictionaries

A dictionary is a collection of key-value pairs, where each key is associated with a value. Dictionaries are useful for storing and retrieving data in a structured way. In Python, dictionaries are created using curly braces ({}) and colons (:).

**Creating a dictionary**

To create a dictionary, you can use the following syntax:

```python
my_dict = {key1: value1, key2: value2, key3: value3}
```

Here is an example:

```python
person = {'name': 'John', 'age': 25, 'city': 'New York'}
```

In this example, `person` is a dictionary with three keys: 'name', 'age', and 'city', and their respective values: 'John', 25, and 'New York'.


**Accessing values in a dictionary**

You can access the values in a dictionary by using the keys. To access the value associated with a particular key, you can use the following syntax:

```python
my_dict[key]
```

Here is an example:


```python
print(person['name']) # Output: John
```

You can also use the `get()` method to access the values in a dictionary. The `get()` method returns None if the key does not exist in the dictionary.


**Adding and modifying items in a dictionary**

To add or modify an item in a dictionary, you can use the following syntax:

```python
my_dict[key] = value
```

Here is an example:

```python
person['email'] = 'john@example.com'
person['age'] = 26
```

In this example, we added a new key-value pair to the `person` dictionary, and also modified the value associated with the 'age' key.

**Removing items from a dictionary**

To remove an item from a dictionary, you can use the del keyword, followed by the key that you want to remove.

Here is an example:

```python
del person['city']
```

In this example, we removed the key-value pair associated with the 'city' key from the `person` dictionary.


**Looping through a dictionary**

You can loop through a dictionary using the for loop. By default, the for loop will loop through the keys of the dictionary. To loop through the values, you can use the values() method. To loop through both the keys and the values, you can use the items() method.

Here is an example:


```python
for key in person:
    print(key, person[key])

for value in person.values():
    print(value)

for key, value in person.items():
    print(key, value)
```

In this example, we looped through the `person` dictionary using three different methods: looping through the keys, looping through the values, and looping through both the keys and the values.


**Dictionary methods**

Python provides several useful methods for working with dictionaries. Here are some of the most commonly used methods:

1. `clear()`: Removes all key-value pairs from the dictionary.

```python
my_dict = {"name": "John", "age": 30}
my_dict.clear()
print(my_dict)  # Output: {}
```

2. `copy()`: Returns a shallow copy of the dictionary.

```python
my_dict = {"name": "John", "age": 30}
new_dict = my_dict.copy()
print(new_dict)  # Output: {"name": "John", "age": 30}
```

3. `get(key, default)`: Returns the value of the specified key. If the key does not exist, it returns the specified default value.

```python
my_dict = {"name": "John", "age": 30}
print(my_dict.get("name"))  # Output: "John"
print(my_dict.get("address", "Unknown"))  # Output: "Unknown"
```

4. `items()`: Returns a list of key-value pairs in the dictionary.

```python
my_dict = {"name": "John", "age": 30}
print(my_dict.items())  # Output: [("name", "John"), ("age", 30)]
```

5. `keys()`: Returns a list of all keys in the dictionary.

```python
my_dict = {"name": "John", "age": 30}
print(my_dict.keys())  # Output: ["name", "age"]
```

6. `values()`: Returns a list of all values in the dictionary.

```python
my_dict = {"name": "John", "age": 30}
print(my_dict.values())  # Output: ["John", 30]
```

To see more dictionary methods, read the python documentation.

Here's an example that demonstrates the various operations that can be performed on a dictionary:

```python
# Creating an empty dictionary
my_dict = {}

# Adding key-value pairs
my_dict['name'] = 'John'
my_dict['age'] = 25
my_dict['gender'] = 'male'

# Accessing values using keys
print(my_dict['name'])   # Output: John

# Updating values
my_dict['age'] = 30

# Removing key-value pairs
del my_dict['gender']

# Checking if a key exists in the dictionary
if 'age' in my_dict:
    print('Age is present in the dictionary')
else:
    print('Age is not present in the dictionary')

# Looping through keys and values
for key, value in my_dict.items():
    print(key + ': ' + str(value))

# Clearing the dictionary
my_dict.clear()
```

In this example, we first create an empty dictionary `my_dict`. We then add some key-value pairs to it using the syntax `my_dict[key] = value`. We access the value of a key using the syntax` my_dict[key]`. We update a value by reassigning it using the syntax `my_dict[key] = new_value`. We delete a key-value pair using the `del` keyword followed by the dictionary name and the key to be deleted (`del my_dict[key]`).

We can check if a key exists in the dictionary using the `in` keyword (`if key in my_dict:`). We can loop through the keys and values of a dictionary using the `items()` method. Finally, we can clear the dictionary using the `clear()` method.


## 2.6 Functions

In Python, a function is a named block of code that performs a specific task. It allows you to group together a set of instructions that can be called multiple times within a program, making it easier to reuse code and avoid repeating yourself.

A function typically takes some input (known as arguments or parameters), processes the input, and then returns a result. The input can be of any data type, including other functions, and the output can also be of any data type.

Functions in Python are defined using the keyword `def`, followed by the function name, a set of parentheses (which may contain arguments), and a colon. The body of the function is then indented and contains the instructions that make up the function.

Here's a simple example of a function that takes two arguments and returns their sum:

```python
def add_numbers(a, b):
    sum = a + b
    return sum
```

In this example, `add_numbers` is the name of the function, and it takes two arguments, `a` and `b`. Inside the function, the values of `a` and `b` are added together and stored in a variable called `sum`. The `return` statement then sends the value of `sum` back to the code that called the function.

To call a function, you simply write its name followed by the arguments you want to pass in parentheses. For example:

```python
result = add_numbers(3, 4)
print(result)  # Output: 7
```
In this case, the `add_numbers` function is called with arguments `3` and `4`, and the value `7` is returned and assigned to the variable `result`. This value is then printed to the console.

**More complex example:**

Here's an example of a function that takes a list of numbers as input and returns the sum of all even numbers in the list:

```python
def sum_even_numbers(numbers):
    """
    Given a list of numbers, return the sum of all even numbers in the list.
    """
    total = 0
    for number in numbers:
        if number % 2 == 0:
            total += number
    return total
```

Here, the function `sum_even_numbers` takes one parameter, `numbers`, which is expected to be a list of numbers. Inside the function, a variable `total` is initialized to 0, which will store the sum of all even numbers in the list.

Next, we use a `for` loop to iterate over each number in the list. For each number, we check if it is even by using the modulo operator (`%`) to check if the remainder of the number divided by 2 is 0. If the number is even, we add it to the `total` variable.

Finally, we return the `total` variable as the output of the function.

Here's an example of calling the function and printing the result:

```bash
numbers = [1, 2, 3, 4, 5, 6]
even_sum = sum_even_numbers(numbers)
print(even_sum)  # Output: 12
```

In this example, the function is called with the `numbers` list as input, and the output is assigned to the variable `even_sum`. The result is then printed, which should be the sum of all even numbers in the list, i.e., 2 + 4 + 6 = 12.

Here is another example in which a function is needed to run a block of code more than once:

```python
def get_grade(score):
    if score >= 90:
        letter_grade = "A"
    elif score >= 80:
        letter_grade = "B"
    elif score >= 70:
        letter_grade = "C"
    elif score >= 60:
        letter_grade = "D"
    else:
        letter_grade = "F"
    return letter_grade

score1 = 85
score2 = 72
score3 = 95

grade1 = get_grade(score1)
grade2 = get_grade(score2)
grade3 = get_grade(score3)

print(f"Score: {score1}, Grade: {grade1}")
print(f"Score: {score2}, Grade: {grade2}")
print(f"Score: {score3}, Grade: {grade3}")
```

Output:

```bash
Score: 85, Grade: B
Score: 72, Grade: C
Score: 95, Grade: A
```

Additionally, you can also return more than one value in a function, which is demonstrated below:

```python
def calculate_rectangle_properties(width, height):
    area = width * height
    perimeter = 2 * (width + height)
    diagonal = (width**2 + height**2)**0.5
    return area, perimeter, diagonal
```

In this function, we calculate the area, perimeter, and diagonal of a rectangle based on its width and height. Instead of returning these values as separate variables, we use the tuple packing feature of Python to return them as a single tuple.

Here's an example of how we can call this function and unpack the returned values:

```python
w = 5
h = 7
a, p, d = calculate_rectangle_properties(w, h)
print(f"The area of a rectangle with width {w} and height {h} is {a}.")
print(f"The perimeter of the rectangle is {p}.")
print(f"The length of the diagonal is {d}.")
```

Output:

```bash
The area of a rectangle with width 5 and height 7 is 35.
The perimeter of the rectangle is 24.
The length of the diagonal is 8.602325267042627.
```

**More Complex Example**

Here is an example of how functions may be used:

```python
# function to find the sum of a list of numbers
def find_sum(num_list):
    sum = 0
    for num in num_list:
        sum += num
    return sum

# function to find the product of a list of numbers
def find_product(num_list):
    product = 1
    for num in num_list:
        product *= num
    return product

# function to find the maximum number in a list
def find_max(num_list):
    max_num = num_list[0]
    for num in num_list:
        if num > max_num:
            max_num = num
    return max_num

# function to find the minimum number in a list
def find_min(num_list):
    min_num = num_list[0]
    for num in num_list:
        if num < min_num:
            min_num = num
    return min_num

# main program
numbers = [3, 7, 2, 8, 4, 5]

# find the sum of the numbers
sum = find_sum(numbers)
print("The sum of the numbers is:", sum)

# find the product of the numbers
product = find_product(numbers)
print("The product of the numbers is:", product)

# find the maximum number
max_num = find_max(numbers)
print("The maximum number is:", max_num)

# find the minimum number
min_num = find_min(numbers)
print("The minimum number is:", min_num)
```

In this example, we define four different functions: `find_sum`, `find_product`, `find_max`, and `find_min`. These functions take a list of numbers as input, perform a specific operation on the numbers, and return a single result.

In the main program, we create a list of numbers and call each of these functions to perform different operations on the list. Finally, we print out the results of each function.



### 2.6.1 Built-in Functions

In Python, a built-in function is a pre-defined function that is included in the Python interpreter by default. These functions are available to be used in any Python program without having to define them first.

Built-in functions work similarly to user-defined functions, but they are already implemented and available for use. You simply need to call the function with the appropriate arguments to use it.

An example of a built-in function that we have used multiple times thus far is the `print()` function. 

Here are some examples of some more built-in functions in Python:

1. `len()` - returns the length of an object (e.g. string, list, tuple, etc.)

```python
my_string = "Hello World!"
my_list = [1, 2, 3, 4, 5]

print(len(my_string)) # Output: 12
print(len(my_list)) # Output: 5
```

2. `max()` and `min()` - returns the maximum and minimum value in a sequence

```python
my_list = [5, 10, 15, 20]

print(max(my_list)) # Output: 20
print(min(my_list)) # Output: 5
```

3. `range()` - generates a sequence of numbers

```python
# Using only stop argument
for num in range(5):
    print(num) # Output: 0 1 2 3 4
    
# Using start and stop arguments
for num in range(2, 7):
    print(num) # Output: 2 3 4 5 6
    
# Using start, stop, and step arguments
for num in range(0, 11, 2):
    print(num) # Output: 0 2 4 6 8 10
```

There are mamy more built-in functions and to see them, refer to the python documentation.

## 2.7 String Manipulation

String manipulation refers to the process of modifying or transforming a given string in a desired way. In Python, strings are an essential data type that are used to represent text-based data. There are many scenarios where we may need to manipulate strings, such as cleaning up user inputs, formatting strings, parsing data from text files, or generating dynamic outputs for user interfaces. Python provides a variety of built-in methods and functions that enable us to perform different kinds of string manipulations. By using these methods, we can easily accomplish tasks such as splitting and joining strings, replacing or removing characters, converting cases, and checking for substring occurrences. By mastering string manipulation techniques, we can improve our ability to work with text-based data and develop more robust and effective Python programs.

### 2.7.1 Single vs Double Quotes

In Python, you can create strings using either single quotes or double quotes. Both are interchangeable and can be used to define a string. However, if your string contains an apostrophe, it is best to use double quotes to define the string, and vice versa. Here is an example below:

```python
print("Chris's dog jumped over the fence")
```

Output:

```
Chris's dog jumped over the fence
```

In this case, a singular apostrophe can be used inside the string as the string is covered by a double apostrophe. However, if not, it would have to be done as follows:

```python
print('I\'m happy')
```

Output:

```
I'm happy
```

### 2.7.2 Newline

The `\n` characters are used to create a new line in a string. For example, if you want to print two sentences on separate lines, you can use `\n`.

```python
print("Hello\nWorld")
```

Output:

```bash
Hello
World
```

### 2.7.3 Tabs

The `\t` characters are used to create a tab in a string.  For example, if you want to create a tab space between two words, you can use \t.

```python
print("Hello\tWorld")
```

Output:

```bash
Hello World
```

### 2.7.4 Triple Quotations


Triple quotes are used to create multiline strings in Python. Unlike single quotes or double quotes, triple quotes allow you to create strings that span multiple lines. To create a multiline string using triple quotes, you simply enclose the entire string in three consecutive single quotes ('''). You can also use three consecutive double quotes (""") to achieve the same effect.

Triple quotes are particularly useful when you need to create long strings that span multiple lines, such as docstrings or large blocks of text. They allow you to easily include line breaks and formatting within your strings without having to use escape characters or concatenation. Additionally, triple-quoted strings can be used as a comment or to temporarily disable code.


```python
multiline_string = """This is a multiline string.
It can span multiple lines
without needing to use escape characters."""

print(multiline_string)
```

Output:

```bash
This is a multiline string.
It can span multiple lines
without needing to use escape characters.
```

### 2.7.5 Built-in Functions

Now, let's look at the many ways you can manipulate a string using built-in functions.


1. **Concatenation**: Concatenation is the process of joining two or more strings together. In Python, you can concatenate strings using the `"+"` operator. For example:

```python
string1 = "Hello"
string2 = "World"
result = string1 + " " + string2
print(result) # Output: "Hello World"
```

2. **Slicing**: Slicing is the process of selecting a portion of a string. In Python, you can slice a string using the square brackets `[]`. For example:

```python
string = "Hello World"
result = string[0:5]
print(result) # Output: "Hello"
```

3. **Upper** and **Lower** Case Conversion: In Python, you can convert a string to upper or lower case using the `upper()`and `lower()` methods. For example:

```python
string = "Hello World"
result1 = string.upper()
result2 = string.lower()
print(result1) # Output: "HELLO WORLD"
print(result2) # Output: "hello world"
```

4. **Replace**: The `replace()` method is used to replace a portion of a string with another string. For example:

```python
string = "Hello World"
result = string.replace("World", "Universe")
print(result) # Output: "Hello Universe"
```

5. **Split**: The `split()` method is used to split a string into a list of substrings based on a specified delimiter. For example:

```python
string = "Hello,World"
result = string.split(",")
print(result) # Output: ["Hello", "World"]
```

6. **Join**: The `join()` method is used to join a list of strings into a single string using a specified delimiter. For example:

```python
list = ["Hello", "World"]
delimiter = " "
result = delimiter.join(list)
print(result) # Output: "Hello World"
```
7. **Upper**. The `upper()` method returns a new string with all characters in uppercase. It does not modify the original string. Example:

```python
s = "hello world"
s_upper = s.upper()  # "HELLO WORLD"
```
8. **Lower**. The `lower()` method returns a new string with all characters in lowercase. It does not modify the original string. Example:

```python
s = "HeLLo WoRLd"
s_lower = s.lower()  # "hello world"
```

There are many more built-in functions that can help you manipualte strings. To learn more about them, read the documentation on string manipulation.

**More complex example**

Here is an example of how the previously discussed string manipulation methods may be used:

```python
# Original string
text = "   This is some text to manipulate!   "

# Remove leading and trailing white space
text = text.strip()

# Convert all characters to lowercase
text = text.lower()

# Replace all occurrences of "some" with "new"
text = text.replace("some", "new")

# Split the string into a list of words
words = text.split()

# Loop through the list and capitalize the first letter of each word
capitalized_words = []
for word in words:
    capitalized_words.append(word.capitalize())

# Join the list of words back into a string
text = " ".join(capitalized_words)

# Add an exclamation mark to the end of the string
text = text + "!"

# Print the final string
print(text)
```

This code snippet takes an original string, manipulates it in multiple ways, and then prints the final result. The steps involved are:

- Remove leading and trailing white space using the `strip()` method.
- Convert all characters to lowercase using the `lower()` method.
- Replace all occurrences of "some" with "new" using the `replace()` method.
- Split the string into a list of words using the `split()` method.
- Loop through the list of words, capitalize the first letter of each word, and add the result to a new list using the `capitalize()` method.
- Join the list of capitalized words back into a string using the `join()` method.
- Add an exclamation mark to the end of the string.
- Print the final result.

The final output of this code would be:

```bash
New Text To Manipulate!
```

## 2.8 Modules

### 2.8.1 What are Python modules?

Python modules are pre-written code libraries that can be imported and used in your Python program. These modules can contain functions, variables, and classes that you can use to add functionality to your programs without having to write everything from scratch.


### 2.8.2 How to use Python modules?

To use a Python module, you need to first import it into your program using the import keyword. Once imported, you can use the functions and variables defined in the module by prefixing them with the module name. For example, if you want to use the math module to calculate the square root of a number, you would use the code `import math` at the top of your file, then `math.sqrt(number)` to calculate the square root. Here is an example of how to import a built-in python module:

```python
import random

# Generate a random number between 1 and 10
num = random.randint(1, 10)
print(num)
```


### 2.8.3 Common Python modules

Python comes with a number of built-in modules that you can use, such as the math module, which provides functions for mathematical operations, or the os module, which provides functions for interacting with the operating system. There are also many third-party modules available that you can install and use in your programs, such as NumPy for scientific computing, Flask for web development, or Pygame for game development.

### 2.8.4 Installing Python modules

To install third-party Python modules, you can use a package manager such as pip. Pip allows you to easily search for, install, and manage Python packages. To install a package using pip, you can use the command `pip install package_name`. For example, to install the NumPy package, you would use the command `pip install numpy`. Here is an example on how to install and use a python module:

```python
# First, you need to install the module using pip
# pip install requests

import requests

# Make a GET request to a URL and print the response content
response = requests.get('https://www.google.com')
print(response.content)
```

### 2.8.5 Creating your own modules

You can also create your own Python modules to organize your code and make it more reusable. To create a module, simply save your code to a .py file and import it into your program using the import keyword. You can then use the functions and variables defined in your module just like any other module.


**More complex example**

```python
import math
import random

# Generate a random number between 1 and 100
random_number = random.randint(1, 100)
print("Random number: ", random_number)

# Calculate the square root of the random number
sqrt_num = math.sqrt(random_number)
print("Square root of random number: ", sqrt_num)
```

In this example, we're importing two modules: `math` and `random`. The random module is used to generate a random integer between 1 and 100, while the `math` module is used to calculate the square root of that random integer. We then print both the random number and its square root.


## 2.9 Exceptions

In programming, an exception is an event that disrupts the normal flow of the program's instructions. When an exception occurs, the program will stop executing unless the exception is handled. Python provides a way to handle exceptions using try-except blocks.

### 2.9.1 Try and Except

To handle exceptions in Python, we use a try-except block. A try block is where we put the code that we think might cause an exception. The except block is where we handle the exception. Here's the basic syntax of a try-except block:

```python
try:
   # code that might cause an exception
except ExceptionType:
   # code to handle the exception
```

The `try` block executes normally until an exception occurs. If an exception occurs, the code inside the `try` block stops executing, and the code inside the `except` block is executed. The `except` block catches the exception and allows the program to continue running. Here's an example of try-except:

```python
try:
    numerator = int(input("Enter the numerator: "))
    denominator = int(input("Enter the denominator: "))
    result = numerator / denominator
    print("Result: ", result)
except ValueError:
    print("Please enter valid integers for the numerator and denominator.")
except ZeroDivisionError:
    print("Cannot divide by zero!")
```

In this example, we use try-except to handle potential errors that might occur when dividing two numbers. If the user enters a non-integer value for either the numerator or denominator, a `ValueError` will be raised. If the user enters 0 for the denominator, a `ZeroDivisionError` will be raised. By using try-except, we can gracefully handle these errors and provide helpful feedback to the user


### 2.9.2 Types of Exceptions

In Python, there are many types of exceptions that can occur. Here are some common exceptions:

- `TypeError`: raised when an operation or function is applied to an object of inappropriate type.
- `ValueError`: raised when a built-in operation or function receives an argument that has the right type but an inappropriate value.
- `NameError`: raised when a local or global name is not found.
- `IOError`: raised when an I/O operation (such as reading or writing to a file) fails.

### 2.9.3 Raising Exceptions

We can also raise exceptions ourselves using the `raise` keyword. Here's an example:

```python
x = -1

if x < 0:
    raise ValueError("x cannot be negative")
```

This will raise a `ValueError` exception with the message "x cannot be negative".

Exception handling is an important part of writing robust and reliable code in Python. By using try-except blocks and raising exceptions, we can write code that gracefully handles errors and allows the program to continue running.

## 2.10 Classes

### 2.10.1 Introduction to Classes

Python is an object-oriented programming language. This means that it provides features that support object-oriented programming (OOP). One of the most important features of Python is the ability to define classes, which are templates for creating objects. Classes define the properties and methods of objects, and allow you to create new instances of those objects.

### 2.10.2 What is a Class?

A class is a blueprint for creating objects. It defines a set of attributes and methods that describe the behavior of the objects created from it.

In Python, a class is defined using the `class` keyword, followed by the name of the class. By convention, class names are capitalized. For example:

```python
class MyClass:
    pass
```

This defines a new class named `MyClass`. The `pass` keyword is used to indicate that the class is empty, but it can be replaced with any valid Python code.

### 2.10.3 What is an Object?

An object is an instance of a class. It is created from the blueprint defined by the class. Every object has its own set of attributes, which are specific to that object, and its own methods, which allow it to perform actions.

To create an object in Python, you use the `class` keyword followed by the name of the class, followed by parentheses. For example:

```python
my_object = MyClass()
```

This creates a new instance of the `MyClass` class and assigns it to the variable `my_object`.

### 2.10.4 Class Attributes

A class can have attributes, which are properties that are common to all instances of the class. Class attributes are defined inside the class definition, but outside any methods.

```python
class MyClass:
    class_attribute = "Hello, World!"
```

This defines a class named `MyClass` with a class attribute named `class_attribute`.

### 2.10.5 Instance Attributes

An instance attribute is a property that is specific to an instance of a class. Instance attributes are defined inside the `__init__()` method of the class.

```python
class MyClass:
    def __init__(self, instance_attribute):
        self.instance_attribute = instance_attribute
```

This defines a class named `MyClass` with an instance attribute named `instance_attribute`.


### 2.10.6 Methods

A method is a function that is associated with a class. It can be called on an instance of the class, and can access the instance attributes and class attributes of that instance.

Methods are defined inside the class definition, just like functions, but they have a special first parameter called `self`. This parameter refers to the instance of the class that the method is being called on.

```python
class MyClass:
    class_attribute = "Hello, World!"
    
    def __init__(self, instance_attribute):
        self.instance_attribute = instance_attribute
        
    def instance_method(self):
        print("This is an instance method.")
        
    @classmethod
    def class_method(cls):
        print("This is a class method.")
        
    @staticmethod
    def static_method():
        print("This is a static method.")
```

This defines a class named `MyClass` with three methods: `instance_method()`, `class_method()`, and `static_method()`.

- `instance_method()` is an instance method, which can be called on an instance of the class.

- `class_method()` is a class method, which can be called on the class itself. It has a special first parameter called cls, which refers to the class.

- `static_method()` is a static method, which is not associated with any instance or class. It is like a regular function, but it is defined inside the class.


### 2.10.7 Inheritance

Inheritance is a powerful feature of object-oriented programming. It allows you to create new classes based on existing ones, inheriting their attributes and methods while also adding new ones or overriding existing ones. This allows for code reusability, modularity, and flexibility.

Inheritance is based on the concept of a parent-child relationship, where the parent class is the base class from which the child classes inherit attributes and methods. The child classes are also known as derived classes.

To inherit from a parent class, you simply define the child class and include the parent class name in parentheses after the child class name. For example, if we have a parent class called "Animal", we can define a child class called "Dog" that inherits from "Animal" like this:

```python
class Animal:
    def __init__(self, name):
        self.name = name

    def make_sound(self):
        pass

class Dog(Animal):
    def __init__(self, name, breed):
        super().__init__(name)
        self.breed = breed

    def make_sound(self):
        return "Woof!"
```

In this example, the `Dog` class inherits the `__init__` method and `make_sound` method from the `Animal` class. However, the `Dog` class also has its own `__init__` method that takes an additional argument for the `breed` and overrides the `make_sound` method to return "Woof!".

The `super()` function is used to call the parent class's `__init__` method to initialize the inherited attributes.

We can create instances of the `Animal` and `Dog` classes and call their methods like this:

```python
animal = Animal("Unknown")
dog = Dog("Fido", "Labrador")

print(animal.name)  # Output: Unknown
print(dog.name)  # Output: Fido
print(dog.breed)  # Output: Labrador

print(animal.make_sound())  # Output: None
print(dog.make_sound())  # Output: Woof!
```

In this example, we create an instance of the `Animal` class and the `Dog` class. We can access the `name` attribute of both instances, but only the `Dog` instance has a `breed` attribute. We can also call the `make_sound` method of both instances, but the `Dog` instance returns "Woof!" while the `Animal` instance returns `None` because it doesn't have an implementation of the method.

In conclusion, inheritance is a powerful and essential feature of object-oriented programming. It allows for code reusability, modularity, and flexibility. By defining parent classes with shared attributes and methods, we can create child classes that inherit those attributes and methods while also adding new ones or overriding existing ones.

**More Complex Example**

Let's consider an example of a bank account management system. We can create a class called `BankAccount` that represents a customer's bank account. Here's an example implementation:

```python
class BankAccount:
    def __init__(self, account_number, balance=0):
        self.account_number = account_number
        self.balance = balance
    
    def deposit(self, amount):
        self.balance += amount
    
    def withdraw(self, amount):
        if amount > self.balance:
            print("Insufficient funds")
        else:
            self.balance -= amount
    
    def display_balance(self):
        print(f"Account number: {self.account_number}\nBalance: {self.balance}")
```

In this implementation, we define the `BankAccount` class with an `__init__` method that takes in an `account_number` and `balance` as arguments. `balance` is an optional argument that defaults to 0 if no balance is specified.

We then define three methods: `deposit`, `withdraw`, and `display_balance`. The `deposit` method adds the specified `amount` to the account's balance, the `withdraw` method subtracts the specified `amount` from the account's balance, but only if the balance is sufficient. If not, it prints an error message. The `display_balance` method simply displays the account's current balance and account number.

With this class, we can create instances of `BankAccount` for each customer and manage their accounts. Here's an example usage:

```python
# create a new bank account with account number 123 and initial balance of 1000
account1 = BankAccount(123, 1000)

# deposit 500 into account1
account1.deposit(500)

# withdraw 200 from account1
account1.withdraw(200)

# display the balance of account1
account1.display_balance()
```

This will output:

```bash
Account number: 123
Balance: 1300
```

In this way, we can use classes to model real-world systems and objects and provide a structured and organized way to manage them.



## 2.11 Reading and Writing Files

Reading and writing files is a common task in programming. In Python, it's easy to read and write files using built-in functions.

### 2.11.1 Opening a File

To open a file, you use the built-in `open()` function. The `open()` function takes two arguments: the path to the file and the mode in which you want to open the file. The mode can be "r" for reading, "w" for writing (which will erase the file's contents), "a" for appending, "x" for creating a new file, or "b" for binary mode.

Here's an example of opening a file for reading:

```python
file = open("example.txt", "r")
```

### 2.11.2 Reading a File

Once you've opened a file for reading, you can read its contents using various methods. The most common method is `read()`, which returns the entire contents of the file as a string. You can also use `readline()` to read one line at a time or `readlines()` to read all the lines of the file into a list.

```python
file = open("example.txt", "r")
content = file.read()
print(content)
```

This will print the contents of the file to the console.

```python
file = open("example.txt", "r")
line = file.readline()
while line:
    print(line)
    line = file.readline()
```

This will print all the lines of the file to the console as a list.


To read a file line by line, we can use a loop and the `readline()` method.

```python
file = open("example.txt", "r")
for line in file:
    print(line)
file.close()
```



### 2.11.3 Writing to a File

To write to a file, you open it in "w" or "a" mode and use the `write()` method to write to it. If you're writing multiple lines, you can use the `writelines()` method.

```python
file = open("example.txt", "w")
file.write("This is a test.")
file.close()
```

This will erase the contents of the file and write "This is a test." to it.

```python
file = open("example.txt", "a")
file.write("This is another test.")
file.close()
```

This will append "This is another test." to the end of the file.

To write to a file line by line, we can use a loop and the `write()` method.

```python
lines = ["This is line 1.\n", "This is line 2.\n", "This is line 3.\n"]
file = open("example.txt", "w")
for line in lines:
    file.write(line)
file.close()
```



### 2.11.4 Closing a File

It's important to always close a file after you're done with it. You can do this using the `close()` method.

```python
file = open("example.txt", "r")
content = file.read()
file.close()
```

This will close the file after reading its contents.

### 2.11.5 Using "with" Statement

Another way to work with files is to use the with statement. This ensures that the file is closed properly, even if an error occurs.

```python
with open("example.txt", "r") as file:
    content = file.read()
```

This will read the contents of the file and automatically close it when the `with` block is exited.


### 2.11.6 Handling Exceptions

When working with files, it's important to handle exceptions that may occur. For example, if you try to open a file that doesn't exist, you'll get a `FileNotFoundError`. You can handle this exception using a try-except block.

```python
try:
    with open("example.txt", "r") as file:
        content = file.read()
except FileNotFoundError:
    print("File not found.")
```

This will print "File not found." if the file doesn't exist.

**More Complex Example**

Let's say we have a file called "input.txt" that contains a list of names, one name per line. We want to read in the file, sort the names alphabetically, and then write the sorted names to a new file called "output.txt". Here's how we can do it:

```python
# Open the input file for reading
with open('input.txt', 'r') as f:
    # Read in all the names and store them in a list
    names = f.read().splitlines()

# Sort the names alphabetically
names.sort()

# Open the output file for writing
with open('output.txt', 'w') as f:
    # Write the sorted names to the output file, one name per line
    for name in names:
        f.write(name + '\n')
```

In this example, we first open the input file for reading using the `open()` function and the `'r'` mode. We then read in all the names from the file using the `read()` method and split them into a list using the `splitlines()` method. We close the file automatically using a with statement.

Next, we sort the names alphabetically using the `sort()` method.

Finally, we open the output file for writing using the `open(`) function and the `'w'` mode. We then write the sorted names to the file using a for loop and the `write()` method, making sure to add a newline character (`'\n'`) after each name. We close the file automatically using a `with` statement.





# 3. Pracice Questions


## 3.1 Variables

1. What is the output of the following code?

```python
x = 5
y = 3
print("The value of x is", x, "and the value of y is", y)
```

<details>
Answer
</details>