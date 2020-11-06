---
jupytext:
  formats: md:myst
  text_representation:
    extension: .md
    format_name: myst
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---
Importing Functions
====================

The functions that we saw on the previous page (`abs`, `round`, and `max`) are available for you to use whenever you would like because they are built into Python. However, sometimes you need to use a function that isn't built into Python, and the way that you gain access to this function is by <b><i>importing</i></b> it. More specifically, you need to import the file of Python code that someone else has written that contains this function. This file (technically called a <b><i>module</i></b>) will contain a bunch of functions that are all related to one another by some theme. For example, you can import a module full of math functions.

```{image} https://media0.giphy.com/media/bGPTxLislwm3u/giphy.gif
:alt: Shocked!
:height: 200px
```

<br>Shocker, I know! :p How would you import these math functions into a Python program that you're writing? You need to use an <b><i>import statement</i></b> at the top of your program. It will look like this:

```{code-cell} python3
import math
```

If nothing happens when you press run, then you're good to go! You now have the power to use any of the functions found in this <a href="https://www.w3schools.com/python/module_math.asp">math module</a>. As you can see there are quite a lot of functions that we can use! Let's use one to calculate the square root of a number!

```{code-cell} python3
import math
root = math.sqrt(4)
print(root)
```

Ultimately, the list of Python's built-in functions is quite long and includes many functions that are never needed in data science. The list of mathematical functions in the math module is similarly long. I will do my best to introduce the most important functions in context, rather than expecting you to memorize or understand these lists by yourself.
