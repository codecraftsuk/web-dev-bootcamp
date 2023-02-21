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

The `"Hello, World!"` program is a simple program that is often used as a first example when learning a new programming language. The purpose of the program is to output the string `"Hello, World!"` to the console, which is a basic way to demonstrate that the language is working correctly.

In our "Hello, World!" program, we pass a single argument to the print function: the string "Hello, World!".

Strings are a fundamental data type in Python, and they are used to represent text. A string is a sequence of characters that are enclosed in quotes, either single quotes (') or double quotes ("). In our program, we use double quotes to enclose the string "Hello, World!".

When we run the "Hello, World!" program in Python, the print function outputs the string "Hello, World!" to the console. The console is a text-based interface where we can interact with the Python interpreter, and it is often used for debugging and testing programs.

Overall, the "Hello, World!" program is a simple and effective way to demonstrate the basic syntax and functionality of Python. It provides a foundation for learning more advanced concepts, such as variables, data types, and control structures, which are essential for writing more complex programs.

# 2. Syntax