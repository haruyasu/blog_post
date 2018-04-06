## Map
It applies a function to all the items in an input_list.

### Example
```python
li = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```
```python
mapped_list = list(map(lambda x: x ** 2, li))
print(mapped_list)
# [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```
```python
def plus(num):
    return num + 10
mapped_list = list(map(plus, li))
print(mapped_list)
# [10, 11, 12, 13, 14, 15, 16, 17, 18, 19]
```
```python
mapped_list = list(map(lambda num: num+20, li))
print(mapped_list)
# [20, 21, 22, 23, 24, 25, 26, 27, 28, 29]
```

## Filter
It creates a list of elements for which a function returns true.

### Example
```python
filtered_list = list(filter(lambda num: num % 2 == 1, li))
print(filtered_list)
# [1, 3, 5, 7, 9]
```

## Reduce
It applies a rolling computation to sequential pairs of values in a list.

### Example
```python
product = 1
li = [1, 2, 3, 4]
for num in li:
    product = product * num
print(product)
# 24
```
