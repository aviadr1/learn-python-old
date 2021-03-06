---
redirect_from:
  - "/09-advanced-collections/exercise/questions"
interact_link: content/09_advanced_collections/exercise/questions.ipynb
kernel_name: python3
has_widgets: false
title: 'Questions'
prev_page:
  url: /09_advanced_collections/exercise/questions.html
  title: 'exercise'
next_page:
  url: /09_advanced_collections/exercise/solutions.html
  title: 'Solutions'
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---
<a href="https://colab.research.google.com/github/aviadr1/learn-python/blob/master/content/09_advanced_collections/exercise/questions.ipynb" target="_blank">
<img src="https://colab.research.google.com/assets/colab-badge.svg" 
     title="Open this file in Google Colab" alt="Colab"/>
</a>




# List comprehension



### simple list comprehension: powers of 2
use __list comprehension__ to compute a list containing the powers of 2:
i.e.  `[2**0, 2**1, 2**2, 2**3, ..., 2**15]`

> NOTE: the code should be one just line <br>
> reminder: list comprehensions look like `[ _____ for _____ in ____ ]` where you fill in the blanks 





### list comprehension with filtering
take the sentnence `"everything shuold be as simple as possible but no simpler"` (this is a qoute by albert einstein). <br>
use list comprehension to 
1. take only words that are shorter than 6 letters
2. convert words to uppercase
  
expected output:
```['BE', 'AS', 'AS', 'BUT', 'NO']```
  
> reminder: list comprehension with filtering has the form `[ _____ for ____ in ____ if ____ ]`



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
### useful: the qoute to work on
words = "everything should be as simple as possible but no simpler".split()

```
</div>

</div>



### max length of words in a list
using JUST ONE LINE, find the length of the longest word in a given sentence
    
hints - use the functions `str.split()`, `max()` and `len()`:
- break the sentence into words using the function `str.split()`
- use __list comprehension__ to compute the length of all words
- use the function `max` to get the maximum length from the list of lengths



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
### useful: sentence to work on from "life of brian" 
brian = """“
Alright, but apart from the sanitation, the medicine, education, wine, public order, 
irrigation, roads, the fresh-water system, and public health, 
what have the Romans ever done for us?”
"""

```
</div>

</div>



### max lengh of words, and the actual word too

build on the [previous exercise](#max-length-of-words-in-a-list) <br>
now, get the _length_ of the longest word _as well as_ the __actual word__

expected output for the life of brian qoute:
```
[11, 'sanitation']
```

or alternatively:
```
[[11, 'sanitation,'], [11, 'irrigation,'], [11, 'fresh-water']]
```



### multiple comprehensions
for the list of "interesting" angles: `0, 30, 60, 90, 120, 150, 180`
   
   a) compute the list of radian values using list comprehension
   ```
        0  --> 0
        30 --> 30 *math.pi/180
        60 --> 60 *math.pi/180
         x -->  x *math.pi/180
       180 --> 180*math.pi/180
   ```      
   b) compute the math.sin value for each of the rad from (a) using list comprehension
   ```
        0        --> math.sin(0)
        x        --> math.sin(x)
   ```
   
   c) use the format `"{:.2f}"` and list comprehension to compute nicely formatted strings for the numbers in (b)
   ```
      x --> "{:.2f}".format(x)
   ```
   
expected output:
```
['0.00', '0.50', '0.87', '1.00', '0.87', '0.50', '0.00']
```



### dictionary comprehension
a restaurant stores the menu and prices of items in a dictionary.
now it needs to __double the prices of all the items__.
can you do this in one line with a __dictionary comprehension__?
   ```
   menu = {
       'steak' : 150,
       'falafel' : 20,
       'pizza' : 59,
       'hamburger' : 63,
       'chips' : 18,
       'salad' : 30
   }
   ```
   
> reminders: 
  - dictionary comprehension has the form `{ ____ : ____ for ___ in ____ }`
  - remember the `.items()` function of dictionaries



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
### useful: here is the menu
menu = {
       'steak' : 150,
       'falafel' : 20,
       'pizza' : 59,
       'hamburger' : 63,
       'chips' : 18,
       'salad' : 30
   }

