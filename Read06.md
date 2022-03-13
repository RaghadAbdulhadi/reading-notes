# How to use the Random Module in Python

The random module provides access to functions that support many operations, and it allows the generation of random numbers.

## Random Module is used when we want the computer to:
- Pick a random number in a given range
- Pick a random element from a list
- Pick a random card from a deck, flip a coin ..etc.

## Random Module Functions
**Randint:**

To get a random integer
Parameters: Lowest number, Highest number
    import random
    print random.randint(lowest, highest)        
    or

**Random:**

To get a larger random number
    import random
    random.random() * 100

**Choice:** 

To generate a random value from the sequence sequence
    import random
    myList = [element1, element2, element3]
    random.choice(myList)

**Shuffle:**

To shuffle the elements in list in place, so they are in a random order
    from random import shuffle
    x = [ [i] for i in range(num) ]
    shuffle(x)  

**Randrange:**
To generate a randomly selected element from range(start, stop, step)
    import random
    for i in range(3):
        print random.randrange(0, 101, 5)


# What is Risk Analysis in Software Testing and how to perform it?

The probability of any unwanted incident is defined as Risk.
In Software Testing, risk analysis is the process of identifying the risks in applications or software that you built and prioritizing them to test. After that, the process of assigning the level of risk is done. The categorization of the risks takes place, hence, the impact of the risk is calculated.

## Why use Risk Analysis?

Using risk analysis at the beginning of a project highlights the potential problem areas.
When a test plan has been created, risks involved in testing the product are to be taken into consideration along with the possibility of the damage they may cause to your software along with solutions.

**Possible Risks:**

1. Use of new hardware
2. Use of new technology
3. Use of new automation tool
4. The sequence of code
5. Availability of test resources for the application

**Unvoidable Risks:**
1. The time that you allocated for testing

2. A defect leakage due to the complexity or size of the application

3. Urgency from the clients to deliver the project

4. Incomplete requirements

**Tackle the situation:**
Conduct Risk Assessment review meeting

Use maximum resources to work on high-risk areas

Create a Risk Assessment database for future use

Identify and notice the risk magnitude indicators: high, medium, low.

*Risk magnitude indicators:*
High: means the effect of the risk would be very high and non-tolerable. The company might face loss.

Medium: it is tolerable but not desirable. The company may suffer financially but there is a limited risk.

Low: it is tolerable. There lies little or no external exposure or no financial loss.

**Risk Identification:**
Business Risks: This risk is the most common risk associated with our topic. It is the risk that may come from your company or your customer, not from your project.

Testing Risks: You should be well acquainted with the platform you are working on, along with the software testing tools being used.

Premature Release Risk: a fair amount of knowledge to analyze the risk associated with releasing unsatisfactory or untested software is required

Software Risks: You should be well versed with the risks associated with the software development process.


**Risk Assessment:**
After risk identification, assessment has to be dealt programmatically.

*The perspective of Risk Assessment*

Effect – To assess risk by Effect. In case you identify a condition, event or action and try to determine its impact.

Cause – To assess risk by Cause is opposite of by Effect. Initialize scanning the problem and reach to the point that could be the most probable reason behind that.

Likelihood – To assess risk by Likelihood is to say that there is a probability that a requirement won’t be satisfied.

**How to perform Risk Analysis?**

1. Searching the risk

2. Analyzing the impact of each individual risk

3. Measures for the risk identified


# TestCoverage
Test coverage is a useful tool for finding untested parts of a codebase. 
Test coverage is of little use as a numeric statement of how good your tests are.

Low coverage numbers, say below half, are a sign of trouble. But high numbers don't necessarily mean much, and lead to ignorance-promoting dashboards.

If you rarely get bugs that escape into production, and rarely hesitant to change some code for fear it will cause production bugs, then you had enough testing.

# Big O

How time scsles with respect to some input varaibles