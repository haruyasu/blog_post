## The list Type
Lists are ordered sequences of arbitrary data.  
Lists are the first kind of data discussed so far that are mutable: the length of the sequence can be changed and elements substituted.

### Example
```python
li = []
li.append(1)
li.append(2)
li.append(3)
# [1, 2, 3]
```
```python
li = ["a1", "b2", "c3"]
res = ""
for i in li:
    res += i
# a1b2c3
```
```python
res = " ".join(li)
# a1 b2 c3
```
```python
res = ",".join(li)
# a1,b2,c3
```
```python
li = [1, 2, 3]
str_li = map(str, li)
res = " ".join(str_li)
# 1 2 3
```
```python
s = "a1 a2 a3"
str_list = s.split()
# ['a1', 'a2', 'a3']
```
```python
# list copy
import copy
li = [1, 2, 3]
li2 = copy.deepcopy(li)
li2.reverse()
print(li)
# [1, 2, 3]
print(li2)
# [3, 2, 1]
```
```python
li = [[1, 2, 3], [4, 5, 6]]
x = []
for i in li:
    x.extend(i)
print(x)
# [1, 2, 3, 4, 5, 6]
```
