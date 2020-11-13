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

Scatter Plots
=============

A <b><i>scatter plot</i></b> displays the relation between two numerical variables. In other words, it's a graph where we can examine the relationship between two sets of data.  

Imagine that we have a data set that contains information about a bunch of famous actors. Here's the first three rows of the table:

```{code-cell}Python
from datascience import *
actors = Table().read_table("actors.csv")
actors.show(3)
```

As you can see, this data set contains information about the number of movies an actor has appeared in and the amount of money that they have earned over time. Although your gut might be telling you that actors who have been a lot of films have probably made more money than those who haven't, but is there a way to be sure about that? We could use a scatter plot to examine the relationship between the number of movies that an actor has appeared in and the amount of money that they have made in their career.


The function `scatter` draws a scatter plot consisting of one point for each row of the table. Its first argument is the label of the column to be plotted on the horizontal axis (x axis), and its second argument is the label of the column on the vertical (y axis).
```{code-cell}Python
from datascience import *
actors = Table().read_table("actors.csv")
actors.scatter("Number of Movies", "Total Earned (Millions)")
```

The plot contains 50 points, one point for each actor in the table. You might also notice that there is a trend in this data --- the more movies an actor has been in, the more money they have made. Now you could have just told the world that your gut told you that this would be true, but no one is going to believe you without evidence to back it up (especially now)! That's where you break out your handy, dandy graph and say...

```{image} https://media4.giphy.com/media/gmg7s5bBQzlN6/giphy.gif
:alt: Told you so
:height: 300px
```
Formally, we say that the plot shows an <i>association</i> between the variables, and that the association is <i>positive</i>: high values of one variable tend to be associated with high values of the other, and low values of one with low values of the other, in general.

Of course there is some variability. Some actors are literally in everything but they're not making anything close to what Harrison Ford is making. Others have been in very few movies but got paid a TON. <i>The association is positive</i> is simply a statement about the broad general trend.

Now that we have explored how the number of movies is related to the total , let's turn our attention to how it is related to the average gross receipt per movie.
