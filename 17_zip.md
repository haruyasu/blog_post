## Zip
It makes an iterator that aggregates elements from each of the iterables.

### Example
```python
names = ["a", "b", "c", "d", "e"]
numbers = [5, 2, 4, 5, 1]
```
```python
for x, y in zip(names, numbers):
    print(x, y)
# a 5
# b 2
# c 4
# d 5
# e 1
```
```python
from itertools import zip_longest

names = ["a", "b", "c", "d", "e"]
numbers = [1, 2, 3]

for x, y in zip_longest(names, numbers, fillvalue='nostock'):
    print(x, y)
# a 1
# b 2
# c 3
# d nostock
# e nostock
```