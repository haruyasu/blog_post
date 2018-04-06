## The input Function
One way to get data is directly from the user.

### Example
```python
# IN abcde
s = input()
# OUT "abcde"
```
```python
# IN 5
a = int(input())
# OUT 5
```
```python
# IN abcde
s = list(input())
# OUT ["a", "b", "c", "d", "e"]
```
```python
# IN 1 2
x, y = map(int, input().split())
# OUT x = 1, y = 2
```
```python
# IN 1 2 3 4 ... n
li = input().split()
# OUT ["1", "2", "3"...."n"]
```
```python
# IN 1 2 3 4 ... n
li = list(map(int, input().split()))
# OUT [1, 2, 3, 4 ... n]
```
```python
# IN 1,2,3,4....n
li = list(map(int, input().split(",")))
# OUT [1, 2, 3, 4 ... n]
```
```python
# IN
# 3
# test1
# test2
# test3
n = int(input())
li = [input() for i in range(n)]
# OUT ["test1", "test2", "test3"]
```
```python
# IN
# a
# b
# c
# ...
# (EOF)
import sys

li = []
for line in sys.stdin:
    li.append(str(line).replace('\n', ''))
# OUT ["a", "b", "c"]
```
```python
# IN
# 3 4
# 1 2 3 4
# 5 6 7 8
# 9 0 1 2
n, m = map(int, input().split())
li = []
for i in range(m):
    li.append(list(map(int, input().split())))
# OUT [[1, 2, 3, 4], [5, 6, 7, 8], [9, 0, 1, 2]]
```
```python
# IN
# 1 2 3 4
# 5 6 7 8
# 9 0 1 2
# ...
# (EOF)
li = []
while True:
    try:
        li.append(list(map(int, input().split())))
    except:
        break
# OUT [[1, 2, 3, 4], [5, 6, 7, 8], [9, 0, 1, 2]]
```
