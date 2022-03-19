# List Comprehensions

    my_new_list = [ expression for item in list ]

**For a python list comprehension to work:**

1. expression: is the expression we’d like to carry out.  
3. item: is the object that the expression will work on. 
4. list: iterable list of objects to build our new list from. 

**Why list comprehension?**

- List comprehension methods are an elegant way to create and manage lists. 
- List comprehensions are a more compact way of creating lists. 
- More flexible than for loops, list comprehension is usually faster than other methods.

**To create a list**

1. Using loop
2. list comprehension

**Create a list with range**

*Using loop*

- Create an empty list
- loop over the elements in the list using for loop
- expression to carry out
- append to the new list
    new_list = []
    for x in range(y):
    squares.append(x**2)

*Using list comprehension*

- assign a variable to be a list with: expression to carry out, for loop all in one line inside the list
     new_list = [x**2 for x in range(y)]

**Multiplying parts of a list**

*Using loop*

- Create an empty list
- loop over the elements in the list using for loop
- expression to carry out
- append to the new list
    new_list = []
    for x in range(y):
        if x % 2 == 0:
            squares.append(x*2)

*Using list comprehension*

- assign a variable to be a list with: expression to carry out, for loop, condition all in one line inside the list
     new_list = [x*2 for x in range(y) if x % 2 == 0]

**Show the first letter of each word**
*Using list comprehension*

    letters = [ name[0] for name in authors ]

**Separating the characters in a string**

    letters = [ letter for letter in "any string"]

**Lower/Upper case converter**

    lower_case = [ letter.lower() for letter in ['A','B','C'] ]
    upper_case = [ letter.upper() for letter in ['a','b','c'] ]

**Print numbers only from a given string**

    phone_number = [ x for x in user_data if x.isdigit()]

**Parsing a file using list comprehension**

    open the file in read-only mode
    reading_file = [ line for line in file ]
    for line in reading_file:
        print(line)

**Using functions in list comprehensions**

    list = [function(argument) for argument in range(num) if any condition]

*Additional arguments can be added to create more complex logic:*

    example: nums = [x+y for x in [1,2,3] for y in [10,20,30]]
