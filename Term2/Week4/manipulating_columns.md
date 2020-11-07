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
Manipulating Columns
=====================

More functions! Real cliff hanger, I know. :P I'm about to quickly go through a ton of functions that you can call to make sense of the data contained within a table. I do not expect you to memorize all of this information found in this chapter; instead, you should continue to use this text as a guide for all future projects that you work on.

Let's get to it!

***Size***<br>
The function `num_columns` returns the number of columns that exist in the table. ***Please note that this function call does not require a set of parentheses in order to work***.
```{code-cell}Python
from datascience import *
soccer = Table().read_table("matches.csv")
print("Number of columns:", soccer.num_columns)
```
***Labels***<br>
Need to know the labels of your columns? There's a function for that, and it's named `labels`.
Again, this function does not use parentheses when called.
```{code-cell}Python
from datascience import *
soccer = Table().read_table("matches.csv")
print("Labels:", soccer.labels)
```

You can change a columns name by using the `relabeled` function. This function requires two arguments, so it will require the use of parentheses. The first argument is the name of the column you are trying to change and the second argument is the new name that you would like your column to have.
```{code-cell}Python
from datascience import *
soccer = Table().read_table("matches.csv")

soccer.relabeled("English Name", "English Translation")
soccer = soccer.relabeled("Spanish Name", "Spanish Translation")
print("New Labels: ", soccer.labels)
```
Did you notice that the column label "English Name" did not change? That's because the `relabeled` function does not make changes to the original table. In order to save these changes, you must reassign your variable to the result of calling `relabeled` (like you see on line 4 of the example above).

***Accessing data***<br>
Sometimes you only want to see the data in a single column. One way that you can grab a single column is by calling the function `column`. This function returns an array of the data found within a specific column of your table.
```{code-cell}Python
from datascience import *
soccer = Table().read_table("matches.csv")
print(soccer.column("Student"))
```
Sometimes you won't know the name of the column you're looking for though. In these cases, you will need to use its position in the table instead. Programmers use an ***index*** value when trying to do this, and it represents the position of an item in a table or an array. Programmers like to be different than the rest of us though, so they collectively decided to start counting at 0 instead of 1. So when you talk about the first item in an array, or the first column in a table, it is at index 0, not index 1. The second item in an array, or the second column in a table, is then at index 1, so on and so forth.

We can pass an index value into `column` in order to retrieve a specific column of data.
```{code-cell}Python
from datascience import *
soccer = Table().read_table("matches.csv")
print(soccer.column(0))
```

***Selecting and deleting columns***<br>
Did you notice that the `column` function returns an array? Sometimes it would be nice to get a table, not an array. If this is your need, then you should use the `select` function instead. This function will return a new table instead of an array.

```{code-cell}Python
from datascience import *
soccer = Table().read_table("matches.csv")
new_table = soccer.select('Latitude')
print(new_table)
```
This function also works with index values too! Here is how you would `select` the first two columns of a table.

```{code-cell}Python
from datascience import *
soccer = Table().read_table("matches.csv")
new_table = soccer.select(0, 1)
print(new_table)
```

What about deleting columns in a table? There's a function for that too and it's named `drop`.
```{code-cell}Python
from datascience import *
soccer = Table().read_table("matches.csv")

#Doesn't make sense to have a Per Capita column, so let's drop it!
modified_table = soccer.drop("Per Capita")
print(modified_table)
```

Cool, cool, cool. What about the rows of our tables? Can we do anything with those?
