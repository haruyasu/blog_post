## Itertools functions
The following module functions all construct and return iterators.

### Example
```python
import itertools

itr = itertools.count(5)
li = []
for i in itr:
    li.append(str(i))
    if i == 10:
        break
print(li)
# ['5', '6', '7', '8', '9', '10']
print(" ".join(li))
# 5 6 7 8 9 10
```
```python
itr = itertools.cycle("ABC")
li = []
for i, j in enumerate(itr):
    li.append(str(j))
    if i == 5:
        break
print(li)
# ['A', 'B', 'C', 'A', 'B', 'C']
print(" ".join(li))
# A B C A B C
```
```python
itr = itertools.repeat("ABC", 3)
print([i for i in itr])
# ['ABC', 'ABC', 'ABC']
```
```python
itr = itertools.chain("ABC", range(5))
print(list(itr))
# ['A', 'B', 'C', 0, 1, 2, 3, 4]
```
```python
itr = itertools.compress('ABCDEF', [1, 0, 1, 0, 0, 1])
print(list(itr))
# ['A', 'C', 'F']
```
```python
p = lambda x: x < 5
li = [1, 4, 5, 1, 9, 3, 6]
itr = itertools.dropwhile(p, li)
print(list(itr))
# [5, 1, 9, 3, 6]
```
```python
p = lambda x: x < 5
li = [1, 4, 2, 1, 9, 3, 6]
itr = itertools.takewhile(p, li)
print(list(itr))
# [1, 4, 2, 1]
```
```python
for k, g in itertools.groupby(sorted("AAAABBCCCDDDEEEFFAAACC"), key=list):
    print(k, len([i for i in g]), end=', ')
# ['A'] 7, ['B'] 2, ['C'] 5, ['D'] 3, ['E'] 3, ['F'] 2,
print("")
```
```python
itr = itertools.islice(range(10), 3, None, 2)
print(list(itr))
# [3, 5, 7, 9]
```
```python
tpls = [(2, 3), (3, 4), (6, 8)]
itr = itertools.starmap(lambda x, y: x * y, tpls)
print(list(itr))
# [6, 12, 48]
```
```python
# itr = itertools.izip("ABCDE","xyz")
itr = zip("ABCDE", "xyz")
print(list(itr))
# [('A', 'x'), ('B', 'y'), ('C', 'z')]
```
```python
itr = itertools.zip_longest("ABCDE", "xyz", fillvalue='-')
# itr = itertools.zip_longest("ABCDE","xyz", fillvalue='-')
print(list(itr))
# [('A', 'x'), ('B', 'y'), ('C', 'z'), ('D', '-'), ('E', '-')]
```
```python
# matrix
print(list(itertools.permutations([1, 2, 3], 2)))
# [(1, 2), (1, 3), (2, 1), (2, 3), (3, 1), (3, 2)]
```
```python
# no duplicate
print(list(itertools.combinations([1, 2, 3], 2)))
# [(1, 2), (1, 3), (2, 3)]
```