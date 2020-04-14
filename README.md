
### Questions
* what is a  dunder do in Python? ie `__init__`
* in the solutions they use a different format for looping
    * when should and how does it work
    * list comprehension vs long format for loop
* question about dictionaries (nested)
    * how does that work? how do we access nested dictionaries? 
* lambdas wth?! 
* macbeth project is saying that macbeth isn't defined. 
* in `numpy` setting a seed for reproducibility
    * what does it mean to set a random seed?

### Objectives
YWBAT
- execute helpful jupyter shortcuts
- manipulate a string for a desired result
- use method chaining to manipulate a string
    - method chaining - a function of an object's class
    - ex: `my_string.replace('old', 'new')`
- use the zip function to iterate over 2 lists
- use list comprehension to create a list
    - list comprehension - building a list inline (within a single line of code)
- loop through a dictionary and get specific items

# Shortcut keys
- `tab` autocomples, but also shows you options
- `shift+tab` x1, x2, x4 shows you documentation


```python
import numpy as np
np.random.seed(42)
```


```python
numbers = np.random.normal(10, 2, size=20)
numbers
```




    array([ 9.7234714 , 11.29537708, 13.04605971,  9.53169325,  9.53172609,
           13.15842563, 11.53486946,  9.06105123, 11.08512009,  9.07316461,
            9.06854049, 10.48392454,  6.17343951,  6.55016433,  8.87542494,
            7.97433776, 10.62849467,  8.18395185,  7.1753926 , 12.93129754])




```python
sum()
```




    7



### Outline

# List comprehension vs for loop


```python
import random
random.seed(42)
```

#### Making a list with a for loop


```python
list_of_numbers = [] # make a list of 10 numbers
for i in range(10): # functions in python need parentheses
    random_number = random.randint(0, 20)
    # how do we add this number to our list?
    list_of_numbers.append(random_number)

# print list_of_numbers outside of loop
print(list_of_numbers)
```

    [5, 16, 3, 20, 9, 20, 16, 19, 6, 4]


#### Making a list with list comprehension


```python
# how do I know it's making a list?
# because of the brackets []
list_of_numbers = [random.randint(0, 20) for i in range(10)]
list_of_numbers
```




    [5, 13, 10, 8, 4, 6, 10, 3, 2, 12]




```python
from string import ascii_letters
```


```python
random.choice(ascii_letters)
```




    'q'




```python
# we're going to make a dictionary containing 10 key, value pairs?
# what is a dictionary? 

# collection of key/value pairs (hashable faster in memory)
d = {"key1": 0}
d
```




    {'key1': 0}




```python
d['key1'] # we call the key to get the value
```




    0




```python
d.get("key2", "some other value") # you can also use the .get() method
```




    'some other value'




```python
d["key2"]
```


    ---------------------------------------------------------------------------

    KeyError                                  Traceback (most recent call last)

    <ipython-input-46-2a179be28044> in <module>
    ----> 1 d["key2"]
    

    KeyError: 'key2'



```python
letter_dict = {} # letter: counts
for i in range(40):
    letter_key = random.choice(ascii_letters)
    if letter_key not in letter_dict.keys():
        letter_dict[letter_key] = 1 # if I haven't seen it, create the key/value starting with 1
    else:
        letter_dict[letter_key] += 1 # otherwise add 1 to the value
letter_dict
```




    {'M': 1,
     'O': 2,
     'k': 2,
     'I': 1,
     'U': 1,
     'p': 2,
     'D': 2,
     'y': 1,
     'r': 2,
     'S': 1,
     'J': 1,
     'o': 2,
     'R': 1,
     'u': 3,
     'X': 2,
     'd': 1,
     'c': 1,
     'Z': 1,
     'z': 2,
     'e': 1,
     'n': 2,
     'K': 1,
     'T': 1,
     'P': 2,
     'F': 1,
     'j': 1,
     'q': 1,
     'i': 1}




```python
letter_dict = {} # letter: counts
for i in range(40):
    letter_key = random.choice(ascii_letters)
    letter_dict[letter_key] = letter_dict.get(letter_key, 0) + 1
letter_dict
```




    {'V': 2,
     'J': 2,
     'I': 2,
     'q': 2,
     'L': 2,
     'B': 2,
     'z': 1,
     'x': 1,
     'o': 1,
     'i': 1,
     'G': 1,
     'F': 1,
     'f': 1,
     'W': 2,
     'd': 1,
     'h': 2,
     'j': 1,
     'O': 1,
     'k': 1,
     'Y': 1,
     'R': 3,
     'M': 2,
     'e': 1,
     'y': 2,
     'D': 1,
     'H': 1,
     'a': 1,
     'U': 1}



# What have we learned so far? 
* how to apply the `.get()` function
* how to build a dictionary! 
* random.seed() and np.random.seed()
* list comprehension
* `random.choice()`


