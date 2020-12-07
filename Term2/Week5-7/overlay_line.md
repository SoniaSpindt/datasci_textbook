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
from datascience import *
entire_table = Table.read_table("censusdata.csv")
entire_table.show(3)
```

After looking at the table above, I want to examine the relationship seen between the number of children in a particular age group (i.e. 0 - 18) and the years 2010 and 2014.

In order to isolate just this portion of the data set, we will need to rely on a few functions we have seen before: `select`, `relabel`, `drop`, and `where`.

```{code-cell}python3
from datascience import *
entire_table = Table.read_table("censusdata.csv")
partial_table = entire_table.select(['SEX', 'AGE', 'POPESTIMATE2010', 'POPESTIMATE2014'])
us_pop = partial_table.relabeled('POPESTIMATE2010', '2010')
us_pop = us_pop.relabeled('POPESTIMATE2014', '2014')
children = us_pop.where('SEX', are.equal_to(0))
children = children.where('AGE', are.below(19))
children = children.drop('SEX')
children.show(3)
```
We can now draw two overlaid line graphs, showing the numbers of children in the different age groups for each of the years 2010 and 2014. The method call is analogous to the scatter call in the previous example, where you only want to pass in the label of the column that is shared between the columns `2010` and `2014`.

```python3
children.plot('AGE')
```

```{image} overlayline.png
:alt: Overlaid line graph
:height: 300px
```

<br>It's important to remember that we only have data at ages 0, 1, 2, and so on; the graphs "join the dots" in between.

The graphs cross each other in a few places: for example, there were more 4-year-olds in 2010 than in 2014, and there were more 14-year-olds in 2014 than in 2010.

Of course, the 14-year-olds in 2014 mostly consist of the 10-year-olds in 2010. To see this, look at the gold graph at AGE 14 and the blue graph at AGE 10. Indeed, you will notice that the entire gold graph (2014) looks like the blue graph (2010) slid over to the right by 4 years. The slide is accompanied by a slight rise due to the net effect of children who entered the country between 2010 and 2014 outnumbering those who left. Fortunately, at these ages, there is not much loss of life.
