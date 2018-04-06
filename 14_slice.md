## String Slices
It is also useful to extract larger pieces of a string than a single character. That brings us to slices.

### Example
```python
li = [1, 2, 3, 4, 5, 6, 7, 8, 9]

# Output from n to m-1
# a[n:m]
```
```python
li[1:4]
# [2, 3, 4]
```
```python
li[:3]
# [1, 2, 3]
```
```python
li[7:]
# [8, 9]
```
```python
li[-1]
# 9
```
```python
li[-2:]
# [8, 9]
```
```python
li[::3]
# [1, 4, 7]
```
```python
li[2:7:3]
# [3, 6]
```
```python
li[::-3]
# [9, 6, 3]
```
```python
# reverse
li[::-1]
```
