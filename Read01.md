# Lecture#1 - Read01

## Pain vs. Suffering
**The Pain of Growth** 
- The mindset of growth is to get out of my comfort zone, to reach out and be successful you will experience many problems on new topics and you should be fully ready for searching for hours to find specific information, lose of sleep and other painful situations.
- You are here beacuse you chose to invest in a different life.
- Keep on loving and enjoying what you are doing.
    All growth comes with some degree of pain, as it pulls you out of your comfort zone.

Keep in mind that pain with no purpose will lead you to be suffering.
- Pain with no higher goal
- Pain with no dreams
- Pain with no ambition
- Pain with no aspiration

Keep in my the answers for the following questions it will be motivational:
1. What’s your perspective?
2. Why are you doing this?
3. Do you want what comes at the end of this journey?
4. Are you doing this for you?



## A beginner's guide to Big O Notation
Big O notation is used in Computer Science to describe the performance or complexity of an algorithm.
How time scales with respect to some input variables.

Used to:
- Describe the worst-case scenario.
- Describe the execution time or the space occupied by the algorithm.

### O(1)
Describes an algorithm that will always execute in the same time (or space) regardless of the size of the input data set.

### O(N)
Describes an algorithm whose performance will grow linearly and in direct proportion to the size of the input data set. 

### O(N²)
Represents an algorithm whose performance is directly proportional to the square of the size of the input data set.
The time to run a specific function is going to increase with respect to n squared.

### O(2^N)
- Denotes an algorithm whose growth doubles with each  addition to the input data set. 
- The growth curve of an O(2^N) function is exponential — starting off very shallow, then rising meteorically. 

## Logarithms
### O(log N)
Doubling the size of the input data set has little effect on its growth as after a single iteration of the algorithm the data set will be halved and therefore on a par with an input data set half the size. 

## Four important rules to know with the Big O
1. When we have two different steps in our algorithm, add up both steps. (ex: O(a+b))

2. Drop constants

3. When we have different inputs, we will be using different variables to represent them.

4. Drop non-dominant terms


## Facts and Myths about Python names and values

### Names refer to values:
    name = value

### Many names can refer to one value:
    name = value
    name2 = name

### Names are reassigned independently:
    name = value
    name2 = name
    name = value2
name2 will keep having the name value    

### Values live until no references:
    name = value
    name = value2
name will be reclaimed, removed from the process

### Assignment never copies data:
    nums = [1,2,3,4]
    other = num
both refer to the same list of values
changes are visible through all names 

### Immutable values:
Values that cannot be changed in place
(int, float, string, tuple)


**Rebinding**
Integers: 
    x = x + 1
Lists: 
    nums = nums + [7]

**Mutating**
Lists:
    nums.append(num)

- Names have no type 
- Values have no scope


### Python 3 Module:
[title](https://pymotw.com/3/index.html)