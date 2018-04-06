## Tuples
A tuple is similar to a list except that a literal tuple is enclosed in parentheses rather than square brackets, and a tuple is immutable.  
In particular you cannot change the length or substitute elements, unlike a list.

### Example
```python
a = (2, 3, 4)
print(a[0])
# 2
```
```python
print(len(a))
# 3
```
```python
print(max(a))
# 4
```
```python
print(min(a))
# 2
```
```python
print(2 in a)
# True
```
```python
print(5 in a)
# False
```