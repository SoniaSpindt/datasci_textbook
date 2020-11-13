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
<br>Formally, we say that the plot shows an <i>association</i> between the variables, and that the association is <i>positive</i>: high values of one variable tend to be associated with high values of the other, and low values of one with low values of the other, in general.

Of course there is some variability. Some actors are literally in everything but they're not making anything close to what Harrison Ford is making. Others have been in very few movies but got paid a TON. <i>The association is positive</i> is simply a statement about the broad general trend.

Now that we have explored how the number of movies is related to the total money earned, let's turn our attention to how it is related to the average amount earned per movie.
```{code-cell}Python
from datascience import *
actors = Table().read_table("actors.csv")
actors.scatter("Number of Movies", "Average per Movie")
```
This is a totally different picture, and shows a negative association! In general, the more movies an actor has been in, the less the average receipt per movie. Bet your gut didn't tell you that.

Also, one of the points is quite high and off to the left of the plot. It corresponds to one actor who has a low number of movies and high average per movie. This point is an <i>outlier</i>. It lies outside the general range of the data.

We will examine the negative association further by looking at points at the right and left ends of the plot. For the right end, let's zoom in on the main body of the plot by just looking at the portion that doesn't have the outlier.
```{code-cell}Python
from datascience import *
actors = Table().read_table("actors.csv")
no_outlier = actors.where('Number of Movies', are.above(10))
no_outlier.scatter('Number of Movies', 'Average per Movie')
```
Hmmmmmmm...the negative association is still clearly visible. Let's identify the actors corresponding to the points that lie on the right hand side of the plot where the number of movies is large:
```{code-cell}Python
from datascience import *
actors = Table().read_table("actors.csv")
actors.where('Number of Movies', are.above(60))
no_outlier.scatter('Number of Movies', 'Average per Movie')
```
Robert DeNiro has the highest number of movies and the lowest average salary per movie. Other actors are not very far away, but DeNiro's is at the extreme end.

To understand the negative association, note that the more movies an actor is in, the more variable those movies might be, in terms of style, genre, and box office draw. For example, an actor might be in some high-grossing action movies or comedies (such as Meet the Fockers), and also in a large number of smaller films that may be excellent but don't pull in large crowds. Thus the actor's value per movie might be relatively low.

To approach this argument from a different direction, let us now take a look at the outlier.
```{code-cell}Python
from datascience import *
actors = Table().read_table("actors.csv")
actors.where('Number of Movies', are.below(10))
```
First of all, who? Anthony Daniels is not a household name, but the character he has played in all of his 7 movies is adored by people across the world! He played <a href="https://starwars.fandom.com/wiki/C-3PO">C-3PO</a> in Star Wars, and he earned an average of 452 million dollars per movie that he made! Crazy, right?

Mr. Daniels' entire filmography (apart from cameos) consists of movies in the high-grossing Star Wars franchise. That explains why he has made so much money even though, comparatively, he has made very few movies.

If you think about it, variables such as genre and production budget have an effect on the association between the number of movies and the average salary per movie. Let this be the reminder that studying the association between two variables often involves understanding other related variables as well! So don't stop graphing just because you examined a single relationship between variables.
