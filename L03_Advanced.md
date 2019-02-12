# Python for Machine Learning 3: Advanced

## Dictionaries

Dictionaries extend lists in a useful way: they introduce key value pairs which allow indexing an item by name, rather than by position. Dictionaries in Python use curly brackets, item names are strings, item values follow the name, separated by a colon:

```
empty_dict = {}
fruit = {'apples':1, 'bananas': 2}
```

We can get an item from the second dictionary like this:

```
number_of_apples = fruit['apples']
```

To loop over a dictionary, Python 3 offers the `items()`function. For instance:

```
for k, v in fruit.items():
    print(k, v)
```

will print the contents of the dictionary. Keys and values can be accesses separately. Values of keys can be simply overwritten:

```
fruit['apples'] = 15
```

To check whether a single key is in the dictionary, use the in keyword:

```
if 'apples' in fruit:
    print('We have', fruit['apples'], 'apples.')
```

## Classes

Python is a multi-paradigm programming language. It is not strictly [imperative](https://en.wikipedia.org/wiki/Imperative_programming) or [declarative](https://en.wikipedia.org/wiki/Declarative_programming) but combines feature from both [paradigms](https://en.wikipedia.org/wiki/Programming_paradigm). The building-block like structure of neural networks (or rather the useful abstraction of a building-block like structure), however, lends itself to an object-oriented approach. From Wikipedia:

> Object-oriented programming (OOP) is a programming paradigm based on the concept of "objects", which may contain data, in the form of fields, often known as attributes; and code, in the form of procedures, often known as methods. A feature of objects is that an object's procedures can access and often modify the data fields of the object with which they are associated (objects have a notion of "this" or "self"). In OOP, computer programs are designed by making them out of objects that interact with one another. There is significant diversity of OOP languages, but the most popular ones are class-based, meaning that objects are instances of classes, which typically also determine their type.

Objects are thus arbitrary structures consisting of methods and attributes. We can regard classes as recipes for building objects, or, conversely, we can regard them as abstraction of (future) objects. Classes define which initial attributes and which methods an object will have at its disposal. Objects are *instantiated* from a class. Classes have several predefines methods starting and ending with double underscores. The most commonly used is `__init__`, which is called once when an object is created. Classes - and thus objects - define their own scope, of course. Hence, all class *methods* must take the `self` argument to pass down a reference to the calling object. An example class `Apple` that makes use of all these techniques could be defined like this:

```
class Apple():
    
    color = 'red'
    diameter = 4
    price = '0.0'
    
    def __init__(self):
        self.price = '1.99'

    def eat(self):
        self.diameter-=1
        if (self.diameter <=0):
            self.diameter = 0
```

We can now construct an object from the `Apple` class and access its attributes and methods:

```
a = Apple()
print(a.color)
print(a.diameter)
a.eat()
print(a.diameter)
```

will print `red`, `4`, then `3`.

One important technique in OOP is *inheritance*. Inheritance means that we can create new classes that extend existing classes. For instance, climbing further down the ladder of abstraction, we could define a subclass `FujiApple`, which will have all the properties of a regular `Apple`but be more expensive. The base class for a class inheriting properties is defined in parenthesis behind the class name:

```
class FujiApple(Apple):
    
    def __init__(self):
        self.price = 2.99
```

This class will have the same attributes and methods as the base class.

## Numpy

[NumPy](http://www.numpy.org/), an extension of the Python programming language for high-performance numerical computation, is an important part of all major machine learning frameworks (TensorFlow and PyTorch). Importantly, NumPy re-introduces multidimensional array with predefined *types* to Python, which helps particularly with machine learning tasks. To quote the NumPy docs:

> NumPy’s main object is the homogeneous multidimensional array. It is a table of elements (usually numbers), all of the same type, indexed by a tuple of positive integers. In NumPy dimensions are called axes.

To import NumPy and create a new 10x10 *NumPy 64 bit floating point array* initialized with zero, we can write:

```
import numpy as np
a = np.zeros([3, 3, 3], dtype=np.float64)
```

The most important property of a NumPy array, next to its content, is its *shape*. In machine learning, we operate on large, high-dimensional arrays of values that constantly change their shape. Thus, it is important to occasionally check what values, shape, and type an array contains:

```
print(a)
print(a.shape)
print(a.dtype)
```

NumPy re-implements many Python functions in a more efficient way. For instance, the generation of random numbers in NumPy is provided by the `np.random.random()` function and its cousins:

```
for x in range(10):
    print(np.random.random(), np.random.randint(10))
```

Most NumPy functions allow passing a `size` parameter (sometimes implicitly, sometimes explicitly) to create matrices directly from functions:

```
r = np.random.random(size=(3,3))
```

will create a 3x3 matrix of random numbers between 0 and 1.

The more complex multidimensional arrays are, the more important does slicing become. For instance, to return the n-th z-axis plane of our three, dimensional array `a` we can write:

```
n=1
print(a[:,:,n])
```

A colon indicates that the respective dimension (axis) is returned completely, you can think of it as an "empty" slicing operator.

NumPy is an incredibly powerful package. Please read through the [official tutorial](https://docs.scipy.org/doc/numpy/user/quickstart.html) to get to know some of the functions its provides.