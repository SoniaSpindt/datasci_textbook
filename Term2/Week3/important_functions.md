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

Arrays as Arguments
=========================

Once you have created an array of data, you can pass your array into other function calls. This makes the analysis step of data science A LOT easier on us. For example, this is what it would look like to sum all of the values stored within an array:

```{code-cell} python
from datascience import *
nums = make_array(1, 2, 3, 4, 5)
result = sum(nums)
print(result)
```
Isn't this better than adding every single number together by hand? Not convinced? What if we made this array a lot bigger? Consider the program below, which creates an array with one thousand integers in it and adds each one of those numbers together[^*].

```{code-cell} python
from datascience import *
#Creates an array with one thousand 3s and 5s in it.
a_thousand_nums = make_array(*[3, 5]*500)
print(a_thousand_nums)
result = sum(a_thousand_nums)
print("The result is...", result)
```

Here is another function that you might want to use: `len`. This function returns the length of an array. If we used it in the program above, we would expect the length to be 1000 because there are one thousand numbers in the array. Don't believe me? Check this out:

```{code-cell} python
from datascience import *
#Creates an array with one thousand 3s and 5s in it.
a_thousand_nums = make_array(*[3, 5]*500)
print(a_thousand_nums)
length = len(a_thousand_nums)
print("The length is...", length)
```

Both `sum` and `len` are built into Python, so you don't have to worry about importing them. However, there are a set of functions that make data scientists across the world swoon:

```{image} https://media.giphy.com/media/wAQ2pgjKmSB2lFK6qR/giphy.gif
:alt: Doing too much
:height: 200px
```
<br>What are these functions? And how do we use them?

[^*]: It's ok if the argument passed into make_array looks weird to you! I'm using a notation we haven't discussed, and won't discuss in this class. Just know that I'm embracing my lazy side, and that it creates an array with a thousand numbers in it. :)
