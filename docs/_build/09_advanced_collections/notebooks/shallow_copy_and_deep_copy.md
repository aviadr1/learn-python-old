---
redirect_from:
  - "/09-advanced-collections/notebooks/shallow-copy-and-deep-copy"
interact_link: content/09_advanced_collections/notebooks/shallow_copy_and_deep_copy.ipynb
kernel_name: python3
has_widgets: false
title: 'Shallow Copy And Deep Copy'
prev_page:
  url: /09_advanced_collections/notebooks/list_comprehension_sin.html
  title: 'List Comprehension Sin'
next_page:
  url: /09_advanced_collections/notebooks/template_for_list_comprehension.html
  title: 'Template For List Comprehension'
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---
<a href="https://colab.research.google.com/github/aviadr1/learn-python/blob/master/content/09_advanced_collections/notebooks/shallow_copy_and_deep_copy.ipynb" target="_blank">
<img src="https://colab.research.google.com/assets/colab-badge.svg" 
     title="Open this file in Google Colab" alt="Colab"/>
</a>




<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
bank = [
    {"name" : "avi", "money" : 100, "city" : "rehovot"},
    {"name" : "ben", "money" : -20, "city" : "raanana"},
    {"name" : "carrie", "money" : 500, "city" : "tel-aviv"},
    {"name" : "david", "money" : 250, "city" : "nes-ziona"},
    {"name" : "efrat", "money" : 1000, "city" : "beer-sheeva"},
    {"name" : "fred", "money" : 50, "city" : "yafo"},
]

```
</div>

</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
bank_by_money = sorted(bank, key=lambda customer: customer['money'])

```
</div>

</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
bank_by_money

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">


{:.output_data_text}
```
[{'name': 'ben', 'money': -20, 'city': 'raanana'},
 {'name': 'fred', 'money': 50, 'city': 'yafo'},
 {'name': 'avi', 'money': 100, 'city': 'rehovot'},
 {'name': 'david', 'money': 250, 'city': 'nes-ziona'},
 {'name': 'carrie', 'money': 500, 'city': 'tel-aviv'},
 {'name': 'efrat', 'money': 1000, 'city': 'beer-sheeva'}]
```


</div>
</div>
</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
bank

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">


{:.output_data_text}
```
[{'name': 'avi', 'money': 100, 'city': 'rehovot'},
 {'name': 'ben', 'money': -20, 'city': 'raanana'},
 {'name': 'carrie', 'money': 500, 'city': 'tel-aviv'},
 {'name': 'david', 'money': 250, 'city': 'nes-ziona'},
 {'name': 'efrat', 'money': 1000, 'city': 'beer-sheeva'},
 {'name': 'fred', 'money': 50, 'city': 'yafo'}]
```


</div>
</div>
</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
bank_by_money

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">


{:.output_data_text}
```
[{'name': 'ben', 'money': -20, 'city': 'raanana'},
 {'name': 'fred', 'money': 50, 'city': 'yafo'},
 {'name': 'avi', 'money': 100, 'city': 'rehovot'},
 {'name': 'david', 'money': 250, 'city': 'nes-ziona'},
 {'name': 'carrie', 'money': 500, 'city': 'tel-aviv'},
 {'name': 'efrat', 'money': 1000, 'city': 'beer-sheeva'}]
```


</div>
</div>
</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
bank_by_money[0]['city'] = 'eilat'

```
</div>

</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
bank_by_money

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">


{:.output_data_text}
```
[{'name': 'ben', 'money': -20, 'city': 'eilat'},
 {'name': 'fred', 'money': 50, 'city': 'yafo'},
 {'name': 'avi', 'money': 100, 'city': 'rehovot'},
 {'name': 'david', 'money': 250, 'city': 'nes-ziona'},
 {'name': 'carrie', 'money': 500, 'city': 'tel-aviv'},
 {'name': 'efrat', 'money': 1000, 'city': 'beer-sheeva'}]
```


</div>
</div>
</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
bank

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">


{:.output_data_text}
```
[{'name': 'avi', 'money': 100, 'city': 'rehovot'},
 {'name': 'ben', 'money': -20, 'city': 'eilat'},
 {'name': 'carrie', 'money': 500, 'city': 'tel-aviv'},
 {'name': 'david', 'money': 250, 'city': 'nes-ziona'},
 {'name': 'efrat', 'money': 1000, 'city': 'beer-sheeva'},
 {'name': 'fred', 'money': 50, 'city': 'yafo'}]
```


</div>
</div>
</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
bank2 = bank

```
</div>

</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
bank2

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">


{:.output_data_text}
```
[{'name': 'avi', 'money': 100, 'city': 'rehovot'},
 {'name': 'ben', 'money': -20, 'city': 'eilat'},
 {'name': 'carrie', 'money': 500, 'city': 'tel-aviv'},
 {'name': 'david', 'money': 250, 'city': 'nes-ziona'},
 {'name': 'efrat', 'money': 1000, 'city': 'beer-sheeva'},
 {'name': 'fred', 'money': 50, 'city': 'yafo'}]
```


</div>
</div>
</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
bank2.append({'name' : "greg", "money" : 10000, "city" : "NY"})

```
</div>

</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
bank2


```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">


{:.output_data_text}
```
[{'name': 'avi', 'money': 100, 'city': 'rehovot'},
 {'name': 'ben', 'money': -20, 'city': 'eilat'},
 {'name': 'carrie', 'money': 500, 'city': 'tel-aviv'},
 {'name': 'david', 'money': 250, 'city': 'nes-ziona'},
 {'name': 'efrat', 'money': 1000, 'city': 'beer-sheeva'},
 {'name': 'fred', 'money': 50, 'city': 'yafo'},
 {'name': 'greg', 'money': 10000, 'city': 'NY'}]
```


