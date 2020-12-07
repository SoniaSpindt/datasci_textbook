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

Franics Galton (1822-1911) was an English scientist who was a pioneer in the analysis of relations between numerical data. He was particularly interested in the controversial area of eugenics, which involves understanding how to arrange reproduction within the human population in order to increase the likelihood that children will inherit favorable traits from their parents.

```{image} https://media3.giphy.com/media/8p05WdXxPiOyY/200.gif
:alt: Yikes...
:height: 200px
```
<br>Galton meticulously collected a ton of data on how traits were passed from generation to generation. Here is a portion of Galton's data on heights of parents and their children. Specifically, the population consists of 179 men who were the first-born in their families. The data are their own heights and the heights of their parents. All heights were measured in inches.

We can create a table using this data and store it in the variable `heights`, like so:

```{code-cell}python3
from data science import *
heights = Table.read_table("galtonheightdata.csv")
heights.show(3)
```
There are a few extra columns of data in this table that are unrelated to the relationships that we are examining (height between father, mother, and child), so let's delete them with `drop`:

```{code-cell}python3
from data science import *
heights = Table.read_table("galtonheightdata.csv")

heights = heights.drop("family")
heights = heights.drop("midparentHeight")
heights = heights.drop("children")
heights = heights.drop("childNum")
heights = heights.drop("gender")

heights.show(3)
```
The scatter method allows us to visualize how the children's heights are related to the heights of both their parents. In the graph, the children's heights will form the common horizontal axis.

```python3
heights.scatter('childHeight')
```
```{image} overlayscatter.png
:alt: Overlay scatter
:height: 300px
```

<br>Notice how we only passed in the column label `childHeight` into our `scatter` function call? We chose this column of data because it is the data that is shared between other groups of data in the table (i.e. it is shared between `father` and `mother`), so it should go on the common horizontal axis. Python knew to draw two scatter plots when it saw this function call: one for the relationship seen between `mother` and `childHeight` and one for the relationship seen between `father` and `childHeight`.

Both the gold and the blue scatter plots slope upwards and show a positive association between the sons' heights and the heights of both their parents. The blue (fathers) plot is in general higher than the gold, because the fathers were in general taller than the mothers.