```python
# making a dictionary
d = {}
d['name'] = 'rafa'
d['age'] = 33
d
```




    {'name': 'rafa', 'age': 33}




```python
d['careers'] = [{"job_title": "ms science teacher", "year": 2011},
                {"job_title": "ms math teacher", "year": 2011},
                {"job_title": "math author", "year": 2016},
                {"job_title": "data scientist", "year": 2017}]
d
```




    {'name': 'rafa',
     'age': 33,
     'careers': [{'job_title': 'ms science teacher', 'year': 2011},
      {'job_title': 'ms math teacher', 'year': 2011},
      {'job_title': 'math author', 'year': 2016},
      {'job_title': 'data scientist', 'year': 2017}]}




```python
from pprint import pprint 
```


```python
pprint(d)
```

    {'age': 33,
     'careers': [{'job_title': 'ms science teacher', 'year': 2011},
                 {'job_title': 'ms math teacher', 'year': 2011},
                 {'job_title': 'math author', 'year': 2016},
                 {'job_title': 'data scientist', 'year': 2017}],
     'name': 'rafa'}



```python
d['careers'][1].get('job_title').split("a")

```




    ['ms m', 'th te', 'cher']




```python
for career in d['careers']:
    job_title = career['job_title']
    year = career['year']
    print(f"This job title is {job_title}")
    print(f"This job was performed in {year}")
    print(f" 5 x 2 = {5*2}")
    print("This job title is {}".format(job_title))
    print("--------------------")
    
```

    This job title is ms science teacher
    This job was performed in 2011
     5 x 2 = 10
    This job title is ms science teacher
    --------------------
    This job title is ms math teacher
    This job was performed in 2011
     5 x 2 = 10
    This job title is ms math teacher
    --------------------
    This job title is math author
    This job was performed in 2016
     5 x 2 = 10
    This job title is math author
    --------------------
    This job title is data scientist
    This job was performed in 2017
     5 x 2 = 10
    This job title is data scientist
    --------------------


# Zip Function!!!!!


```python
lst1 = [random.randint(0, 10) for i in range(15)]
lst2 = [random.randint(0, 10) for i in range(15)]
lst1, lst2
```




    ([5, 2, 8, 8, 0, 9, 5, 7, 0, 1, 5, 4, 3, 0, 3],
     [9, 1, 1, 7, 1, 8, 2, 2, 10, 7, 8, 2, 4, 8, 9])




```python
# lst3 = [5 + 9, 2 + 1, ..., 3 + 9]
lst3 = []
for i in range(len(lst1)):
    e1 = lst1[i]
    e2 = lst2[i]
    lst3.append(e1 + e2)
print(lst3)
```

    [14, 3, 9, 15, 1, 17, 7, 9, 10, 8, 13, 6, 7, 8, 12]



```python
lst3 = []
for i, j in zip(lst1, lst2): # 
    lst3.append(i + j)
lst3
```




    [14, 3, 9, 15, 1, 17, 7, 9, 10, 8, 13, 6, 7, 8, 12]




```python
for i, j, k in zip(lst1, lst2, lst3):
    print(i, j, k)
```

    5 9 14
    2 1 3
    8 1 9
    8 7 15
    0 1 1
    9 8 17
    5 2 7
    7 2 9
    0 10 10
    1 7 8
    5 8 13
    4 2 6
    3 4 7
    0 8 8
    3 9 12



```python
lst3 = [i+j for i, j in zip(lst1, lst2)]
lst3
```




    [14, 3, 9, 15, 1, 17, 7, 9, 10, 8, 13, 6, 7, 8, 12]



# Lambda Functions


```python
def remove_as(s):
    new_string = s.replace("a", "")
    return new_string
```


```python
string1 = "this is a string with some letters and stuff in it for the sake of an example"
```


```python
remove_as(string1)
```




    'this is  string with some letters nd stuff in it for the ske of n exmple'



#### how can I write this same function as a lambda function? 


```python
remove_as = lambda s: s.replace("a", "")
```


```python
remove_as(string1)
```




    'this is  string with some letters nd stuff in it for the ske of n exmple'




```python
remove_as("here is another example")
```




    'here is nother exmple'



# How else can I manipulate this string? 


```python
# separate it by words
student_word_list = student.split(",")
student_word_list

new_student_word_list = []

for word in student_word_list:
    word = word.strip()
    new_student_word_list.append(word)
new_student_word_list
```




    ['John', 'December', 'Full Time', '2019']




```python
# replace aspects of the string
student = student.replace("December", "January")
student
```




    'John, January, Full Time, 2019'




```python
student
```




    'John, January, Full Time, 2019'



# Method chaining


```python
# method chaining example
student.replace(",", "-").replace(" ", "").lower().capitalize()
```




    'John-january-fulltime-2019'




```python
student.swapcase()
```




    'jOHN, jANUARY, fULL tIME, 2019'




