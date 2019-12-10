
### Questions
* Do you need to complete everything in the curriculum?
    * environment setup not working on learn
* Only clone labs or anything where you're coding on your machine
* 

### Objectives
YWBAT
- manipulate a string for a desired result
- use method chaining to manipulate a string
    - method chaining - a function of an object's class
    - ex: `my_string.replace('old', 'new')`
- use the zip function to iterate over 2 lists
- use list comprehension to create a list
    - list comprehension - building a list inline (within a single line of code)
- loop through a dictionary and get specific items

### Outline

### Inline examples


```python
p = True

if p:
    x = 4
else:
    x = 10
    
x
```




    4




```python
x = 4 if p else 10 #inline conditional

x 
```




    4




```python

```


```python

```


```python

```


```python
import pandas as pd
import numpy as np

from collections import defaultdict

import matplotlib.pyplot as plt
```

### List comprehension


```python
x = list(range(0, 21, 2))

# what is the expected result?
x
```




    [0, 2, 4, 6, 8, 10, 12, 14, 16, 18, 20]




```python
# using a for loop, create a list (y) 
# such that ever element in y is twice the element in x, respectively.

y = []

for i in x:
    y.append(2*i)

y
```




    [0, 4, 8, 12, 16, 20, 24, 28, 32, 36, 40]




```python
# using list comprehension, create a list (y) 
# such that ever element in y is twice the element in x, respectively.

y = [2*i for i in x]

y 
```




    [0, 4, 8, 12, 16, 20, 24, 28, 32, 36, 40]




```python
lst1 = list(range(10))
lst2 = list('abcdefghijklmono')

# print(lst1)
# print(lst2)

# using the zip function, create a list lst3 that is a list of tuples
# lst3 = [(0, a), (1, b), ... , (9, j)]

# code here

# the old way of doing things
# it sucks but is super reliable

# commenting out for now
# lst3 = []
# for index in range(len(lst1)):
#     tup = (lst1[index], lst2[index])
#     lst3.append(tup)
# lst3


# let's use the zip function

# lst3 = list(zip(lst1, lst2))

lst3 = [(i, j) for i, j in zip(lst1, lst2)]

lst3
```




    [(0, 'a'),
     (1, 'b'),
     (2, 'c'),
     (3, 'd'),
     (4, 'e'),
     (5, 'f'),
     (6, 'g'),
     (7, 'h'),
     (8, 'i'),
     (9, 'j')]




```python
# now  let's make the above lst3 into a dictionary
# d = {0: 'a', ..., 9: 'j'}

d = {}

for i, j in zip(lst1, lst2):
    d[i] = j # assign value j to key i

d
```




    {0: 'a',
     1: 'b',
     2: 'c',
     3: 'd',
     4: 'e',
     5: 'f',
     6: 'g',
     7: 'h',
     8: 'i',
     9: 'j'}




```python
# shortcut time
d = dict(zip(lst1, lst2))
d
```




    {0: 'a',
     1: 'b',
     2: 'c',
     3: 'd',
     4: 'e',
     5: 'f',
     6: 'g',
     7: 'h',
     8: 'i',
     9: 'j'}




```python
# let's spell out 'cab'

my_word = d[2] + d[0] + d[1]

my_word
```




    'cab'




```python
d.get(12, d[len(d) - 1]) 
```




    'j'




```python
# default dict

numbers = list(range(30))
print(numbers)
```

    [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29]



```python
# make a dictionary with 

# d['evens'] = [0, 2 , 4, ..., 28]
# d['odds'] = [1, 3, ..., 29]

d = defaultdict(list)


for number in numbers:
    if number%2==0:
        d['evens'].append(number)
    else:
        d['odds'].append(number)

d
```




    defaultdict(list,
                {'evens': [0, 2, 4, 6, 8, 10, 12, 14, 16, 18, 20, 22, 24, 26, 28],
                 'odds': [1, 3, 5, 7, 9, 11, 13, 15, 17, 19, 21, 23, 25, 27, 29]})




```python
list(zip(lst1, lst2, lst3))
```




    [(0, 'a', (0, 'a')),
     (1, 'b', (1, 'b')),
     (2, 'c', (2, 'c')),
     (3, 'd', (3, 'd')),
     (4, 'e', (4, 'e')),
     (5, 'f', (5, 'f')),
     (6, 'g', (6, 'g')),
     (7, 'h', (7, 'h')),
     (8, 'i', (8, 'i')),
     (9, 'j', (9, 'j'))]



### What did we learn?

- learned that `zip` creates tuples from multiple lists
- inline coding, specifically how to create conditions (if statements) inline
- inline coding, for loops
- list comprehension : creating a list from a single line of code
- `get` method on dictionaries returns values of keys or a default value


```python
lst2.index('d')
```




    3



### Assessment
