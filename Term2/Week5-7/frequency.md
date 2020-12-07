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

Calculating Frequency
=====================

In our ice cream example, someone had to go through the trouble of counting the number of containers of each flavor by hand to get the frequency data.

```{image} https://media.giphy.com/media/N4xCVPenanVcI/giphy.gif
:alt: Michael Scott "Don't Like That"
:height: 200px
```

<br>Don't worry, I'm not going to ask you to go count millions of ice cream containers by hand. Instead, we need to talk about what you can do if you're asked to make a bar chart from a data set that does not contain frequency data. Gulp.

```{image} https://media2.giphy.com/media/zv8JtHs5SIrQs/source.gif
:alt: Nervous Raven
:height: 200px
```

<br>Let's go through an example to understand how we can do this.

The table `top`, seen below, consists of U.S.A.'s top grossing movies of all time. The first column contains the title of the movie. "Star Wars: The Force Awakens" is at the top, with a box office earnings of more than 900 million dollars in the United States. The second column contains the name of the studio that produced the movie. The third contains the domestic box office earning amount in dollars, and the fourth contains the amount that would have been earned from ticket sales at 2016 prices. The fifth contains the release year of the movie.

There are 200 movies on the list. Here are the top ten according to unadjusted earning amounts.

```{code-cell}Python
from datascience import *
top = Table.read_table("top_movies.csv")
top.show(10)
```

The Disney owned studio Buena Vista shows up frequently in the top ten, as do Fox and Warner Brothers. Which studios will appear most frequently if we look among all 200 rows?

To figure this out, first notice that all we need is a table with the movies and the studios; the other information is unnecessary! Add the following code to the cell above to see what happens:

```python3
movies_and_studios = top.select('Title', 'Studio')
movies_and_studios.show(10)
```

The function `group` allows us to count how frequently each studio appears in the table, by calling each studio a category and assigning each row to one category. The `group` function takes as its argument the label of the column that contains the categories, and returns a table of counts of rows in each category. The column of counts is always called count, but you can change that if you like by using `relabeled`. Again, add these lines of code to the example above to see how group works.
```python3
movies_and_studios.group('Studio')
```
Thus `group` can be used to generate the frequency data that you might need for a bar graph!

We can now use this table, along with the graphing skills that we acquired above, to draw a bar chart that shows which studios are most frequently among the 200 highest grossing movies.
```python3
studio_freq = movies_and_studios.group('Studio')
studio_freq.sort('count', descending=True).barh('Studio')
```
```{image} bar3.png
:alt: Graph 9
:height: 400px
```
<br>Warner Brothers and Buena Vista are the most common studios among the top 200 movies. Warner Brothers produces the Harry Potter movies and Buena Vista produces Star Wars, so that makes sense.
