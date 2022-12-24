# Creating Decorators

1. Decorator (Using function)

```python
def star(func):
    def inner(*args, **kwargs):
        print("*" * 30)
        func(*args, **kwargs)
        print("*" * 30)

    return inner

@star
def printer(msg):
    print(msg)


printer("Hello")

>>> 
******************************
Hello
******************************
```
\
2. Using class

```python
class star:
    def __init__(self, func):
        self.func = func

    def inner(self, *args, **kwargs):
        print("*" * 30)
        self.func(*args, **kwargs)
        print("*" * 30)

    def __call__(self, *args, **kwargs):
        """This allows you to call the function"""
        return self.inner(*args, **kwargs)
    
@star
def printer(msg):
    print(msg)


printer("Hello")

>>> 
******************************
Hello
******************************
```
