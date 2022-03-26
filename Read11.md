# Jupyter Lab
JupyterLab is a next-generation web-based user interface for Project Jupyter

JupyterLab enables us to work with documents and activities such as:
- Jupyter notebooks
- text editors
- terminals
- custom components 

in a flexible, integrated, and extensible manner.

**Text, code consoles, and terminals:**
Includes syntax highlighting and configurable indentation.

To create code console for the text -> right click -> New console for editor -> Python

**Common Format**

All image formates are supported as separated files

**Shortcuts:**
Zoom in and out (- =)
Rotate left/ right []
Reset 0

**Jupyter Note Books:**

New way to work easily with data and code
Jupyet has 2 modes:
1. When a notebook is open --> Command Mode --> Easily navigating and changing the framework of my notebook
2. Edit mode: press enter to edit the current active cell

Composed of cells, which keeps my data and code in small containers

**Shortcuts:**
- Add a cell above: a
- Add a cell below: b
- Copy a cell: c
- Paste a cell: v
- Cut a cell: x
- Delete a cell: d d
- Undo a cell: z
- Redo a cell: shift + z
- y -> Cell format: Code
- m -> Cell format: [Markdown Sheet](https://www.markdownguide.org/cheat-sheet/)
- shift + enter -> Run cell
- 0 0 -> Restart Kernel

Using jupyter we can arrange multiple documents and activities side by side in the work area using tabs and splitters. 

**Documents and activities integrate with each other, enabling new workflows for interactive computing, for example:**

**Code Consoles** provide transient scratchpads for running code interactively, with full support for rich output. A code console can be linked to a notebook kernel as a computation log from the notebook, for example.

**Kernel-backed documents** enable code in any text file (Markdown, Python, R, LaTeX, etc.) to be run interactively in any Jupyter kernel.

Notebook cell outputs can be **mirrored into their own tab**, side by side with the notebook, enabling simple dashboards with interactive controls backed by a kernel.

Multiple views of documents with different editors or viewers enable live editing of documents reflected in other viewers. For example, it is easy to have live preview of **Markdown, Delimiter-separated Values, or Vega/Vega-Lite** documents.

JupyterLab also offers a unified model for viewing and handling data formats. JupyterLab understands many file formats (images, CSV, JSON, Markdown, PDF, Vega, Vega-Lite, etc.) and can also display rich kernel output in these formats. See File and Output Formats for more information.

To navigate the user interface, JupyterLab offers customizable keyboard shortcuts and the ability to use key maps from vim, emacs, and Sublime Text in the text editor.

JupyterLab extensions can customize or enhance any part of JupyterLab, including new themes, file editors, and custom components.

JupyterLab is served from the same server and uses the same notebook document format as the classic Jupyter Notebook.

# NumPy Tutorial: Data Analysis with Python

NumPy is a commonly used Python data analysis package. By using NumPy, you can speed up your workflow, and interface with other packages in the Python ecosystem,

The data is in ssv (semicolon separated values) format —> each record is separated by a semicolon (;), and rows are separated by a new line

**Lists Of Lists for CSV Data**

Working with the data using Python and the csv package

We can read in the file using the csv.reader object, which will allow us to read in and split up all the content from the ssv file.

    Import the csv library
    Open the example.csv file.
        With the file open, create a new csv.reader object.
            Pass in the keyword argument delimiter=";" to make sure that the records are split up on the semicolon character instead of the default comma character.
        Call the list type to get all the rows from the file.
        Assign the result to varaible.

Once we’ve read in the data, we can print out any number of rows

The data has been read into a list of lists. Each inner list is a row from the ssv file. Each item in the entire list of lists is represented as a string, which will make it harder to do computations --> format the data into table

**Numpy 2-Dimensional Arrays(Matrix)**

With NumPy, we work with multidimensional arrays

In a NumPy array, the number of dimensions is called the rank, and each dimension is called an axis. So the rows are the first axis, and the columns are the second axis.

**Creating A NumPy Array**

We can create a NumPy array using the numpy.array function. If we pass in a list of lists, it will automatically create a NumPy array with the same number of rows and columns.

One of the limitations of NumPy is that all the elements in an array have to be of the same type

*We can check the number of rows and columns in our data using the shape property of NumPy arrays:*

    example.shape

**Alternative NumPy Array Creation Methods**

It’s useful to create an array with all zero elements in cases when you need an array of fixed size, but don’t have any values for it yet.

Creating arrays full of random numbers can be useful when you want to quickly test your code with sample arrays.

**Using NumPy To Read In Files**

It’s possible to use NumPy to directly read csv or other files into arrays. We can do this using the numpy.genfromtxt function.

**Indexing NumPy Arrays**

We can use array indexing to select individual elements, groups of elements, or entire rows and columns. One important thing is that just like Python lists, NumPy is zero-indexed, meaning that the index of the first row is 0, and the index of the first column is 0.

With a 2-dimensional array in NumPy, we specify 2 indexes to retrieve an element. The first index is the row, or axis 1, index, and the second index is the column, or axis 2, index.

**Slicing NumPy Arrays**

If we want to select the first three items from the fourth column, we can do it using a colon (:)
A colon indicates that we want to select all the elements from the starting index up to but not including the ending index

**Assigning Values To NumPy Arrays**

We can also use indexing to assign values to certain elements in arrays. We can do this by assigning directly to the indexed value


**Dimensional NumPy Arrays**

One of the most common types of multidimensional arrays is the 1-dimensional array, or vector.

A 1-dimensional array only needs a single index to retrieve an element. Each row and column in a 2-dimensional array is a 1-dimensional array.

**N-Dimensional NumPy Arrays**

Arrays that have greater than 3 dimensions. (list of lists of lists)

**NumPy Data Types**

Each NumPy array can store elements of a single data type

NumPy stores values using its own data types, which are distinct from Python types like float and str. This is because the core of NumPy is written in a programming language called C, which stores data differently than the Python data types. NumPy data types map between Python and C, allowing us to use NumPy arrays without any conversion hitches.

We can find the data type of a NumPy array by accessing the dtype property:

    example.dtype

Data types of NumPy: [DataTypes](https://numpy.org/doc/stable/reference/arrays.dtypes.html)

**Converting Data Types**

We can use the numpy.ndarray.astype method to convert an array to a different type. The method will actually copy the array, and return a new array with the specified data type

    example.astype(int)

**NumPy Array Operations**

NumPy makes it simple to perform mathematical operations on arrays. This is one of the primary advantages of NumPy, and makes it quite easy to do computations.

*Single Array Math*

If we do any of the basic mathematical operations (/, *, -, +, ^) with an array and a value, it will apply the operation to each of the elements in the array.

*Multiple Array Math*

It’s also possible to do mathematical operations between arrays. This will apply the operation to pairs of elements.

*Broadcasting*

Unless the arrays that you’re operating on are the exact same size, it’s not possible to do elementwise operations. In cases like this, NumPy performs broadcasting to try to match up elements. Essentially, broadcasting involves a few steps:

    The last dimension of each array is compared.
        If the dimension lengths are equal, or one of the dimensions is of length 1, then we keep going.
        If the dimension lengths aren’t equal, and none of the dimensions have length 1, then there’s an error.
    Continue checking dimensions until the shortest array is out of dimensions.

**NumPy Array Methods**

Used for more complex calculations on arrays

**NumPy Array Comparisons**

NumPy makes it possible to test to see if rows match certain values using mathematical comparison operations like <, >, >=, <=, and ==. 

*Subsetting*

One of the powerful things we can do with a Boolean array and a NumPy array is select only certain rows or columns in the NumPy array.

*Reshaping NumPy Arrays*

We can change the shape of arrays while still preserving all of their elements. This often can make it easier to access array elements. The simplest reshaping is to flip the axes, so rows become columns, and vice versa. We can accomplish this with the numpy.transpose function

*Combining NumPy Arrays*

With NumPy, it’s very common to combine multiple arrays into a single unified array. We can use numpy.vstack to vertically stack multiple arrays.

## Free NumPy Cheat Sheet

[CheatSheet](https://s3.amazonaws.com/dq-blog-files/numpy-cheat-sheet.pdf)
