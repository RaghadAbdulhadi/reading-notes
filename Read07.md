# Big O

- Is a way for comparing algorithms with other algorithms, and how the algorithm will perform 
- Is a way of measuring how an algorithm will respond to an increasing amount of data that it has to process
- It gives us that the algorithm Worst Casen

**Two Components:** 

- Time Complexity: How long an algorithm takes to do something
- Space Complexity: How mush memory it takes while its doing something

**Types of Complexities:** 

- O(1) -> Constant running time
- O(logn) -> Logarithmic running time
- O(n) -> Linear running time
- O(n logn) -> Log-Linear running time
- O(n^k) -> Polynomial running time
- O(c^n) -> Exponential running time

*O(1)*

Time to process doesn't go up as the number of inputs increases

*O(n)*

Time to process goes up linearly with the number of inputs

*O(n^2)*

Time to process goes up with the square of numbers increases

*O(logn)*

Time to goes up by one as the data scales in one level


# Modules: The Global Scope
Python turns the program’s main script into a module called __main__ to hold the main program’s execution. The namespace of this module is the main global scope of your program.
- Any name defined at the top level of any Python module, then that name is considered global to the module.
- __main__' is also the name of its main module
     __name__
    '__main__'
- The interpreter executes the code in the module or script that serves as an entry point to your program
- To inspect the names within the main global scope, you can use dir()
    - Call dir() without arguments, then we’ll get the list of names that live in your current global scope
    - If we assigned a new name at the top level of the module, then that name will be added to the list returned by dir().
- There’s only one global Python scope per program execution.
    - This scope remains in existence until the program terminates and all its names are forgotten.
- We can access or reference the value of any global name from any place in your code. This includes functions and classes.

Whenever a value is assigned to a name in Python, one of two things can happen:
1. We create a new name
3. We update an existing name

Global names can be updated or modified from any place in the global Python scope. Beyond that, the global statement can be used to modify global names from almost any place in the code

**Modifying global names is generally considered bad programming practice because it can lead to code that is:**

- *Difficult to debug:* Almost any statement in the program can change the value of a global name.
- *Hard to understand:* You need to be aware of all the statements that access and modify global names.
- *Impossible to reuse:* The code is dependent on global names that are specific to a concrete program.

**Good programming practice recommends using local names rather than global names:**

- Write self-contained functions that rely on local names rather than global ones.
- Try to use unique objects names, no matter what scope you’re in.
- Avoid global name modifications throughout your programs.
- Avoid cross-module name modifications.
- Use global names as constants that don’t change during your program’s execution.


**Python provides two keywords that allows the modification of the content of global and nonlocal names:**

1. global
2. nonlocal

**The global Statement**

The statement consists of the global keyword followed by one or more names separated by commas.

All the names that you list in a global statement will be mapped to the global or module scope in which you define them.

    The use of global is considered bad practice in general. If you find yourself using global to fix problems like the one above, then stop and think if there is a better way to write your code.

**The nonlocal Statement**

Nonlocal names can be accessed from inner functions, but not assigned or updated

With a nonlocal statement, we can define a list of names that are going to be treated as nonlocal.

The nonlocal statement consists of the nonlocal keyword followed by one or more names separated by commas

We can’t use nonlocal outside of a nested or enclosed function, we can’t use a nonlocal statement in either the global scope or in a local scope.

Names must already exist in the enclosing Python scope if we want to use them as nonlocal names. This means that we can’t create nonlocal names by declaring them in a nonlocal statement in a nested function.

