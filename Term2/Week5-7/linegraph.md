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

Line Graphs
===========

Line graphs are among the most common visualizations made by data scientists, and are often used to study chronological trends and patterns. Like scatter plots, line graphs are used to examine the relationship seen between two variables, except one of the variables is often time!

The table movies_by_year contains data on movies produced by U.S. studios in each of the years 1980 through 2015. The columns are:

```{code-cell}Python
from datascience import *
movies = Table().read_table("movies_by_year.csv")
movies.labels
```
The function `plot` produces a line graph. Its two arguments are the same as those for `scatter`: first the name of the column you want on the x-axis, then the column you want on the y-axis. Here is a line graph of the number of movies released each year over the years 1980 through 2015.

```Python
from datascience import *
movies = Table().read_table("movies_by_year.csv")
movies.plot("Year", "Number of Movies")
```
```{image} line1.png
:alt: Graph 5
:height: 300px
```
<br>As you can see, the line rises sharply and then has a gentle upwards trend, though the numbers vary noticeably from year to year. The sharp rise in the early 1980's is due in part to studios returning to the forefront of movie production after some years of filmmaker driven movies in the 1970's.

Our focus will be on more recent years. In keeping with the theme of movies, the table of rows corresponding to the years 2000 through 2015 have been assigned to the name century_21.

```Python
from datascience import *
movies = Table().read_table("movies_by_year.csv")
century_21 = movies.where('Year', are.above(1999))
century_21.plot('Year', 'Number of Movies')
```
```{image} line2.png
:alt: Graph 6
:height: 300px
```
<br>The global financial crisis of 2008 has a visible effect – in 2009 there is a sharp drop in the number of movies released. However, the total money earned was higher in 2009 than in 2008, even though there was a financial crisis and fewer movies were consequently released...

What could explain this contradiction? According to the New York Times in the article titled "In Downturn, Americans Flock to the Movies," people tend to go to the movies when there is a recession. The article quotes Martin Kaplan of the University of Southern California saying, "People want to forget their troubles, and they want to be with other people." When holidays and expensive treats are unaffordable, movies provide welcome entertainment and relief.

I can think of another possible reason!

```{code-cell}Python
from datascience import *
movies = Table().read_table("movies_by_year.csv")
century_21 = movies.where('Year', are.above(1999))
century_21.where('Year', are.equal_to(2009))
```
Avatar was released during 2009!  Not only was Avatar the #1 movie of 2009, it is also, by some calculations, the second highest grossing movie of all time!

Before you go, it's important to mention that you can include more arguments in `scatter` and `plot` if you need to change the way your visualization looks. There comes a time in every data scientists life where they run across a data set that is really big! In many of these cases, your x-axis will look like trash because all of the labels will overlap one another. Here's a great example of this phenomenon:

```{image} line3.png
:alt: Graph 7
:height: 300px
```

You couuuuld remove data from the csv file until it all fits on your x-axis, but that kind of sucks for argumentative purposes; the more data you use in your analysis, the more confident you can be that your conclusions are right after all! Instead, it would be nice to simply have a bigger graph. Well, you can achieve this look by adding the `width` and `height` arguments to the `plot` function call, like so.

```Python
table.plot('X-Axis Data', 'Y-Axis Data', width=20, height=10)
```

Here is more information about the arguments you can add to both our <a href="http://data8.org/datascience/_autosummary/datascience.tables.Table.scatter.html?highlight=scatter#datascience.tables.Table.scatter">scatter</a> and <a href="http://data8.org/datascience/_autosummary/datascience.tables.Table.plot.html?highlight=plot#datascience.tables.Table.plot">plot</a> functions.