```
</div>

</div>



### dictionary comprehension with filtering

> doubling all prices turns out to be too expensive !

we want raise prices in a different way:
1. remove all the items that already cost 100 NIS or more from the menu
2. all other items should have their price increased by 20%
3. make sure every price is in whole shekels (no pennies / agorot) 

> hint: 
  - instead of removing, just keep the ones that are cheaper than 100
  - use the function `round()`
  
expected output:
```
{'falafel': 24, 'pizza': 71, 'hamburger': 76, 'chips': 22, 'salad': 36}
```



### cost of a meal

People came into our restaurant and ordered a meal for the table:
```
order = ['steak', 'steak', 'steak', 'falafel', 'chips', 'salad', 'salad']
```
lets use the original menu
  ```
   menu = {
       'steak' : 150,
       'falafel' : 20,
       'pizza' : 59,
       'hamburger' : 63,
       'chips' : 18,
       'salad' : 30
   }
   ```

and _using list comprehension_ calculate the cost of the meal
hint:
- use list comprehension
- use the function `sum()`

expected output:
```
548
```

> also see [This video](https://www.youtube.com/watch?v=kyCWPqQYHEA)



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
### useful: the order
order = ['steak', 'steak', 'steak', 'falafel', 'chips', 'salad', 'salad']

```
</div>

</div>



### 😵Create a matrix using list comprehension
use list comprehension to create an NxM marix with numbers going from 0 to NxM
> hint: you need nested list comprehension - list comprehension within list comprehension

example with N=6 M=4
```
[[0,  1,  2,  3],
 [4,  5,  6,  7],
 [8,  9,  10, 11],
 [12, 13, 14, 15],
 [16, 17, 18, 19],
 [20, 21, 22, 23]]
```



### set comprehension

use set comprehension to find all the unique words in the song "knights of the round table" by monty python

> 1. sort the words in the set using the `sorted()` function 
> 1. see if there are words that look similar
> 2. remove duplicates by turning all words into lowercase
> 3. use the `.replace('.', '')` function to remove the coma `'.'` characters in words
      - alernatively remove special characters using the `str.translate()` and `str.maketrans()` functions
> 4. print all the unique words in this song




<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
### useful: song lyrics
knights_of_round_table = """
We're knights of the round table
We dance whene'er we're able
We do routines and scenes
With footwork impeccable.
We dine well here in Camelot
We eat ham and jam and spam a lot.
We're knights of the Round Table
Our shows are formidable
But many times we're given rhymes
That are quite unsingable
We're opera mad in Camelot
We sing from the diaphragm a lot.
In war we're tough and able.
Quite indefatigable
Between our quests we sequin vests
And impersonate Clark Gable
It's a busy life in Camelot.
I have to push the pram a lot.
"""

```
</div>

</div>



### using sets to test a password
can you use a `set` to check that a password has one of the following special characters:
```
special_chars = """!@#$%^&*()-=_+`~;'"|/.,<>?"""
```
    
hint: it requires only one line, no loops and no list comprehension



# pprint



sometimes regular old `print()` makes it difficult to read a data structure.
for instance take a look at the following code

```
people = [
    ['adva', 28, 'physicist'],
    ['ben', 25, 'hairdresser'],
    ['carmel', 30, 'mountaineer'],
    ['daria', 32, 'doctor'],
    ['edward', 45, 'king']
    ]

print(people)
```

1. whats weird or annoying about the output of the program? try it yourself
2. run the following code which imports a __pretty print__ function called `pprint`
    ```
    from pprint import pprint
    pprint(people)
    ```
   any differece?
3. read the documentation of the pprint function https://docs.python.org/3.7/library/pprint.html
4. try using pprint with parameter `depth=1`
4. try using pprint with parameter `indent=4`



# zip



### basic use of the zip function
look at the following code, read it, can you figure out what it does?

```
fruits = ["apricots", "banannas", "cherries"]
colors = ["pink", "yellow", "red"]
for fruit, color in zip(fruits, colors):
    print(fruit, "are", color)
```

1. copy the code below and try it for yourself to see if your were right

2. read the documentation for the zip function https://docs.python.org/3.7/library/functions.html#zip

3.  we have data about people in **columns**
    ```
    first_name_column = ['adva', 'ben', 'carmel']
    age_column = [28, 25, 30]
    job_column = ['physicist', 'hairdresser', 'mountaineer']
    ```
    we would like to print data about each person with one **row per person**, in csv format
   
    expected output:
    ```
    adva, 28, physicist
    ben, 25, hairdresser
    carmel, 30, mountaineer
    daria, 32, doctor
    edward, 45, king
    ```

4. now we want the data as a list of lists,
   that is a list of rows, where each row is the data for a person

   expected output ( **use `pprint()`** ):
    ```
    [['adva', 28, 'physicist'],
     ['ben', 25, 'hairdresser'],
     ['carmel', 30, 'mountaineer'],
     ['daria', 32, 'doctor'],
     ['edward', 45, 'king']]
    ```
    
   hint: we provide a few solutions, its worthwhile to go through them




<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
### useful: data
first_name_column = ['adva', 'ben', 'carmel', 'daria', 'edward']
age_column = [28, 25, 30, 32, 45]
job_column = ['physicist', 'hairdresser', 'mountaineer', 'doctor', 'king']


```
</div>

