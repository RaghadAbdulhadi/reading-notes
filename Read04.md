# Classes and Objects

**Objects** are an encapsulation of variables and functions into a single entity. 
**Objects** get their variables and functions from classes. 
**Classes** are essentially a template to create your objects.

```
Classes:
class Point:
  #Constructor: called when we create new object
  #self: refrence to a current object
  #instead of:
  #point1.x = 10
  #point1.Y = 10
  def __init__(self, x, y):
    self.x = x
    self.y = y
  def move(self):
    print("move")
  def draw(self):
    print("draw")


point1 = Point()
point1.x = 10
point1.draw()
point1.move()
print(point1.x)


Constructor is a function that is called at the time we create an instance of an object
point1 = Point(10,12)


class Person:
  def __init__(self, name):
    self.name =  name
  def talk(self):
    print(f"hi i am {self.name}")


person1 = Person("Raghad")
person1.talk()
print(person1.name)
```

# Thinking Recursively
**Break problems into small parts**
A recursive function is a function defined in terms of itself via self-referential expressions.
```
Recursive Function
A function that calls itself 
In Recursive Function break the problem in to two parts:
1- Base case when the function stops calling itself to prevent infinite loop
2- Recursive case when the function calls itself 
Basic Structure:
if statment (the Base case)
else statment (the recursive case)
function functionName (parameter){
  if (condition){
    return;
  }
  else{
    the expression to solve a problem 
  }
}
```

Behind the scenes, each recursive call adds a stack frame (containing its execution context) to the call stack until we reach the base case. Then, the stack begins to unwind as each call returns its results

# Maintaining State
Keeping track of the process

- Thread the state through each recursive call so that the current state is part of the current call’s execution context
- Keep the state in global scope

# Recursive Data Structures in Python
A data structure is recursive if it can be deﬁned in terms of a smaller version of itself.

**sep and end**
The end parameter prints after all the output objects present in one output statement have been returned, the sep parameter differentiates between the objects.

### Decorator: 

**lru_cache()** is one such function in functools module which helps in reducing the execution time of the function by using memoization technique.

Syntax:
@lru_cache(maxsize=128, typed=False)

Parameters:

**maxsize:** This parameter sets the size of the cache, the cache can store upto maxsize most recent function calls, if maxsize is set to None, the LRU feature will be disabled and the cache can grow without any limitations
**typed:**
If typed is set to True, function arguments of different types will be cached separately. For example, f(3) and f(3.0) will be treated as distinct calls with distinct results and they will be stored in two separate entries in the cache

# Python Testing with pytest: Fixtures and Coverage

# Fixtures:
Objects available to all of your tests
Objects might contain data you want to share across tests, or they might involve the network or filesystem

Fixtures are functions, which will run before each test function to which it is applied. Fixtures are used to feed some data to the tests such as database connections, URLs to test and some sort of input data.

**Fixture scopes**
- Fixtures are created when first requested by a test, and are destroyed based on their scope:

- function: the default scope, the fixture is destroyed at the end of the test.

- class: the fixture is destroyed during teardown of the last test in the class.

- module: the fixture is destroyed during teardown of the last test in the module.

- package: the fixture is destroyed during teardown of the last test in the package.

- session: the fixture is destroyed at the end of the test session.

**A function is marked as a fixture by**

    @pytest.fixture


Execute the test using the following command

    pytest -k divisible -v


# Coverage

Coverage.py is a tool for measuring code coverage of Python programs. It monitors your program, noting which parts of the code have been executed, then analyzes the source to identify code that could have been executed but was not.

Coverage measurement is typically used to gauge the effectiveness of tests. It can show which parts of your code are being exercised by tests, and which are not.
Checking that your tests have run all of the code.

**Package: python-cov**

A package called pytest-cov on PyPI that can be downloaded and installed. 
Can invoke pytest with the --cov option -----> will get a coverage report for every part of the Python library that your program used.
When we provide an argument to --cov, specifying which program(s) we want to test, and we should indicate the directory into which the report should be written:

    pytest --cov=mymul .


### Convert
Turn the coverage report into something human-readable
    coverage html

This creates a directory called htmlcov. 
Opening the index.html file in this directory using our browser, and we'll get a web-based report showing (in red) where our program still lacks coverage. 
In this case, it showed that the function path wasn't covered. 