```python
# endswith returns a Boolean

student.endswith("2020")
```




    False




```python
student
```




    'John, January, Full Time, 2019'




```python
# Boolean exercises
# student.endswith("2020") == True ->
# False == True
# False

bool1 = student.endswith("2020") == True
print(bool1)

# True == False
bool2 = student.endswith("2019") == student.startswith("j")
print(bool2)

# True == True
bool3 = student[-1].isdigit() == student.startswith("J")
print(bool3)
```

    False
    False
    True



```python
True == 1

```




    True




```python
student.startswith("j")
```




    False




```python
True + True + False + True * (True + True) # 1 + 1 + 0 + 1(2)
```




    4




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
x = 4 if p else 10 # inline conditional
x
```




    4




```python
sleep = 4
tired = True if sleep < 8 else False
tired
```




    True




```python
y = 10
# send me a line of code that sets x to 2 if y is > 0 otherwise set x to 10
x = 2 if y > 0 else 10
x
```




    2




```python
import pandas as pd
import numpy as np

from collections import defaultdict

import matplotlib.pyplot as plt
```

### List comprehension


```python
# declare an empty list that I will populate
triples = []

# populating my list
for i in range(10):
    triples.append(3*i)

triples
```




    [0, 3, 6, 9, 12, 15, 18, 21, 24, 27]




```python
# square of every element in triples
y = []

for element in triples: # 0, 3, 6, ...
    y.append(element**2) # y.append(0), y.append(9), y.append(36), ...
y

```




    [0, 9, 36, 81, 144, 225, 324, 441, 576, 729]




```python
# list comprehension
y = [element**2 for element in triples]
y
```




    [0, 9, 36, 81, 144, 225, 324, 441, 576, 729]




```python
# loop through both of my lists, triples and y
# for i in range(10)

for i in range(len(triples)):# i = 0, 1
    print(triples[i]) # triples[0], triples[1]
    print(y[i]) # y[0], y[1]
    print('\n')
```

    0
    0
    
    
    3
    9
    
    
    6
    36
    
    
    9
    81
    
    
    12
    144
    
    
    15
    225
    
    
    18
    324
    
    
    21
    441
    
    
    24
    576
    
    
    27
    729
    
    



```python
x = [1, 2, 3, 4, 3, 2, 1, 5, 5]
```


```python
# using the zip function
# let's make a dictionary 
# d[triples] = y {0: 0, 3: 9, 6: 36, ... }

triples_squared_dict = {}

for e1, e2 in zip(triples, y):
    triples_squared_dict[e1] = e2
    
triples_squared_dict
```




    {0: 0,
     3: 9,
     6: 36,
     9: 81,
     12: 144,
     15: 225,
     18: 324,
     21: 441,
     24: 576,
     27: 729}




```python
triples_squared_dict = dict(zip(triples, y))
triples_squared_dict
```




    {0: 0,
     3: 9,
     6: 36,
     9: 81,
     12: 144,
     15: 225,
     18: 324,
     21: 441,
     24: 576,
     27: 729}




```python
# Show you some more awesomeness with zip and dict
new_dictionary = dict(zip(triples, [t/2 for t in triples]))
new_dictionary
```




    {0: 0.0,
     3: 1.5,
     6: 3.0,
     9: 4.5,
     12: 6.0,
     15: 7.5,
     18: 9.0,
     21: 10.5,
     24: 12.0,
     27: 13.5}




```python
print(new_dictionary[0]) # 0.0
print(new_dictionary[24]) # 12.0
print(new_dictionary[25]) # error
```

    0.0
    12.0



    ---------------------------------------------------------------------------

    KeyError                                  Traceback (most recent call last)

    <ipython-input-68-19adcd930e85> in <module>
          1 print(new_dictionary[0]) # 0.0
          2 print(new_dictionary[24]) # 12.0
    ----> 3 print(new_dictionary[25]) # error
    

    KeyError: 25



```python
new_dictionary.get(0, "does not exist, dude")
```




    0.0




```python
new_dictionary.get(25, 1234)
```




    1234



### Assessment
* inline, looping through more than one list and zip
* New methods for dictionary (zip, get)
* learned to use tab to know how to I can manipulate strings
* Learned about retrieving information from dictionaries and about the zip function
* I learned about the wonderment of zip()
* Love the zip shortI thought in the last example that [0], [24] and [25] were calling the index #, so I learned is actually calling the value for that key. cuts and the other inline shortcuts
* Learned - created a dictionary by zipping two lists, while using a for loop for one of the lists.
* I really liked the zip function
* learned that in _ line conditionals can ve used in zip functions
* how to use the dictionary methods zip and get
* Learned how to create dictionaries from data using particular python functions
* Reinforced the comparative operator and the zip func
* simple  if/else  statement can be coded in one line using inline condition


```python

```
