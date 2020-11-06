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
Calling Functions
=================

When we want our computer to actually use a function, we <b><i>call</i></b> the function in our programs. How do we do this? Calling functions ALWAYS follows the same pattern: `name(list of needed values or expressions)`.

Here are some examples of calling functions in Python:

```Python
abs(-12)
```
```Python
round(5 * 1.3)
```
```Python
max(2, 100 + 1000, -356)
```

As you can see, the name of the function is found at the very beginning of the function call. It is easily overlooked but it is very important to include! Why? Python is a very popular programming language, which means a ton of programmers have created hundreds and thousands of functions that you can use in your programs. Without a specific name, your computer would have no idea what you're asking it to do. It would be like asking someone to get the cookie recipe from Google. Without more information (or a better recipe name!), you would have no idea what recipe you were supposed to find.

The name of a function is also very useful in determining what a function actually does. In the first example above, the name of the function is `abs`. What do you think this function does?

```{image} https://media4.giphy.com/media/3o7TKIgFOgUs4ul4SA/giphy.gif
:alt: Thinking hard
:height: 200px
```
<br>Obviously, it's how our computers get that 6 pack.

```{image} https://media.giphy.com/media/iZftXYkraI8VfzojE6/giphy.gif
:alt: working out fail
:height: 300px
```

<br>Kidding! If you said that the `abs` function is used to calculate the absolute value of a number (or expression), then you are correct! The second function's name is `round`, and this function rounds a value (or expression) to the nearest whole number! The third function is `max` and it determines which number (or expression) is the largest.

In this last example, the `max` function is called on three <b><i>arguments</i></b>: 2, 1100, and -356. Arguments are the values that are placed inside of the parentheses of our function call. You can think of arguments as the list of ingredients at the top of a recipe --- without these ingredients (*cough* arguments *cough*), our computer wouldn't have anything to actually bake (in this case, our computer wouldn't have any numbers to compare).

Once each of these values are passed into the function call, your computer will follow the steps outlined by the function and <b><i>return</i></b> some final value. In the example above, 12 is returned by the function call `abs(12)`, 7 is returned by the function call `round(5 * 1.3)`, and 1100 is returned by the function call `max(2, 100 + 1000, -356)`. When a value is returned by a function, it will essentially replace the function call itself.

Big deal, right? Actually! This is super useful because it allows us to call functions and store the value that is returned by the function call in a variable. Here is an example of what I mean:

```{code-cell} python3
result = abs(-100)
print(result)
```

Have a more complex relationship that you need to represent with code? No problema! You can embed function calls into larger expressions. For example, consider a farm in Florida that produced 2.72 billion eggs, and a farm in Iowa that produced 16.25 billion eggs. What would you need to write in order to calculate the percent difference between the two farms? Well, the percent difference would be 100 times the absolute value of their difference, divided by their average. Here's what that would look like in Python.

```{code-cell} python3
florida = 2.72
iowa = 16.25
expression = 100 * abs(florida - iowa) / ((florida + iowa)/2)
print(expression)
```

Functions are amazing because they save us a lot of work when we're coding! You just have to know which functions are out there for you to use. What functions are available? And which ones might be useful for data science? Keep reading to find out!
