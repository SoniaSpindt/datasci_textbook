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

Bar Charts
==========

Did you notice that in order to create a scatter plot or a line graph in last week's make assignment, you needed to use columns that contained numerical data? This was fine and dandy because our data set contained numbers in it.

However, data often comes in many forms that are not numerical. Data can be pieces of music, or places on a map. They can also be categories into which you can place individuals. Here are some examples of ***categorical*** data.

1. Flavors of ice cream.
2. Professional basketball players.
3. Genre of movies.
4. Responses on a survey like: "Not at all satisfied", "Somewhat satisfied", or "Very satisfied".
5. Lyrics in a song.

Consider the following data table about ice cream:

```{code-cell}Python
from datascience import *
icecream = Table().with_columns(
    'Flavor', make_array('Chocolate', 'Strawberry', 'Vanilla'),
    'Number of Cartons (in Millions)', make_array(16, 5, 9)
)
icecream
```
The values of the categorical column "flavor" are chocolate, strawberry, and vanilla. The table also shows the number of cartons of each flavor. We call this numerical data the ***frequency*** of our categorical data.

The bar chart is one way that we can visualize categorical data. It displays a bar for each category. The bars are equally spaced and equally wide. The length of each bar is proportional to the frequency of the corresponding category.

We will draw bar charts with horizontal bars because it's easier to label the bars that way. In order to do this, you will want to call the `barh` function, and it takes two arguments: the first is the column label of the categories, and the second is the column label of the frequencies.

```python3
icecream.barh('Flavor', 'Number of Cartons (in Millions)')
```
```{image} bar1.png
:alt: Graph 8
:height: 300px
```

Don't forget about all of the functions we learned about in chapters 2 - 4! We can use those functions to change the way our bar graphs look. For example, we can rearrange the order of our bars in the ice cream chart above by calling `sort`!
```python3
icecream.sort('Number of Cartons', descending=True).barh('Flavor', 'Number of Cartons Number of Cartons (in Millions)')
```
```{image} bar2.png
:alt: Graph 9
:height: 300px
```
This bar chart contains exactly the same information as the previous one, but it is a little easier to read. While this ease of reading is less obvious with a chart that only contains 3 bars, it can be quite significant when the number of categories being visualized is large.
