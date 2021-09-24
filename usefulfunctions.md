# Useful Python functions and other tips

Here are some of the most useful functions in Python and how to use them

## Built-in functions

These functions are built into basic Python and don't need a library importing to use them.

* `print()` - use to show variables as your code progresses. You can add extra text to clarify which `print` statement you are seeing, e.g. `print(thevariable, " is being scraped")`
* `import` - use to import a library whose functions you want to use. If it isn't already installed, you'll need to use...
* `!pip install` - to install a library which isn't already installed
* `type()` - put a variable name inside the brackets and it tells you the type of that variable (`str` for string, `int` for integer, `bool` for boolean and so on)
* `len()` - put a variable name inside the brackets and it tells you its length. If it's a string that will be the number of characters (including spaces). If it's a list it will tell you the number of items (the length of the list)
* `sum()` - will add any ingredients given. If it's given a list it will add up all items in that list.

## `pandas` functions

The `pandas` library has a number of useful functions for dealing with data. These tend to either be joined to `pandas.` (or `pd.` when it is imported `as pd`) or a dataframe. In the examples below I've used `pd.` as this is what you will tend to see in documentation online.

* `pd.read_csv()` - import a CSV file specified in the brackets (that can be a URL or a location on the computer/server, e.g. `"samples/thedata.csv"`). Normally this is stored in a variable, which will be a `pandas` dataframe, like so: `mydf = pd.readjson("thedata.csv")`
* `pd.read_json()` - import a JSON file specified in the brackets (that can be a URL or a location on the computer/server, e.g. `"samples/thedata.json"`). Normally this is stored in a variable, which will be a `pandas` dataframe, like so: `mydf = pd.readjson("thedata.json")`
* `pd.read_excel()` - import an Excel file specified in the brackets. By default this will import the first sheet, so you may need to specify extra parameters such as `sheet_name=` (this should be a string) and `skip_rows=` (an integer: how many rows to skip before the header row), as well as `skipfooter=` (how many rows to skip at the end of the sheet)

The functions below need to be attached to the *variable* you want to apply them to. In this case it's indicated by `mydf` (you'll often see `df` used in online documentation)

* `mydf.to_csv()` - export the specified dataframe to a CSV. You need to specify the name of the CSV in the brackets, as a string, e.g. `"data.csv"`
* `mydf.to_excel()` - export the specified dataframe to an XLS. You need to specify the name of the CSV in the brackets, as a string, e.g. `"data.xlsx"`
* `mydf.to_json()` - export the specified dataframe to a JSON file. You need to specify the name of the CSV in the brackets, as a string, e.g. `"data.json"`
* `mydf.to_html()` - export the specified dataframe to a HTML file. You need to specify the name of the CSV in the brackets, as a string, e.g. `"data.html
* `mydf.head()` - show the first few rows of the dataframe. Specify the number of rows in brackets, or it defaults to 10 if left empty
* `mydf.tail()` - show the last few rows of the dataframe. Specify the number of rows in brackets, or it defaults to 10 if left empty
* `mydf.columns` - show the columns of the dataframe. Note that this doesn't use brackets
* `mydf.dtypes` - show the columns *and* their data types (float, integer, text object etc) of the dataframe. Note that this doesn't use brackets
* `mydf.info()` - show the columns *and* their data types *and* other info such as how many non-null values there are
* `mydf.shape` - show how many rows and columns the dataframe has. Note the lack of brackets.
* `mydf.size` - show how many cells it has. No brackets.
* `mydf.describe()` - provide a statistical summary of any numerical columns (count, mean, standard deviation, quartiles etc). If you want a summary of non-numerical columns too, specify `include="all"` in the brackets)

Other functions can be attached to specific columns, which would be accessed by naming the column key in square brackets like so: `mydf['mycolumn']`

* `mydf['mycolumn'].sum()` - add up all numbers in the column
* `mydf['mycolumn'].count()` - count all numbers in the column
* `mydf['mycolumn'].min()` - show the smallest number in the column
* `mydf['mycolumn'].max()` - show the largest number in the column

## For loops

For loops follow this pattern:

```python
for item in alistvariable:
  afunction(item)
```

Don't forget the colon at the end of the first line, and to indent any lines that you want to run inside the loop (i.e. for each item in the list)

## If/else tests

If/else tests follow this pattern:

```python
if thisistrue:
  dothis
elif thisistrueinstead:
  dothisinstead
else:
  dothisthen
```

Don't forget the colon at the end of each test (if, elif, else), and to indent any lines that you want to run *if* that test is met.

Note that you don't *have* to have an `elif` or even an `else`: you can just have an `if` test and then if that isn't `True` then the script will skip it and move to the next lines of code.

## Creating functions: `def`

A function is created with this pattern:

```python
def functionname(names, of, ingredients):
  whatthefunctiondoes
  return(anythingyouneedtogetout)
```

The function name is arbitrary - that's up to you. It can have no ingredients at all but it still needs brackets. Don't forget the colon and the indented lines indicating code to be executed when the function runs. 

The `return()` at the end is optional - some functions won't need to return any information (they might just print something, for example).

