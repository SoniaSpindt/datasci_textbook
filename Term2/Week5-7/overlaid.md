Overlaid Graphs
=================
In this chapter, we learned how to visualize data by drawing scatter plots, line graphs, and bar charts!

```{image} https://media3.giphy.com/media/BxWTWalKTUAdq/giphy.gif
:alt: Did I do that?
:height: 200px
```

A common use of such visualizations is to compare two datasets. In this section, we will see how to ***overlay*** plots, that is, to draw them on a single graph.

For the overlay to make sense, the graphs that are being overlaid must represent the same variables and must be measured in the same units.

To draw overlaid graphs, the methods `scatter`, `plot`, and `barh` can all be called in the same way. For `scatter` and `plot`, one column must serve as the common horizontal axis for all the overlaid graphs. For `barh`, one column must serve as the common axis which is the set of categories. The general call looks like:

```python3
name_of_table.method(column_label_of_common_axis, array_of_labels_of_variables_to_plot)
```

More commonly, we will first select only the columns needed for our graph, and then call the method by just specifying the variable on the common axis:

```python3
name_of_table.method(column_label_of_common_axis)
```

Turn the page to look at how you can combine scatter plots! 
