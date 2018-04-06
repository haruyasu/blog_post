## Counter
It is a dict subclass for counting hashable objects and an unordered collection where elements are stored as dictionary keys and their counts are stored as dictionary values.

### Example
```python
from collections import Counter

data = ['a', 'b', 'c', 'a', 'd']
counter = Counter(data)
print(counter)
# Counter({'a': 2, 'b': 1, 'c': 1, 'd': 1})

for i in counter.values():
    print(i)
# 2
# 1
# 1
# 1
```
```python
myword = "helloworld!"
mycounter = Counter(myword)
print(mycounter)
# Counter({'l': 3, 'o': 2, '!': 1, 'e': 1, 'd': 1, 'h': 1, 'r': 1, 'w': 1})
```
```python
phrase = "my motto is one for all all for one"
words = phrase.split()
mycounter = Counter(words)
print(mycounter)
# Counter({'one': 2, 'for': 2, 'all': 2, 'my': 1, 'motto': 1, 'is': 1})
```
```python
for i in mycounter.keys():
    if i == "for":
        print(mycounter[i])
# 2
```