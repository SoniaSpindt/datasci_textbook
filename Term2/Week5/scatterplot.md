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


The Table method scatter draws a scatter plot consisting of one point for each row of the table. Its first argument is the label of the column to be plotted on the horizontal axis, and its second argument is the label of the column on the vertical.
