## Enumerate
Enumerate is really useful function.  
It returns an enumerate(index) object.

### Example
```python
names = ["a", "b", "c", "d"]
```
```python
for counter, name in enumerate(names):
    print(counter, name)
# 0 a
# 1 b
# 2 c
# 3 d
```
```python
for i, j in enumerate(range(5, 0, -1)):
    print(i, j)
# 0 5
# 1 4
# 2 3
# 3 2
# 4 1
```
```python
for i, j in enumerate(range(5, 0, -1), start=5):
    print(i, j)
# 5 5
# 6 4
# 7 3
# 8 2
# 9 1
```