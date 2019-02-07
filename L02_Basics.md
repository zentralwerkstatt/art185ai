# Python for Machine Learning 2: Basics

## Lists

One of the most convenient things in Python is its handling of lists, a compound data type. You can put almost anything between square brackets and pass it to a function to process. Items in a list usually have the same type, although they can also be of different types. Here are lists of integers and strings, respectively:

- `int_list = [1, 2, 3, 4, 5]`
- `string_list = ['foo', 'bar', 'baz']`

The most important feature of lists and similar compound data types - one that we will encounter over and over - is *slicing*. Slicing a list means returning just a part of it. This is done with the colon operator. For instance, to just return the first element of our integer list, we can write `int_list[0]` (in programming, we are almost always counting from 0, not from 1). The second element can be returned by `int_list[1]`, etc.. But we can also access parts of lists in a more dynamic fashion:

- `print(int_list[:2])`: 1 2, the "first two" elements
- `print(int_list[2:])`: 3 4 5, everything but the "first two" elements
- `print(int_list[-2])`: 4, the "second to last" element

Lists are *mutable*, we can replace arbitrary elements by assigning a new value to them:

```
int_list[0] = 100
print(int_list)
```

will print `100 2 3 4 5`. We can also concatenate lists:

```
new_int_list = int_list[:2] + [int_list[-2:]
print(new_int_list)
```

will print `100 2 4 5`. Note that for all these examples we do not need to know how long the list is, or what is in it. If we *do* want to know how long a list is, we can use the `len` keyword: `len(new_int_list)` will return `4`. Slicing becomes more complicated but also more effective when we deal with multi-dimensional data types.

A word of caution: single items from lists are treated as simple types, not single-item lists. Concretely, this means that `int_list[2] + int_list[-2]` will not return a new list but a value. To avoid this, we can either add extra brackets when dealing with single-item lists (`[int_list[2]] + [int_list[-2]]`) or use the `append` keyword to append items to a list.

## Flow control: if...(then)...else

Do to anything productive you will need to control the flow of your program, i.e. you will need to control what is executed when (not in terms of time but in terms of order). In most cases, flow control decisions will be tied to the value of a variable. Accordingly, the most simple flow control measure you can take is to have the execution of a piece of code depend on the value of a variable. In Python, we use the if ... (then) ... else statements for this:

```
a = 0
if (a == 0): 
    print('A is zero')
else:
    print('A is not zero')
```

Note the colon dividing the statement into "cause" and "effect". `If`-statements can be arbitrarily complex, and contain, for instance, arguments chained through Boolean operators. In Python, Boolean operators are real words:

- `if (a == 0 and b==1): print('A is zero, b is one`)
- `if (a == 1 or b==1): print('A or b or both are one`)

All standard Boolean operators are available, many more can be obtained through libraries (and of course you can also build them by stacking standard operators).

## Flow control: for

If you are used to another programming language, the `for` loop in Python takes some getting used to but is actually much more convenient than, for instance, its C or C++ cousin. In Python, a `for` loop always processes a list. For the technically inclined: a `for` loop in Python is actually a `for each` loop. The basic function of a `for` loop is to run some code a number of times until a condition is met, usually until a predefined number of times has been reached. To print "hello" ten times, in Python we write:

```
for x in range(10):
    print('hello')
```

Note that the `range` statement here defines a list of numbers. If it is given only one argument, it will create a list that ranges from 0 to the argument. If it is given two, it will treat them as the lowest and highest values of the list. A third argument defines the step size.

Also note the indentation: this is how Python knows that we are defining a new code block that should run "inside" the `for` loop. The same indentation is used for`if`-statements.

As `for` loops always iterate over lists, we can very easily iterate over the elements of our integer list from before:

```
for x in int_list:
    print(x)
```

## Flow control: while

An alternative to the `for` loop is the `while` loop. This loop continues running until a specified condition is met, however other than the `for` loop it does not operate on lists. The simplest `while` loop is an infinite loop (do not run this):

 ```
while True:
    print('forever')
```

A more useful variation will check the value of a variable:

```
a = 0
while a <= 10:
    print(a)
    a += 1
```

## Functions

Functions in Python mirror mathematical functions. They are defined as an operation over several arguments. In Python, the `def` keyword is used for this, followed by a colon and an indent the block that defines the function. Functions can take anything between zero and infinite arguments, listed in parentheses right after the function name. Arguments can be anything, even lists or other functions. Importantly, functions open up a new variable *scope*. This means, variables defined within the context of the function will not exist outside the function, including the arguments! Results computed by a function are returned to the part of the program that calls them with the `return` statement.

```
def add(a, b):
    return a + b
add(1, 2)
```

In python, arguments can have default values. This is exessively used in machine learning code. Default values make arguments optional. Given the function

```
def add(a, b=100):
    return a + b
```

`add(1, 2)`will return 3, but `add(1)`will return 101.

## Next

In the next meetings we will talk about:

- Classes, dictionaries, NumPy
- PyTorch: basics
- PyTorch: examples
- Building our own MNIST classifier