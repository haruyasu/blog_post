## Dictionaries
A dictionary is a collection of words matched with their definitions.  
Given a word, you can look up its definition.

### Example
```python
d = {'a': 30, 'b': 40, 'c': 80}
```
```python
for key, val in d.items():
    print(key, val)
# a 30
# b 40
# c 80
```
```python
for key in d.keys():
    print(key, d[key])
# a 30
# b 40
# c 80
```
```python
for val in d.values():
    print(val)
# 30
# 40
# 80
```
```python
d = {"a": "1", "b": "2", "c": "3"}
print(d)
# {'a': '1', 'b': '2', 'c': '3'}
```
```python
d = dict(a="1", b="2", c="3")
print(d)
# {'a': '1', 'b': '2', 'c': '3'}
```
```python
d["a"] = 100
print(d)
# {'a': '100', 'b': '2', 'c': 3}
```
```python
d.update(a=150, b=250, c=350)
print(d)
# {'a': 150, 'b': 250, 'c': 350}
```
```python
d.update(test=100)
print(d)
# {'a': 150, 'b': 250, 'c': 350, 'test': 100}
```
```python
d["python"] = "great"
print(d)
# {'a': 150, 'b': 250, 'c': 350, 'test': 100, 'python': 'great'}
```
```python
d = {'a': 1, 'b': 2, 'c': 3}
print(max(d.values()))
# 3
print(max([(v, k) for k, v in d.items()])[1])
# c
print(max((v, k) for (k, v) in d.items())[1])
# c
print(d.items())
# [('a', 1), ('c', 3), ('b', 2)]
```
```python
# list to dict
li1 = [("a", 3), ("b", 2), ("c", 5)]
di1 = dict(li1)
print(di1)
# {'a': 3, 'c': 5, 'b': 2}
```
```python
# list to dict
li2 = ["a", 3, "b", 2, "c", 5]
di2 = dict(zip(li2[0::2], li2[1::2]))
print(di2)
# {'a': 3, 'c': 5, 'b': 2}
```
```python
keys = ['a', 'b', 'c']
values = [10, 20, 30]

dic = dict(zip(keys, values))
print(dic)
# {'a': 10, 'c': 30, 'b': 20}
```
```python
# dict merge
d1 = {"a": 1, "b": 2}
d2 = {"b": 3, "d": 4}
dic = dict(d1, ** d2)
print(dic)
# {'a': 1, 'b': 3, 'd': 4}
```
```python
words = ["apple", "orange", "banana", "alpha", "beta"]

results = {}
for word in words:
    key = word[0]
    if key not in results:
        results[key] = []
    results[key].append(word)
print(results)
# {'a': ['apple', 'alpha'], 'b': ['banana', 'beta'], 'o': ['orange']}
```
```python
# dict.setdefault()
results2 = {}
for word in words:
    results2.setdefault(word[0], []).append(word)
print(results2)
# {'a': ['apple', 'alpha'], 'b': ['banana', 'beta'], 'o': ['orange']}
```
```python
# itertools.groupby
from itertools import groupby
from operator import itemgetter

results4 = {k: list(v) for k, v in groupby(sorted(words), key=itemgetter(0))}
print(results4)
# {'a': ['alpha', 'apple'], 'b': ['banana', 'beta'], 'o': ['orange']}
```
```python
list = [{'Key': 'Name',     'Value': 'apple'},
        {'Key': 'Color',    'Value': 'red'},
        {'Key': 'Quantity', 'Value': 10}]

name_values = [x['Value'] for x in list if x['Key'] == 'Name']
name_value = name_values[0] if len(name_values) else ''
print(name_value)
# apple
```