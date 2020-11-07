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
Manipulating Rows
=================

Duhhh! The following functions are used to manipulate the rows of a table.

***Size***<br>
The function `num_rows` returns the number of rows that exist in a table.

```{code-cell}Python
from datascience import *
nba = Table().read_table("NBA_salaries.csv")
print("Number of rows:", nba.num_rows)
```
***Accessing Data***<br>
Need a specific item within a row? Use an index value, the `column` function AND the `item` function to retrieve it.
```{code-cell}Python
from datascience import *
nba = Table().read_table("NBA_salaries.csv")
nba.column(0).item(1)
```

***Sorting rows***<br>
Want to see just a certain number of rows in your table? The `show` function can help you out.
```{code-cell}Python
from datascience import *
nba = Table().read_table("NBA_salaries.csv")
#This displays the first 3 rows of the nba table.
nba.show(3)
```
You may have noticed that this table doesn't seem to be organized in any particular way. What if you wanted to organize the data by "PLAYER"? You can use the `sort` function to reorganize the data found within a table. Feel free to stick multiple function calls together! Your computer will execute these function calls from left to right.
```{code-cell}Python
from datascience import *
nba = Table().read_table("NBA_salaries.csv")
nba.sort("PLAYER").show(3)
```
***Selecting rows***<br>
You can choose a subset of rows from your table by calling the `take` function. Its argument is an index (or array of indices), and it creates a new table consisting of only those rows.
```{code-cell}Python
from datascience import *
nba = Table().read_table("NBA_salaries.csv")
nba.take(0)
nba.take(make_array(0, 1, 2, 3, 4))
```

***Selecting by A Specific Feature***
<br>More often than not, you will want to access data in a set of rows that share a certain feature or characteristic, but whose indices we don't know ahead of time. For example, you might want to gather data on all the players who made more than $10 million. Obviously, not every player in this table will meet this criteria, and we certainly don't want to count the rows by hand (that's over 400 rows of data to count!).

Don't worry! The function `where` can do the job for us. Its output is a table with the same columns as the original but only the rows where the feature occurs.

The first argument of `where` is the label of the column that contains the information we might want. In this case, we want to focus on the "SALARY" column because this contains information about a player's earnings.

The second argument of `where` is a way of asking our computer a question about the data in a particular column. In this case we want to ask "*who made more than $10 million dollars?*" and the way we ask this question looks like this:

```{code-cell}Python
from datascience import *
nba = Table().read_table("NBA_salaries.csv")
nba.where('SALARY', are.above(10))
```
In the program above, Python will look at each value in the "SALARY" column and check to see if it's greater than 10. If it is, then it will pull the row that contains this value and put it in a new table. If it's not, it will move on and check the next value until it has reached the end of the table.

The use of the argument `are.above(10)` represents a collection of arguments we can pass into the `where` function called ***predicates***. There are a lot of predicates that you should know because, as you saw above, these can make shifting through data a lot faster and easier.

```{image} predicate.png
:alt: Predicates
:height: 400px
```

You can negate any of the predicates above by writing `not` out front!

```{image} NOTpredicate.png
:alt: Predicates
:height: 150px
```
