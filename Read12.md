# Pandas
Is a library that provides us with tools to make data analysis
Import:

    import numpy as np
    import pandas as pd

### Object creation
Create a Series by passing a list of values, letting pandas create a default integer index:

    s = pd.Series([values])

Create a DataFrame by passing a NumPy array, with a datetime index and labeled columns:

    dates = pd.date_range("20130101", periods=6)
    df = pd.DataFrame(np.random.randn(6, 4), index=dates, columns=list("ABCD"))

Create a DataFrame by passing a dictionary of objects that can be converted into a series-like structure:

    df2 = pd.DataFrame(
    {
        "A": 1.0,
        "B": pd.Timestamp("20130102"),
        "C": pd.Series(1, index=list(range(4)), dtype="float32"),
        "D": np.array([3] * 4, dtype="int32"),
        "E": pd.Categorical(["test", "train", "test", "train"]),
        "F": "foo",
    }
)

### Viewing data

To view the top and bottom rows of the frame:

    df.head()
    df.tail(3)

Display the index, columns:

    df.index
    df.columns

DataFrame.to_numpy() gives a NumPy representation of the underlying data. 

NumPy arrays have one dtype for the entire array, while pandas DataFrames have one dtype per column.

When we call DataFrame.to_numpy(), pandas will find the NumPy dtype that can hold all of the dtypes in the DataFrame. This may end up being object, which requires casting every value to a Python object.

DataFrame.to_numpy() does not include the index or column labels in the output.

**Methods:**

- describe() shows a quick statistic summary of your data
    df.describe()
- Transposing your data
    df.T
- Sorting by an axis
    df.sort_index(axis=1, ascending=False)

- Sorting by values
    df.sort_values(by="B")


### Selection
**Getting:**
Selecting a single column, which yields a Series, equivalent to df.A
    df["A"]

Selecting via [], which slices the rows
    df[0:3]

**Selection by label**

For getting a cross section using a label
    df.loc[dates[0]]

Selecting on a multi-axis by label
    df.loc[:, ["A", "B"]]

Showing label slicing, both endpoints are included
    df.loc["20130102":"20130104", ["A", "B"]]

Reduction in the dimensions of the returned object
    df.loc["20130102", ["A", "B"]]

For getting a scalar value
    df.loc[dates[0], "A"]

For getting fast access to a scalar (equivalent to the prior method)
    df.at[dates[0], "A"]

**Selection by position**

Select via the position of the passed integers
    df.iloc[3]

By integer slices, acting similar to NumPy/Python
    df.iloc[3:5, 0:2]

By lists of integer position locations, similar to the NumPy/Python style
    df.iloc[[1, 2, 4], [0, 2]]

For slicing rows explicitly
    df.iloc[1:3, :]

For slicing columns explicitly
    df.iloc[:, 1:3]

For getting a value explicitly
    df.iloc[1, 1]

For getting fast access to a scalar (equivalent to the prior method)
    df.iat[1, 1]

### Boolean indexing

Using a single column’s values to select data
    df[df["A"] > 0]

Selecting values from a DataFrame where a boolean condition is met
    df[df > 0]

Using the isin() method for filtering
    df2 = df.copy()
    df2[df2["E"].isin(["two", "four"])]


### Setting
Setting a new column automatically aligns the data by the indexes
    s1 = pd.Series([1, 2, 3, 4, 5, 6], index=pd.date_range("20130102", periods=6))

Setting values by label

    df.at[dates[0], "A"] = 0

Setting values by position

    df.iat[0, 1] = 0

Setting by assigning with a NumPy array

    df.loc[:, "D"] = np.array([5] * len(df))

The result of the prior setting operations

    df

### Missing Data
pandas primarily uses the value np.nan to represent missing data. It is by default not included in computations. 

Reindexing allows us to change/add/delete the index on a specified axis. This returns a copy of the data

    df1 = df.reindex(index=dates[0:4], columns=list(df.columns) + ["E"])
    df1.loc[dates[0] : dates[1], "E"] = 1

To drop any rows that have missing data
    df1.dropna(how="any")

Filling missing data
    df1.fillna(value=5)

To get the boolean mask where values are nan
    pd.isna(df1)

### Operations

**Stats**

Operations in general exclude missing data

**Apply**

Applying functions to the data

### String Methods

Series is equipped with a set of string processing methods in the str attribute that make it easy to operate on each element of the array, as in the code snippet below. Note that pattern-matching in str generally uses regular expressions by default (and in some cases always uses them).

### Merge
Pandas provides various facilities for easily combining together Series and DataFrame objects with various kinds of set logic for the indexes and relational algebra functionality in the case of join / merge-type operations.

### Join
SQL style merges

### Grouping
By “group by” we are referring to a process involving one or more of the following steps:

Splitting the data into groups based on some criteria

Applying a function to each group independently

Combining the results into a data structure

### Time seies
pandas has simple, powerful, and efficient functionality for performing resampling operations during frequency conversion (e.g., converting secondly data into 5-minutely data). This is extremely common in, but not limited to, financial applications

### Categoricals
pandas can include categorical data in a DataFrame.


