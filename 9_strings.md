## Strings
Strings of characters are really important type in Python.

### Example
```python
s = "Hello World!"
t = "Hello"
```
```python
s.capitalize()
# "Hello world!"
```
```python
s.lower()
# "hello world!"
```
```python
s.swapcase()
# "hELLO wORLD!"
```
```python
s.title()
# "Hello World!"
```
```python
s.upper()
# "HELLO WORLD!"
```
```python
s.count('o')
# 2
```
```python
s.find('W')
# 6
```
```python
s.index('W')
# 6
```
```python
s.rfind('W')
# 6
```
```python
s.rindex('W')
# 6
```
```python
s.startswith('He')
# True
```
```python
''.join(s)
# "Hello World!"
```
```python
' '.join(s)
# "H e l l o  W o r l d !"
```
```python
' '.join((s, t))
# "Hello World! Hello"
```
```python
s.lstrip('He')
# "llo World!"
```
```python
s.replace('Hello', 'My')
# "My World!"
```
```python
s.rsplit()
# ["Hello", "World!"]
```
```python
s.split()
# ["Hello", "World!"]
```
```python
s.splitlines()
# ["Hello World!"]
```
```python
s.strip()
# "Hello World!"
```
```python
s.strip('d!')
# "Hello Worl"
```
```python
s.center(30)
# "         Hello World!         "
```
```python
s.expandtabs()
# "Hello World! "
```
```python
s.ljust(30)
# "Hello World!                  "
```
```python
s.rjust(30)
# "                  Hello World!"
```
```python
s.isalnum()
# False
```
```python
s.isalpha()
# False
```
```python
s.isprintable()
# True
```
```python
s.istitle()
# True
```
```python
s.isupper()
# False
```
```python
s.isdecimal()
# False
```
```python
s.isnumeric()
# False
```