</div>



### unzipping
> There’s a question that comes up frequently in forums for new Pythonistas: “If there’s a `zip()` function, then why is there no `unzip()` function that does the opposite?”

> The reason why there’s no `unzip()` function in Python is because the opposite of `zip()` is… well, `zip()`. So, how do you unzip Python objects?

here's a trick:
```
rows = [['adva', 28, 'physicist'],
        ['ben', 25, 'hairdresser'],
        ['carmel', 30, 'mountaineer'],
        ['daria', 32, 'doctor'],
        ['edward', 45, 'king']]

# notice the * unpacking operator
name_col, age_col, job_col = zip(*rows)

print(name_col)
print(age_col)
print(job_col)
```

notice how it turns rows of data into columns of data?

1. now, using just one line, calculate a variable called `columns` from `rows` using `zip()`. 

   print `columns` ( **use `pprint()`** )
   
2. now, using just one line, reverse `columns` back into rows using `zip()`

> **you've learned how to transpose between columns and rows of data**



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
### useful: data
rows = [['adva', 28, 'physicist'],
        ['ben', 25, 'hairdresser'],
        ['carmel', 30, 'mountaineer'],
        ['daria', 32, 'doctor'],
        ['edward', 45, 'king']]

```
</div>

</div>



# Generators and coroutins



### `even_numbers()` infinite lazy list
1. write a function called `even_numbers()` that returns an infinite lazy list with all the even numbers
```
0, 2, 4, 6, 8, ...
```
> hint: write a generator function (function with 'yield' statement) with an infinite loop

2. call `even_numbers()` and use the `next()` function to print the first 3 values from the list

3. use a combination of the `zip()` function with the `range(20)` function to create a lazy list of the next 20 numbers.
   use a `for` loop to iterate over the shorter list





### `line_reader()`
> did you ever think about how *```for line open('myfile')```* actually works?

imagine files had only one function: `.readline()`

can you write a generator function called `line_reader` so that you could still write an easy for loop over the file's content?

- use the `silly_open()` function provided below to get file objects that indeed only have a `.readline()` function and nothing else

after your write your `line_reader` function you should be able to write code like this
```
f = silly_open('knights.txt')
for line in line_reader(f):
    print(line)
```



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
### useful:
### 1) create a 'knights.txt' 
### 2) create a silly_open() function that returns a file with just a .readline() function

with open('knights.txt', 'w') as f:
    f.write(knights_of_round_table)

def silly_open(filename):
    # define a "Stupid File" which only has a 'readline()' function
    class StupidFile:
        def __init__(self, f):
            self.__f = f
        def readline(self):
            return self.__f.readline()
        def close(self):
            self.__f.close()
    
    # open the file 'knights.txt' for reading
    f = StupidFile(open(filename, 'r'))
    return f

### notice that the following for loop can't work
# for line in silly_open('knights.txt'):
#     print(line)

```
</div>

</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
### useful: test for your line_reader() function
f = silly_open('knights.txt')
for line in line_reader(f):
    print(line.rstrip())

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">
{:.output_stream}
```

We're knights of the round table
We dance whene'er we're able
We do routines and scenes
With footwork impeccable.
We dine well here in Camelot
We eat ham and jam and spam a lot.
We're knights of the Round Table
Our shows are formidable
But many times we're given rhymes
That are quite unsingable
We're opera mad in Camelot
We sing from the diaphragm a lot.
In war we're tough and able.
Quite indefatigable
Between our quests we sequin vests
And impersonate Clark Gable
It's a busy life in Camelot.
I have to push the pram a lot.
```
</div>
</div>
</div>



### yield triangles
remember the function `triangle(n)` that prints a triangle?
```
def triangle(n):
    for i in range(1, n+1):
        print("*" * i)
```
    
1) rewrite this function with yield so that it yields every line of the triangle instead of printing it
2) do a for loop on the function and print each line
3) take all the lines from the functions into a list, print the list



### yield passwords
can you write a generator function (function with 'yield' statement) that:
1. uses input() to ask the user for a password
2. checks the password (not too long, not too short, has both upper and lower characters)

