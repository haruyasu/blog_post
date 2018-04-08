## Numpy
It is the homogeneous multidimensional array and a table of elements.

### Example
```python
import numpy as np

vecx = np.array([[1, 2, 3], [4, 5, 6]])
print(vecx)
# [[1 2 3]
#  [4 5 6]]
```
```python
vecy = np.array([[4, 5, 6], [7, 8, 9]])
vecz = np.array([[1, 2, 3], [7, 8, 9], [4, 5, 6]])
print(vecx + vecy)
# [[ 5  7  9]
#  [11 13 15]]
print(vecx - vecy)
# [[-3 -3 -3]
#  [-3 -3 -3]]
print(np.dot(vecx, vecz))
# [[27 33 39]
#  [63 78 93]]

print(np.add(10, 100))
print(np.subtract(10, 100))
print(np.multiply(10, 100))
print(np.divide(100, 10))

print(np.power(2, 5))
print(np.sqrt(2))

x = np.random.randint(0, 10, size=10)
print(x)
print(np.sort(x))
print(np.sort(x)[::-1])
```
## Slice
```python
arr = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
print(arr[:2])
# [[1 2 3]
#  [4 5 6]]
print(arr[1:])
# [[4 5 6]
#  [7 8 9]]
print(arr[:3, 1:2])
# [[2]
#  [5]
#  [8]]

# 1 line
print(arr[0, :])
# [1 2 3]
# 2 line
print(arr[1, :])
# [4 5 6]

# 1 row
print(arr[:, 0])
# [1 4 7]
# 2 row
print(arr[:, 1])
# [2 5 8]
```

## Sum
```python
print(arr.sum())
# max
print(arr.max())
# min
print(arr.min())
```

## Transpose
```python
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
m = list(map(list, zip(*matrix)))
print(m)
# [[1, 4, 7], [2, 5, 8], [3, 6, 9]]
for i in m:
    print(max(i))
```
## Read CSV
```python
import csv

def read_csv_as_array(filename):
    data = []
    with open(filename) as fp:
        for row in csv.reader(fp):
            data.append([str(x) for x in row])
    return np.array(data)
data = read_csv_as_array("F:/improve_pyhton/test.csv")
print(data)
# [['P1' 'P2' 'P3' 'P4']
#  ['1' '2' '3' '4']
#  ['10' '20' '30' '40']]
```

## empty matrix
```python
e = np.zeros((2, 2), dtype=np.int64)
print(e)
# [[0 0]
#  [0 0]]
```
