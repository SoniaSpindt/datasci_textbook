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

Of course! The following functions are used to manipulate the rows of a table.

***Size***<br>
The function `num_rows` returns the number of rows that exist in a table.

```{code-cell}Python
from datascience import *
example = Table().with_columns("Numbers", make_array(1, 2, 3))
print("Number of rows:", example.num_rows)
```
***Accessing Data***<br>
Need a specific item within a row? Use an index value, the `column` function AND the `item` function to retrieve it.
```{code-cell}Python
from datascience import *
example = Table().with_columns("Student", make_array("Sonia Spindt", "Shro Jacque"), "Student ID", make_array(33327, 74829))
print(example.column(0).item(1))
```

***Sorting rows***<br>
Want to see just a certain number of rows in your table? The `show` function can help you out.
```{code-cell}Python
from datascience import *
nba_salaries = Table.read_table(https://www.statcrunch.com/app/index.php?dataid=1843341 + 'nba_salaries.csv')
#This displays the first 3 rows of the nba_salaries table.
nba_salaries.show(3)
```
You may have noticed that this table is organized alphabetically by team name. If you want to sort your data by player name instead, you can use the `sort` function. Feel free to stick multiple function calls together! Your computer will execute these function calls from left to right.
```{code-cell}Python
from datascience import *
nba_salaries = Table.read_table(https://www.statcrunch.com/app/index.php?dataid=1843341 + 'nba_salaries.csv')
nba_salaries.sort("PLAYER").show(3)
```
***Selecting rows***<br>
The function `take` does just that – it takes a specified set of rows. Its argument is an index or array of indices, and it creates a new table consisting of only those rows.
```{code-cell}Python
from datascience import *
nba_salaries = Table.read_table(https://www.statcrunch.com/app/index.php?dataid=1843341 + 'nba_salaries.csv')
nba_salaries.take(0)
nba_salaries.take(make_array(0, 1, 2, 3, 4))
```
More often, we will want to access data in a set of rows that have a certain feature, but whose indices we don't know ahead of time. For example, we might want data on all the players who made more than  $10 million, but we don't want to spend time counting rows in the sorted table.

The function `where` does the job for us. Its output is a table with the same columns as the original but only the rows where the feature occurs.

The first argument of `where` is the label of the column that contains the information about whether or not a row has the feature we want. If the feature is "made more than  $10  million", the column is SALARY.

The second argument of where is a way of specifying the feature. A couple of examples will make the general method of specification easier to understand.

In the first example, we extract the data for all those who earned more than  $10  million.
```{code-cell}Python
from datascience import *
nba_salaries = Table.read_table(https://www.statcrunch.com/app/index.php?dataid=1843341 + 'nba_salaries.csv')
nba_salaries.where('SALARY', are.above(10))
```
The use of the argument are.above(10) ensured that each selected row had a value of SALARY that was greater than 10.

There are 69 rows in the new table, corresponding to the 69 players who made more than  10  million dollars. Arranging these rows in order makes the data easier to analyze. DeMar DeRozan of the Toronto Raptors was the "poorest" of this group, at a salary of just over  10  million dollars.
```{code-cell}Python
from datascience import *
nba_salaries = Table.read_table(https://www.statcrunch.com/app/index.php?dataid=1843341 + 'nba_salaries.csv')
nba_salaries.where('SALARY', are.above(10)).sort('SALARY')
```

How much did Stephen Curry make? For the answer, we have to access the row where the value of PLAYER is equal to Stephen Curry. That is placed a table consisting of just one line:
```{code-cell}Python
from datascience import *
nba_salaries = Table.read_table(https://www.statcrunch.com/app/index.php?dataid=1843341 + 'nba_salaries.csv')
nba_salaries.where('PLAYER', are.equal_to('Stephen Curry'))
```

Curry made just under  $11.4  million dollars. That's a lot of money, but it's less than half the salary of LeBron James. You'll find that salary in the "Top 5" table earlier in this section, or you could find it replacing 'Stephen Curry' by 'LeBron James' in the line of code above.

In the code, are is used again, but this time with the predicate equal_to instead of above. Thus for example you can get a table of all the Warriors:
```{code-cell}Python
from datascience import *
nba_salaries = Table.read_table(https://www.statcrunch.com/app/index.php?dataid=1843341 + 'nba_salaries.csv')
nba_salaries.where('TEAM', are.equal_to('Golden State Warriors')).show()
```
