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

Expressions
===========

Many Python statements are made up of <b><i>expressions</i></b>, which tell our computer how to combine pieces of data. For example, a multiplication expression consists of a * symbol between two numbers. Here is an example of a multiplication expression:

```{code-cell} python3

print(3 * 4)

```

<br>Expressions, such as `3 * 4`, are <i><b>evaluated</b></i> by the computer.

```{image} https://media.giphy.com/media/rN2EZm3CSXHY1QoGrq/giphy.gif
:alt: Wait, what?
:height: 300px
```
<br>Damn. I thought I could sneak that in there. When you write an expression in your program, your computer will read it and try to turn it into the simplest value it can think of. We call this simplification process <i>evaluation</i>. In the above example, your computer will turn the expression 3 * 4 into 12 because the product of 3 and 4 is 12. We can't turn 12 into anything more basic, and neither can your computer!

Python is hella picky about how you write expressions. If you write an expression that contains something your computer doesn't expect, it will yell at you. For example, what would happen if you were to accidentally add an extra * symbol to our multiplication expression from above? Try it out! Change the line of code below to look like this: `print(3 * * 4)` and then press run.

```{code-cell} python3

print(3 * 4)

```

<br>Obviously, your computer refuses to evaluate this expression. Instead, it has a tantrum and displays a <b><i>SyntaxError</i></b>. The Syntax of a language is its set of grammar rules; when you break these grammatical rules, you produce a SyntaxError. A SyntaxError indicates that an expression's structure doesn't match any of the rules of the language.

Small changes to an expression can change its meaning entirely! If we remove the space found between the *'s in the example above, our computer will be happy again because this is how we form an exponentiation expression in Python (the first number raised to the power of the second: 3 times 3 times 3 times 3). Here is what our program now looks like:

```{code-cell} python3

print(3 ** 4)

```

<br> See! No SyntaxError! The symbols * and ** are called operators, and the values they combine are called operands. We will use a lot of operators in this class because data science is all about combining numerical values. Here is a list of the operators that we can use in Python:

```{image} operators.png
:alt: Operators
:height: 300px
```

<br> Python expressions obey the same order of operations that we learned about in algebra: multiplication and division occur before addition and subtraction [^**]. Parentheses can be used to group together smaller expressions within a larger expression.

```{code-cell} python3

print(1 + 2 * 3 * 4 * 5 / 6 ** 3 + 7 + 8 - 9 + 10)

```

```{code-cell} python3

print(1 + 2 * (3 * 4 * 5 / 6) ** 3 + 7 + 8 - 9 + 10)

```
Although this section introduced many types of expressions, there are many, many more that were not introduced. In fact, it would be impossible to write down every possible expression that could be written in a Python program! Learning to program involves being brave enough to try out the ideas you have and seeing how your computer responds. What happens if you divide by zero? What happens if you divide twice in a row? You don't always need to ask an expert (or the Internet); many of these details can be discovered by trying them out yourself!

[^*]: Python is an incredibly versatile and powerful language. <a href="https://www.goskills.com/Development/Resources/Why-is-Python-so-popular">Check this article out if you want to know more about it.</a>
[^**]: Don't forget about <a href="https://www.mathsisfun.com/operation-order-pemdas.html">PEMDAS</a>!
