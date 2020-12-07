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
Overlaid Line Graphs
======================

For our next example, we will take a look at the following census data set:

```{code-cell}python3
from data science import *
entire_table = Table.read_table("censusdata.csv")
entire_table.show(3)
```

After looking at the table above, I want to examine the relationship seen between the number of children in a particular age group (i.e. 0 - 18) and year.

In order to isolate just this portion of the data set, we will need to rely on a few functions we have seen before: `select`, `relabel`, `drop`, and `where`.

```{code-cell}python3
from data science import *
entire_table = Table.read_table("censusdata.csv")
partial_table = entire_table.select(['SEX', 'AGE', 'POPESTIMATE2010', 'POPESTIMATE2014'])
us_pop = partial_table.relabeled('POPESTIMATE2010', '2010')
us_pop = us_pop.relabeled('POPESTIMATE2014', '2014')
children = us_pop.where('SEX', are.equal_to(0)
children = children.where('AGE', are.below(19))
children = children.drop('SEX')
children.show(3)
```

Our next example involves more data about children. created below again for reference. From this, we will extract the counts of all children in each of the age categories 0 through 18 years.

```{image} https://media3.giphy.com/media/8p05WdXxPiOyY/200.gif
:alt: Yikes...
:height: 200px
```
