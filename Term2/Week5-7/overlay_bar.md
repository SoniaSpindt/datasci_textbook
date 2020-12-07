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
Overlaid Bar Charts
===================
For our final example, let's look at the distributions of ethnicities of adults and children in California as well as in the entire United States.

The Kaiser Family Foundation has complied Census data on the distribution of race and ethnicity in the U.S. The Foundation's website provides compilations of data for the entire U.S. population in 2014, as well as for U.S. children who were younger than 18 years old that year. Here is what the unaltered data sets look like:

```{code-cell}python3
from datascience import *
all_US = Table().read_table("kaiserUS.csv")
all_US.show(3)

child_US = Table().read_table("kaiserUSChild.csv")
child_US.show(3)
```

Here is a table adapted from their data for the United States and California. The columns represent everyone in the U.S.A., everyone in California, children in the U.S.A., and children in California. The body of the table contains proportions in the different categories. Each column shows the distribution of ethnicities in the group of people corresponding to that column. So in each column, the entries add up to 1.

```{code-cell}python3
from datascience import *
entire_table = Table.read_table("censusdata.csv")
entire_table.show(3)
```
It is natural to want to compare these distributions. It makes sense to compare the columns directly, because all the entries are proportions and are therefore on the same scale.

The method barh allows us to visualize the comparisons by drawing multiple bar charts on the same axes. The call is analogous to those for scatter and plot: we have to specify the common axis of categories.

```{image} overlayline.png
:alt: Overlaid line graph
:height: 300px
```
