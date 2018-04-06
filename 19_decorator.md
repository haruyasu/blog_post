## Decorator
Decorators dynamically alter the functionality of a function, method, or class without having to directly use subclasses.

### Example
```python
# decorate print
def deco(func):
    import functools
    @functools.wraps(func)
    def wrapper(*args, **kwargs):
        print("--start--")
        func(*args, **kwargs)
        print("--end--")
    return wrapper

@deco
def test():
    print("Hello World!")

test()
# --start--
# Hello World!
# --end--
```
```python
# decorate return value
def deco2(func):
    import functools
    import os
    @functools.wraps(func)
    def wrapper(*args, **kwargs):
        res = "--start--" + os.linesep
        res += func(*args, **kwargs) + "!" + os.linesep
        res += "--end--"
        return res
    return wrapper

@deco2
def test2():
    return "Hello World!"

print(test2())
# --start--
# Hello World!
# --end--
```
```python
#decorate nest .ex html
def deco_html(func):
    import functools
    @functools.wraps(func)
    def wrapper(*args, **kwargs):
        res = "<html>"
        res += func(*args, **kwargs)
        res += "</html>"
        return res
    return wrapper

def deco_body(func):
    import functools
    @functools.wraps(func)
    def wrapper(*args, **kwargs):
        res = "<body>"
        res += func(*args, **kwargs)
        res += "</body>"
        return res
    return wrapper

@deco_html
@deco_body
def test3():
    return "Hello World!"

print(test3())
# <html><body>Hello World!</body></html>
```
```python
# decorate parameter
def deco_p(func):
    import functools
    @functools.wraps(func)
    def wrapper(*args, **kwargs):
        res = "<p>"
        res += func(args[0], **kwargs)
        res += "</p>"
        return res
    return wrapper

@deco_p
def test4(str):
    return str

print(test4("Hello World!"))
# <p>Hello World!</p>
```
```python
# decorate tag
def deco_tag(tag):
    def _deco_tag(func):
        import functools
        @functools.wraps(func)
        def wrapper(*args, **kwargs):
            res = "<" + tag + ">"
            res += func(*args, **kwargs)
            res += "</" + tag + ">"
            return res
        return wrapper
    return _deco_tag

@deco_tag("html")
@deco_tag("body")
def test5():
    return "Hello World!"

print(test5())
# <html><body>Hello World!</body></html>
```