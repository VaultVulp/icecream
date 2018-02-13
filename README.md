<h1 align="center">
  <img src="icon.svg" width="300px" alt="icecream">
</h1>

<p align="center">
  <a href="https://pypi.python.org/pypi/icecream">
    <img src="https://badge.fury.io/py/icecream.svg">
  </a>
  <a href="https://travis-ci.org/gruns/icecream">
    <img src="https://img.shields.io/travis/gruns/icecream.svg">
  </a>
  <a href="http://unlicense.org/">
    <img src="https://img.shields.io/pypi/l/icecream.svg">
  </a>
  <a href="https://pypi.python.org/pypi/icecream">
    <img src="https://img.shields.io/pypi/pyversions/icecream.svg">
  </a>
</p>


### IceCream is a little library for sweet and creamy print debugging.

Do you ever use `print()` statements to debug your code? Of course you
do. IceCream, or `ic` for short, makes `print()` debugging a little sweeter.

IceCream is well tested, [permissively licensed](), and supports Python 2,
Python 3, PyPy2, and PyPy3.


### Ice Cream with Toppings (Arguments)

Have you ever printed variables or expressions during debugging? If you've ever
typed

```python
print(foo(obj.attr))
```

or the more thorough


```python
print('foo(obj.attr)', foo(obj.attr))
```

then `ic()` is here to help. With arguments, `ic()` inspects itself and prints
both its arguments and its argument's values.

```python
from icecream import ic

def foo():
    return 'bar'
ic(foo())
```

Prints

```
ic| foo(): bar
```

Similarly,

```python
d = {'d': {1: 'one'}}
ic(d['d'][1])

class klass():
    attr = 'yep'
ic(klass.attr)
```

Prints

```
ic| d['d'][1]: 'one'
ic| klass.attr: 'yep'
```

Easy.


### Plain Ice Cream (without Arguments)

Do you ever add print statments to determine which parts of your program are
executed, and in which order they're executed? If you've ever typed something
like

```python
def foo():
    print(0)
    first()

    if expression:
        print(1)
        second()
    else:
        print(2)
        third()
```

then `ic()` helps here, too. Without arguments, `ic()` inspects itself and
prints the call's filename and line number.

```python
from icecream import ic

def foo():
    ic()
    first()
    
    if expression:
        ic()
        second()
    else:
        ic()
        third()
```

Prints

```
ic| example.py:4
ic| example.py:11
```

Simple.


### Installation

Installing IceCream with pip is easy.

```
$ pip install icecream
```


### Other Flavors (Languages)

IceCream is currently just for Python, but IceCream should be enjoyed with every
language.

If you'd like a similar `ic()` method in your favorite language, please open a
pull request! IceCream's goal is to sweeten print debugging with a handy-dandy
`ic()` function to in every language.