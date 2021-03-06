---
redirect_from:
  - "/12-exceptions/exercise/solutions"
interact_link: content/12_exceptions/exercise/solutions.ipynb
kernel_name: python3
has_widgets: false
title: 'Solutions'
prev_page:
  url: /12_exceptions/exercise/questions.html
  title: 'Questions'
next_page:
  url: /12_exceptions/notebooks/exceptions.html
  title: 'notebooks'
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---
<a href="https://colab.research.google.com/github/aviadr1/learn-python/blob/master/content/12_exceptions/exercise/solutions.ipynb" target="_blank">
<img src="https://colab.research.google.com/assets/colab-badge.svg" 
     title="Open this file in Google Colab" alt="Colab"/>
</a>




# convert to int
use a loop and the `int` function to find all the numbers embedded in the quote given below.
- hint: use `try/except` so that things which are not numbers wont stop your loop

expected outout:
```
[3, 3, 3, 4, 2, 3, 5]
```



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
### useful: use the `int` functions to grab all the numbers from this string
holy_hand_grenade_of_antioch = """\
First shalt thou take out the Holy Pin, 
then shalt thou count to 3 , no more, no less. 
3 shall be the number thou shalt count, and the number of the counting shall be 3 . 
4 shalt thou not count, neither count thou 2 , excepting that thou then proceed to 3 . 
5 is right out."""

```
</div>

</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
numbers = []
for word in holy_hand_grenade_of_antioch.split():
    try:
        numbers.append(int(word))
    except:
        pass
    
print(numbers)

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">
{:.output_stream}
```
[3, 3, 3, 4, 2, 3, 5]
```
</div>
</div>
</div>



# finally

we've provided an important function called `answer_to_universe_and_everything()`
1. open a file called `'answer.txt'` for writing
2. use a loop to call `answer_to_universe_and_everything()` a 100 times, and write the results to the file
3. use a `try/except` block to make sure that if answer_to_universe_and_everything() fails, we continue to call the function
4. if the function fails, write the fail message to the file
4. use a `try/finally` block to make sure we close the file
5. make sure the file indeed has exactly 100 lines




<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
### useful: use this function
def answer_to_universe_and_everything():
    import random
    x = random.randint(0, 10)
    if x<3:
        return 'need more time'
    elif x<6:
        return 'blue ... no, red!'
    elif x<9:
        raise Exception('too hard')
    else:
        return 42
    

```
</div>

</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
f = open('answer.txt', 'w')
try:
    for i in range(100):
        try:
            print(answer_to_universe_and_everything(), file=f)
        except Exception as ex:
            print (ex, file=f)
finally:
    f.close()
        
        

```
</div>

</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
### useful: show that the file has 100 lines
assert len(open('answer.txt').readlines()) == 100

```
</div>

</div>

