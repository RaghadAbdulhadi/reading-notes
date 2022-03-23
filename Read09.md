# Dunder (Magic, Special) Methods
- Special methods are a set of predefined methods you can use to enrich your classes.
    start and end with double underscores,

- Special methods can emulate the behavior of built-in types

**Special Methods and the Python Data Model**

This elegant design is known as the Python data model and lets developers tap into rich language features like sequences, iteration, operator overloading, attribute access, etc.

To write more Pythonic code, knowing how and when to use dunder methods is an important step.

**Enriching a Simple Account Class**

**Dunder Methods:**

*Object Initialization: __init__*

To construct objects from the class we need a constructor which in Python is the __init__ dunder, the constructor takes care of setting up the object

*Object Representation: __str__, __repr__*

To provide a string representation of our object for the consumer of your class

**There are two ways to do this using dunder methods:**
1. __repr__: The “official” string representation of an object. This is how you would make an object of the class. The goal of __repr__ is to be unambiguous.

2. __str__: The “informal” or nicely printable string representation of an object. This is for the enduser.

**Iteration: __len__, __getitem__, __reversed__**

- To iterate over class object
- To get the length of the object

**Operator Overloading for Comparing Accounts: __eq__, __lt__**
    from functools import total_ordering

**Operator Overloading for Merging Accounts: __add__**

To be able to merge two object instances

**Callable Python Objects: __call__**

We can make an object callable like a regular function by adding the __call__ dunder method

**Context Manager Support and the With Statement: __enter__, __exit__**

    A context manager is a simple “protocol” (or interface) that your object needs to follow so it can be used with the with statement. Basically all you need to do is add __enter__ and __exit__ methods to an object if you want it to function as a context manager.

# Basic Statistics in Python — Probability

- Statistics enables us to calculate probabilities using real-world observations
- Probability provides the theory, while statistics provides the tools to test that theory using data.
- To calculate probabilities, we must fall back on using data and statistics to calculate them

**The data and the distribution** 

Normal distribution: The most important qualities to notice about the normal distribution is its symmetry and its shape

The x-axis takes on the values of events we want to know the probability of. The y-axis is the probability associated with each event, from 0 to 1.

**Revisiting the normal**

The normal distribution is significant to probability and statistics,two factors: the Central Limit Theorem and the Three Sigma Rule.

*Central Limit Theorem*
Central Limit Theorem lets us know that the average of many trials means will approach the true mean, 
*Three Sigma Rule*
Three Sigma Rule will tell us how much the data will be spread out around this mean.

**Z-score**
The Z-score is a simple calculation that answers the question, “Given a data point, how many standard deviations is it away from the mean?” The equation below is the Z-score equation.
