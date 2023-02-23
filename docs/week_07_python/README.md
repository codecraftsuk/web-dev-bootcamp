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


### 2.4.2 Comparative Operators

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

### 2.4.3 Logical Operators

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

### 2.4.4 Conditional Statements

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

### 2.4.5 Loops

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






