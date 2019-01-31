# Setting Up

## Installation

Welcome to the practical part of [ART185AI](https://github.com/zentralwerkstatt/teaching/blob/master/art185ai.md). Below you will find the necessary steps to setup your system to run the code that we will analyze and develop in class. We will utilize an established combination of tools that is being used by many developers working experimentally on machine learning problems, consisting of the 

- [Python](https://python.org) 3 programming language, the
- [Anaconda](https://www.anaconda.com) data science distribution,
- [Numpy](http://www.numpy.org/), a library for fast numerical operations, the
- [Juypter](https://jupyter.org/) notebook literal programming system, and the
- [PyTorch](https://pytorch.org/) machine learning framework.

The following steps assume some familiarity with the command line on your respective system that we will obtain in class.

1. Download the installer package for [Miniconda 3](https://conda.io/en/master/miniconda.html) for your respective operating system and install Miniconda.
2. Open a terminal and create a new [conda environment](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html) with the command `conda create -n art185ai`.
3. Activate the environment (this depends on your operating system).
4. Install [Juypter](https://jupyter.org/) : `conda install jupyter`.
5. Install [PyTorch](https://pytorch.org/) (this depends on your operating system). We assume that no GPU is available and thus install it without CUDA support. A CUDA enabled server with a GeForce 1080TI GPU will be made availabe on request to run computationally expensive and/or highly customized code.
6. You might need to install Git, depending on your system configuration.

If everything worked, you should be able to `cd` into a directory of your choice and run `jupyter notebook`without errors. A browser window will open with the Jupyter interface. There, by pressing the "New" button and the selecting "Python 3", a new Juypter notebook will open. Click on the first cell and enter `print('Hello world!')`, then press `Ctrl + Enter`. The text "Hello world!" will be printed below the cell. Congratulations, you are all set up!

## Help and Support

In the next couple of weeks you will inevitably run into some problems: your code does not work, a library is missing, cryptic error messages are thrown. Do not panic! Coding in times of the Internet means that there is always someone else who has encountered this error before. Many resources exist online that will help you passively, by already having a solution to your problem, or even actively, allowing you to ask questions. During class, please point out problems immediately so we can solve them in a timely manner. Outside class, please try everything at your disposal to solve the problem yourself, and only then email me: I will expect that you describe some of the steps that you have tried in your email.

## Philosophy

This part of the class is meant to prepare you to critically read, and creatively manipulate an existing base of Python code. Our critical analysis of existing algorithms will be based on a critical analysis of their implementations. Accordingly, our focus will be on understanding existing implementations, rather than implementing new problems. You could think of it as learning ancient Greek vs. learning a modern language: the focus is on deciphering and interpreting existing text, and nobody will expect you to hold a fluent conversation.