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

Don't worry, I'm not going to ask you to go count millions of ice cream containers by hand. Instead, we need to talk about what you can do if you're asked to make a bar chart from a data set that doesn't contain frequency data. Gulp.

```{image} https://media2.giphy.com/media/zv8JtHs5SIrQs/source.gif
:alt: Nervous Raven
:height: 200px
```

Let's go through an example to understand how we can do this.

The table `top` consists of U.S.A.'s top grossing movies of all time. The first column contains the title of the movie. "Star Wars: The Force Awakens" is at the top, with a box office earnings of more than 900 million dollars in the United States. The second column contains the name of the studio that produced the movie. The third contains the domestic box office earning amount in dollars, and the fourth contains the amount that would have been earned from ticket sales at 2016 prices. The fifth contains the release year of the movie.

There are 200 movies on the list. Here are the top ten according to unadjusted earning amounts.
