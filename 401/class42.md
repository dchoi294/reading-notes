# Class 42 Reading Notes

## Python Generators 101 – The Basics

- Generator functions are syntactic sugar for writing objects that support the iterator protocol. Generators abstract away much of the boilerplate code needed when writing class-based iterators.

- The yield statement allows you to temporarily suspend execution of a generator function and to pass back values from it.

- Generators start raising StopIteration exceptions after control flow leaves the generator function by any means other than a yield statement.

## Dunder Methods

special methods are a set of predefined methods you can use to enrich your classes. They are easy to recognize because they start and end with double underscores, for example `__init__` or `__str__`.

To construct account objects from the Account class I need a constructor which in Python is the `__init__` dunder.

```
class Account:
    """A simple account class"""

    def __init__(self, owner, amount=0):
        """
        This is the constructor that lets us create
        objects from this class
        """
        self.owner = owner
        self.amount = amount
        self._transactions = []
```

`__repr__`: The “official” string representation of an object. This is how you would make an object of the class. The goal of `__repr__` is to be unambiguous.

`__str__`: The “informal” or nicely printable string representation of an object. This is for the enduser.

```
class Account:
    # ... (see above)

    def __repr__(self):
        return 'Account({!r}, {!r})'.format(self.owner, self.amount)

    def __str__(self):
        return 'Account of {} with starting amount: {}'.format(
            self.owner, self.amount)
```

## Python Iterators

- Iterators provide a sequence interface to Python objects that’s memory efficient and considered Pythonic. Behold the beauty of the for-in loop.

- To support iteration an object needs to implement the iterator protocol by providing the `__iter__` and `__next__` dunder methods.

- Class-based iterators are only one way to write iterable objects in Python. Also consider generators and generator expressions.

Reference [Dunder Methods](https://dbader.org/blog/python-dunder-methods)  
Reference [Iterators](https://dbader.org/blog/python-iterators)  
Reference [Generators](https://dbader.org/blog/python-generators)  

## Things I want to know more about

[Back to Home](../../README.md)
