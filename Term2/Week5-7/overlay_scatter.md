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
Overlaid Scatter Plots
======================

Franics Galton (1822-1911) was an English scientist who was a pioneer in the analysis of relations between numerical variables. He was particularly interested in the controversial area of eugenics, which involves understanding how to arrange reproduction within the human population in order to increase the likelihood that children will inherit favorable traits from their parents.

```{image} https://media3.giphy.com/media/8p05WdXxPiOyY/200.gif
:alt: Yikes...
:height: 200px
```

Galton meticulously collected a ton of data on how traits were passed from generation to generation. Here is a portion of Galton's data on heights of parents and their children. Specifically, the population consists of 179 men who were the first-born in their families. The data are their own heights and the heights of their parents. All heights were measured in inches.

We can create a table using this data and store it in the variable `heights`, like so:

```{code-cell}python3
heights = Table.read_table('galtonheightdata.csv')
heights.show(3)
```