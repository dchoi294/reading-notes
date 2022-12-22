# Class 4 Reading Note

### Classes and Objects

Objects are an encapsulation of variables and functions into a single entity. Objects get their variables and functions from classes. Classes are essentially a template to create your objects.  
You can create multiple different objects that are of the same class, but each object contains independent copies of the variables defined in the class.  
To access a function inside of an object you use notation similar to accessing a variable.  
The __ init __() function, is a special function that is called when the class is being initiated. It's used for assigning values in a class.  

### Thinking Recursively

A recursive function is a function defined in terms of itself via self-referential expressions.  
A data structure is recursive if it can be deﬁned in terms of a smaller version of itself. A list is an example of a recursive data structure.

### Pytest Fixtures and Coverage

In pytest, you define fixtures using a combination of the pytest.fixture decorator, along with a function definition.  
in order to avoid the newline character from being placed at the start of the line, you remove it from the string before reversing and then add a '\n' in each returned string.  
fixtures are used differently from global variables.  
Coverage is a tool for measuring code coverage of Python programs. It monitors your program, noting which parts of the code have been executed, then analyzes the source to identify code that could have been executed but was not. Coverage measurement is typically used to gauge the effectiveness of tests.

Reference [Classes and Objects](https://www.learnpython.org/en/Classes_and_Objects)  
Reference [Thinking Recursively](https://realpython.com/python-thinking-recursively/)  
Reference [Pytest Fixtures and Coverage](https://www.linuxjournal.com/content/python-testing-pytest-fixtures-and-coverage)

[Back to Home](../../README.md)
