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
Arrays
======

Take a look at this Python program:

```{code-cell} python
sneaker1 = "Air Jordan 1"
sneaker2 = "Buscemi 100 MM Diamond"
sneaker3 = "Air Jordan 12 (Flu Game)"
sneaker4 = "Air Jordan 11 'Jeter'"
sneaker5 = "Nike Air Mag Back to the Future"
sneaker6 = "Adidas NMD_R1 Friends and Family"
sneaker7 = "Nike Yeezy 2 Red October"
sneaker8 = "Solid Gold OVO x Air Jordan"
sneaker9 = "Nike Moon Shoe"
sneaker10 = "Air Jordan Silver Shoes"
```
<br>Is this you right now?
```{image} https://media.giphy.com/media/aMO3tYzgitW8c8u2Si/giphy.gif
:alt: Doing too much
:height: 200px
```
<br>I'm right there with you; there are SO many variables in the program above! Technically speaking, there's nothing wrong with this program, but it sure would be nice to embrace our lazy selves again. How could be streamline this a bit more? Well, we could do something like this!

```{code-cell} python
from datascience import *
sneakers = make_array("Air Jordan 1", "Buscemi 100 MM Diamond", "Air Jordan 12 (Flu Game)", "Air Jordan 11 'Jeter'", "Nike Air Mag Back to the Future", "Adidas NMD_R1 Friends and Family", "Nike Yeezy 2 Red October", "Solid Gold OVO x Air Jordan", "Nike Moon Shoe", "Air Jordan Silver Shoes")
```
```{image} https://i.imgur.com/3v3NsPD.gif
:alt: SO nice
:height: 200px
```
<br>SO much better, right?

When we need to store multiple values in a single variable we use something called an <b><i>array</i></b> in Python. How are they created? Pay attention to how I have created the `sneakers` variable: `sneakers = make_array(all the arguments)`. It looks a lot like how we create variables that only store a single value! However, if you squint really hard, you'll notice that we need to call the `make_array` function on the right side of the assignment operator (`=`). As you may have guessed by it's name, this function creates an array when it is called. This function call is special because you can pass in as many or as few arguments as you would like. In the example above, I pass in 10 strings (AKA sneaker names).

There are many ways to create arrays in Python; we will just focus on calling the `make_array` function in this class. However, this function is not built into the Python standard library, so we must import a set of new tools from a module named `datascience`. You can import this module by writing `from datascience import *` at the very top of your program [^*].

Here is what it would look like to create variables of the three data types that we have seen so far, and assign them to arrays:
```{code-cell} python
from datascience import *
ids = make_array(3041, 2293, 7182)
temps = make_array(98.6, 95.9, 104.2)
patients = make_array("Jane", "Jack", "Jill")
print(patients)
```

If you haven't already executed this program, please do so now. You will notice that when we use the print statement to display the `patients` array, we get to see every item that we passed into the function call. Notice how the values are now contained within square brackets (`[]`)? This is how our computer sees arrays!

If it helps, this is how our computer will think about the program above:

```{image} https://media.giphy.com/media/GWbyIHUbRKEatuiWcG/giphy.gif
:alt: Notional machine arrays
:height: 300px
```

<br>Fun fact! You can store different types of values in a single array. That means you can do something like this in your program:

```{code-cell} python
from datascience import *
nums = make_array(3, 3.5, 4, "four point 5")
print(nums)
```
Don't know why you'd do that, but it is possible! :p It's also possible to put expressions in an array, like so:
```{code-cell} python
from datascience import *
powers_of_two = make_array(2**2, 2**3, 2**4)
print(powers_of_two * 2)
```
Catch what I snuck in at the end? You can use expressions to change every value in the array! In the final line of the code above, we are multiplying every value in our `powers_of_two` array by 2 one last time. If you wanted to add 2 to every value in the array, you would write the following expression: `powers_of_two + 2`. Feel free to try this out by changing the code cell above!

Ultimately, arrays are super powerful in data science because they allow us to begin to create data sets with code. This means that we can also apply functions to arrays to learn more about the trends that exist within a particular data set. What functions can we call? Keep reading to find out!

[^*]: You may have noticed that this does not look like the import statement that we used in our previous chapter. There are many ways to import modules but learning how they actually work is outside of the scope of this class. Just know that I'm conciously making the decision to have you import using the `from datascience import *` statement, as opposed to the `import datascience` statement because this keeps you from having to write extra code later on. :)
