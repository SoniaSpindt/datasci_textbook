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
Numpy Functions
===============

There is a very popular Python module called `numpy` and, as the name suggests, it contains a bunch of functions that do stuff with numbers. Obviously this makes it really useful for data scientists because data scientists are professional number wranglers.

When you want to use numpy functions, you have to import the module because it is not a part of the Python standard library. You can import it like so: `import numpy as np`. This import statement lives at the top of your Python program like the rest of the import statements that we have seen so far. However, this import statement is special because it allows the actual numpy module (abbreviated as np) to manipulate our arrays.

The way that we use np in our programs will always look something like this:
```{code-cell} python
from datascience import *
import numpy as np

array = make_array(4.5, 3.9, 10.2, 9.9, 7.1)
product = np.prod(array)
print("The product is...", product)
```

If you look at line 4 of the program above, you will see what it looks like to call a numpy function. It looks like this: `np.prod(array)`. Don't panic! Most of what you have learned about calling function still applies to numpy functions. For example, we still need to put the name of the function we are calling right before a set of parentheses, and we still need to pass in arguments that we want our functions to do something to. The only difference is you need to put `np.` before the function name.

Here are some more numpy functions in action:
```{code-cell} python
from datascience import *
import numpy as np
arrayOfNums = make_array(4.5, 3.9, 10.2, 9.9, 7.1)
arrayOfStrings=make_array("A", "B", "D", "C")

#Example Numpy Functions
print(np.log(arrayOfNums))
print(np.sort(arrayOfNums))
print(np.char.lower(arrayOfStrings))
print(np.char.startswith(arrayOfStrings, "C"))
```
The full <a href="https://numpy.org/doc/stable/reference/">Numpy reference</a> lists these functions exhaustively, but only a small subset are used commonly for data processing applications. It can also be difficult to make sense of technical documentation when you're first learning to program, so I have included a summary of the important data science functions below. You don't need to memorize these; just refer to this section if you ever need a helpful reminder of what a numpy function does.

Each of these functions takes an array as an argument and returns a single value.
```{image} numpy1.png
:alt: numpy1
:height: 300px
```

Each of these functions takes an array as an argument and returns an array of values.
```{image} nump2.png
:alt: numpy2
:height: 300px
```

Each of these functions takes an array of strings and returns an array.
```{image} nump3.png
:alt: numpy3
:height: 300px
```
Each of these functions takes both an array of strings AND a search string; each returns an array.
```{image} numpy4.png
:alt: numpy4
:height: 300px
```