</div>
</div>
</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
bank

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">


{:.output_data_text}
```
[{'name': 'avi', 'money': 100, 'city': 'rehovot'},
 {'name': 'ben', 'money': -20, 'city': 'eilat'},
 {'name': 'carrie', 'money': 500, 'city': 'tel-aviv'},
 {'name': 'david', 'money': 250, 'city': 'nes-ziona'},
 {'name': 'efrat', 'money': 1000, 'city': 'beer-sheeva'},
 {'name': 'fred', 'money': 50, 'city': 'yafo'},
 {'name': 'greg', 'money': 10000, 'city': 'NY'}]
```


</div>
</div>
</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
bank_shallow_copy = bank[:]

```
</div>

</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
del bank_shallow_copy[-1]

```
</div>

</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
bank_shallow_copy

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">


{:.output_data_text}
```
[{'name': 'avi', 'money': 100, 'city': 'rehovot'},
 {'name': 'ben', 'money': -20, 'city': 'eilat'},
 {'name': 'carrie', 'money': 500, 'city': 'tel-aviv'},
 {'name': 'david', 'money': 250, 'city': 'nes-ziona'},
 {'name': 'efrat', 'money': 1000, 'city': 'beer-sheeva'},
 {'name': 'fred', 'money': 50, 'city': 'yafo'}]
```


</div>
</div>
</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
bank

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">


{:.output_data_text}
```
[{'name': 'avi', 'money': 100, 'city': 'rehovot'},
 {'name': 'ben', 'money': -20, 'city': 'eilat'},
 {'name': 'carrie', 'money': 500, 'city': 'tel-aviv'},
 {'name': 'david', 'money': 250, 'city': 'nes-ziona'},
 {'name': 'efrat', 'money': 1000, 'city': 'beer-sheeva'},
 {'name': 'fred', 'money': 50, 'city': 'yafo'},
 {'name': 'greg', 'money': 10000, 'city': 'NY'}]
```


</div>
</div>
</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
import copy

```
</div>

</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
deep_copy_bank = copy.deepcopy(bank)

```
</div>

</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
deep_copy_bank

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">


{:.output_data_text}
```
[{'name': 'avi', 'money': 100, 'city': 'rehovot'},
 {'name': 'ben', 'money': -20, 'city': 'eilat'},
 {'name': 'carrie', 'money': 500, 'city': 'tel-aviv'},
 {'name': 'david', 'money': 250, 'city': 'nes-ziona'},
 {'name': 'efrat', 'money': 1000, 'city': 'beer-sheeva'},
 {'name': 'fred', 'money': 50, 'city': 'yafo'},
 {'name': 'greg', 'money': 10000, 'city': 'NY'}]
```


</div>
</div>
</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
deep_copy_bank[0]["money"] = 10000000000

```
</div>

</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
deep_copy_bank

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">


{:.output_data_text}
```
[{'name': 'avi', 'money': 10000000000, 'city': 'rehovot'},
 {'name': 'ben', 'money': -20, 'city': 'eilat'},
 {'name': 'carrie', 'money': 500, 'city': 'tel-aviv'},
 {'name': 'david', 'money': 250, 'city': 'nes-ziona'},
 {'name': 'efrat', 'money': 1000, 'city': 'beer-sheeva'},
 {'name': 'fred', 'money': 50, 'city': 'yafo'},
 {'name': 'greg', 'money': 10000, 'city': 'NY'}]
```


</div>
</div>
</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
bank

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">


{:.output_data_text}
```
[{'name': 'avi', 'money': 100, 'city': 'rehovot'},
 {'name': 'ben', 'money': -20, 'city': 'eilat'},
 {'name': 'carrie', 'money': 500, 'city': 'tel-aviv'},
 {'name': 'david', 'money': 250, 'city': 'nes-ziona'},
 {'name': 'efrat', 'money': 1000, 'city': 'beer-sheeva'},
 {'name': 'fred', 'money': 50, 'city': 'yafo'},
 {'name': 'greg', 'money': 10000, 'city': 'NY'}]
```


</div>
</div>
</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
xxx = [[1] , [2], [3] ]

```
</div>

</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
yyy = xxx[:]

```
</div>

</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
yyy

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">


{:.output_data_text}
```
[[1], [2], [3]]
```


</div>
</div>
</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
yyy.append( [4])

```
</div>

</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
yyy

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">


{:.output_data_text}
```
[[1], [2], [3], [4]]
```


</div>
</div>
</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
xxx

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">


{:.output_data_text}
```
[[1], [2], [3]]
```


</div>
</div>
</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
del yyy[0]

```
</div>

</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
yyy

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">


{:.output_data_text}
```
[[2], [3], [4]]
```


</div>
</div>
</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
xxx

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">


{:.output_data_text}
```
[[1], [2], [3]]
```


</div>
</div>
</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
yyy[0][0] = "gotcha"

```
</div>

</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
xxx

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">


{:.output_data_text}
```
[[1], ['gotcha'], [3]]
```


</div>
</div>
</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
zzz = copy.copy(xxx)

```
</div>

</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
zzz.copy

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">


{:.output_data_text}
```
<function list.copy>
```


</div>
</div>
</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
help(zzz.copy)

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">
{:.output_stream}
```
Help on built-in function copy:

copy(...) method of builtins.list instance
    L.copy() -> list -- a shallow copy of L

```
</div>
</div>
</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
zzz[0][0] = "shallow is not deep"

```
</div>

</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
xxx

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">


{:.output_data_text}
```
[['shallow is not deep'], ['gotcha'], [3]]
```


</div>
</div>
</div>

