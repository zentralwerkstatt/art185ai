# Python Tutorial for Machine Learning I

## Introduction

From the official Python docs:

> Python is an easy to learn, powerful programming language. It has efficient high-level data structures and a simple but effective approach to object-oriented programming. Python’s elegant syntax and dynamic typing, together with its interpreted nature, make it an ideal language for scripting and rapid application development in many areas on most platforms.

These are the reasons why we -- and many machine learning researchers have chosen, and continue to choose Python for machine learning.

We will very losely follow the official Python 3.7 tutorial which is available here: https://docs.python.org/3/tutorial/index.html. This document, however, will only contain the parts of the language that we explicitly discuss in class.

Python is a well-documented language. Everything you need to know about the core langauge is in the official [docs](https://docs.python.org/3), and everything you need to know about the few libaries we will actively use can be found in their respective docs.

## Variables

While the technical reality is a bit more complicated, we can regard variables as *signs that holds a values*. In Python, we can assign a value to a sign with the equality sign: `a = 1`. Variables can hold many different kinds of values, integers (`a = 1`), floating point numbers (`a = 1.5`), characters (`a = 'a'`), words (`a = 'foo'`), truth values (`True`or `False`) vectors, matrices, or even complicated structures made up of many different kinds of values, called objects. Python is a [weakly-typed](https://en.wikipedia.org/wiki/Type_system) language. In practice, this means that we do not have to tell the interpreter what kind of value we are assigning to a sign, it will infer this for us.

There are many different way to "look into" a variable, i.e. see what value it is holding at a certain point in the execution of the program. A very easy way is to just print its value to the console/notebook. In Python, we use the `print` function for this purpose: `print(a)`.

## Algebra with Variables

As variables can hold values, we can use them algebraically, almost exactly like we would without a computer. For instance, we could calculate the sum of `a=4`and `b=2` by assigning it to `c`: `c=a+b`. `print`ing c will give us the result: `6`. Many other algebraic operations are possible:

- `print(a-b)`: 2
- `print(a*b)`: 8
- `print(a**b)`: 16
- `print(a/b)`: 2

We can also obtain truth values from algebraic statements using variables. For instance, to check for equality, we use the `==`operator:

- `print(a==b)`: False
- `print(a>b)`: True
- `print(a<b)`: False
- `print(a>=b)`: True
- `print(a<=b)`: False

## Functions

Functions are signs followed by any number of arguments in parentheses. One of the most often used functions is the print function that allows us to print the value of anything we pass to it as an argument. Note above that we do not have to evaluate a statement before passing it to the print function. Python and its libraries comes with many different functions.