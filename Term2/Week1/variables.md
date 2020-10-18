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

Variables
=========

What happens after your computer evaluates an expression? Unless you tell your computer to do something with that value, it will instantly disappear; your computer will move on to the next line of code with no memory of what happened and no ability to look ahead. Lame, right?

Sometimes we want to save the values that we create in our programs so that we can use them later on. The way we get them to stick around is through a programming concept called <b><i>variables</i></b>. Does this term sound familiar to you? It’s possible that you heard about it in your Algebra class, which is a class all about variables! The variables you learned about in your Algebra class are very similar to the variables that you will see and create in this class; in both cases, they are the names we give values!

For example, you may have seen a simple equation in your Algebra class that looks like this:

```Python
  x = 3
```

If I asked you "What is x?" you would (hopefully) answer with "3". See, the name `x` is given to the value `3`! We will do the same thing in this class, except it will look something like this:

```Python
  x = 3
```

```{image} https://media.tenor.com/images/93b843ebb484a8c6204b8241d16f594d/tenor.gif
:alt: Double Take
:height: 200px
```
<br>LOL! They're exactly the same! This line of code is asking our computer to associate the name `x` with the value `3`. So, when I ask you what x is in this class, you can respond with "x is 3", or "x gets 3", or "3 is assigned to x". All of these responses are valid and they all mean the same thing.

I prefer the last response, "3 is assigned to x", because this secretly refers to the name data scientists give the equal sign; they call it the <b><i>assignment operator</i></b>. The assignment operator is responsible for actually telling our computer that you ship a particular name and value.

```{image} https://media.giphy.com/media/HkA9xsCxJCRWw/giphy.gif
:alt: Shipping variables
:height: 200px
```

<br>You can assign expressions to variable names too! Here is an example of a variable that is assigned to a mathematical expression:

```Python
  example = (3 + 12) / 5
```

Here is how your computer will think about this line of code:

```{image} https://media.giphy.com/media/9ScHl0F9yHBzYcRRHh/giphy.gif
:alt: Notional Machine Example
:height: 300px
```

<br>WHAT?! It’s not storing all of `(3 + 12) / 5?` Nope. Remember, your computer will always try to simplify expressions! Consequently, your computer will store the value that you would get if you actually did the math.

As you can see by the animation above, our computers are super organized; they love to put all of the information they come across in boxes that are clearly labeled! That label is super important to include because it helps our computer easily find important bits of information later on. This is also why many people say that variables “store” values in them. If it helps you to think of a variable as a little box used to store a value, then cool! You do you, boo. :)

Need another example? Let’s see how a Python program can be used in medicine to help doctors diagnose patients who might be having a heart attack. One thing that doctors do when they suspect their patient is having a heart attack is draw their blood every few hours. They do this because the heart will release a special protein called Troponin into the blood if it is experiencing a heart attack.

Guess what! Doctors use computers to determine the concentration of these proteins in the blood! You can imagine that if a patient has a lot of Troponin in his/her/their blood, then their heart is really struggling! Here is a simple program that can determine if someone is having a heart attack.

```{code-cell} Python
enzymesHour0 = 2.0;
enzymesHour6 = 320.0;
rateOfChange = (enzymesHour6 - enzymesHour0) / (6 - 0);
print(rateOfChange)
```
Take a moment to read this program, line by line. See if you can predict what your computer will do once this program is executed. Once you are done, press the run button to see if you are right!

Not sure what happened?

Here's how your computer would think about this program:
<br>
```{image} https://media.giphy.com/media/iwJxsXPVpVZ1fjuUdJ/giphy.gif
:alt: Notional Machine Example 2
:height: 300px
```

<br>Are there any expressions in the program above that stand out to you?

```{image} https://media3.giphy.com/media/WRQBXSCnEFJIuxktnw/giphy.gif
:alt: Thinking hard
:height: 200px
```

<br>The expression `(enzymesHour6 - enzymesHour0) / (6 - 0)` stands out to me because it's the largest and it doesn't just have numbers and operators in it. How do we deal with that? Well, like we saw before, your computer will evaluate this expression and turn it into a single value. That means it will grab the values that are stored in `enzymesHour6` and `enzymesHour0` and plug them into the expression where ever it sees these variable names. Then, it will complete the subtraction and division necessary to arrive at the number 53.0. The variable `rateOfChange` is then assigned to this number.

Another expression is found on line 4 of the program, and it is `rateOfChange`. I know it looks like a single value already but it’s actually one step away from becoming the simple value it has always wanted to become! Why? Well, your computer has to actually retrieve the value from memory before the print statement tells our computer to display the value in an output window.

What if you want to change the value that is stored in a variable? No problema! We can change the values that are stored in variables by assigning our variables to new values (*cough* use the <b>assignment operator</b> *cough*). Our computer is happy to chuck the old value and replace it with a new one. Here’s what it might look like to assign variables to new values:

```{code-cell} Python
score = 100
percentChange = 45.7
score = 200
percentChange = 11.2
```

Here is how our computer would reason about this program:

```{image} https://media.giphy.com/media/K4ZEULf0GSwbYIcwyr/giphy.gif
:alt: Notional machine 3
:height: 300px
```

<br>I REALLY need you to notice that the values stored in `score` and `percentChange` are the MOST RECENT values assigned to the variables after program execution has completed. What makes something the most recent value? That depends on how many lines of code our computer has executed. If we were to ask this question right after our computer executed line 4 of the program above, then the most recent values of `score` and `percentChange` would be 100 and 45.7 respectively. Our computer has no awareness of what has happened or what will happen — remember, it lives in the moment! So, the most recent assignment is the assignment which occurs closest to the most recent line of code that has been executed. If we assume the entire program has just been executed, then 200 and 11.2 would be the most recent values assigned to `score` and `percentChange`.
