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

Line Graphs
===========

Line graphs are among the most common visualizations made by data scientists, and are often used to study chronological trends and patterns.

The table movies_by_year contains data on movies produced by U.S. studios in each of the years 1980 through 2015. The columns are:

```{code-cell}Python
from datascience import *
movies = Table().read_table("movies_by_year.csv")
movies.labels
```
