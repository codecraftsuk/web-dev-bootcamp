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




