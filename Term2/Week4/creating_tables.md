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

Creating Tables
===============

Tables are a part of the datascience module, so you can create a table as soon as you write the following import statement at the top of your Python program: `from datascience import *`.

Once you have imported the datascience module, you can create an empty table by calling the `Table` function, like so:

```{code-cell}Python
from datascience import *
table = Table()
print(table)
```
```{image} https://media3.giphy.com/media/YTDZnDjiGQnCzu7mh6/200.gif
:alt: Not helpful
:height: 200px
```

<br>Yeah, you're right; an empty table doesn't get us very far. It would be a lot more useful to create a table that at least has some column labels. How do we do that? You call a different function from the datascience module! It looks like this:

```{code-cell}Python
from datascience import *
election = Table().with_columns("Nominee", "")
print(election)
```

This will create a table that has a single column labeled Nominee! Ok, ok. This is a little more useful than an empty table, but it sure would be nice to put some data in this column. What would that look like?

```{code-cell}Python
from datascience import *
election = Table().with_columns("Nominee", make_array("Joe Biden", "Donald Trump", "Jo Jorgensen"))
print(election)
```

Mkaaaay. Now we're getting somewhere! Notice the second argument in our `with_columns` function call? It's an array! The second argument of the `with_columns` function is the data that you would like to use to populate the column you just created. What if we wanted to have more columns and more data in our table? Easy! Just keep adding arguments to the `with_columns` function!

```{code-cell}Python
from datascience import *
election = Table().with_columns(
  "Nominee", make_array("Joe Biden", "Donald Trump", "Jo Jorgensen"),
  "California (%)", make_array(65.2, 32.9, 0.9),
  "Michigan (%)", make_array(50.3, 48.1, 1.1),
  "Texas (%)", make_array(46.3, 52.3, 1.1)
  )
print(election)
```
In the above example, I am passing eight arguments into the `with_columns` function call. I have separated each argument with a comma, like I always do, but I also moved every two arguments to its own line in the program. Why? It's easier to read. That's it! If it's easier for you to keep it all on the same line, then be my guest. As long as you recognize that every odd argument is a column label and every even argument is the corresponding data used to fill that column, then you're good to go.

Imagine how much typing you would have to do if you were to create any reasonably sized data set by hand. What happened to embracing our lazy selves? Don't worry, there's a different function you can use to create tables from csv files [^*], and it's named `read_table`. Here's an example of what it looks like to create a table from the data contained within a csv file named "election2012.csv":
```{code-cell}Python
from datascience import *
election = Table().read_table(election2012.csv)
print(election)
```
Whew! That was a lot easier, right? Although data collection is an important part of being a data scientist, we won't cover that process in this class. Instead, all of the data sets that you analyze will be collected by another data scientist in the world and packaged into a nice, neat csv file.

How do we analyze data sets contained within csv files?

[^*]: Comma-separated values (csv) files are super common in the world of data science. They're literally text files that contain a bunch of data points separated by commas.
