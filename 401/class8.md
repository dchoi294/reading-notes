# Class 8 Reading Note

## List Comprehensions

- List comprehension methods are an elegant way to create and manage lists.
- In Python, list comprehensions are a more compact way of creating lists.
- More flexible than for loops, list comprehension is usually faster than other methods.

Create a List with range()

```
# construct a basic list using range() and list comprehensions
# syntax
# [ expression for item in list ]
digits = [x for x in range(10)]

print(digits) 
```
```
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```


Create a List Using Loops and List Comprehension in Python

```
# create a list using a for loop
squares = []

for x in range(10):
    # raise x to the power of 2
    squares.append(x**2)

print(squares)
```
or
```
# create a list using list comprehension
squares = [x**2 for x in range(10)]

print(squares)
```
```
[0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```

Multiplying Parts of a List

```
# create a list with list comprehensions
multiples_of_three = [ x*3 for x in range(10) ]

print(multiples_of_three)
```
```
[0, 3, 6, 9, 12, 15, 18, 21, 24, 27]
```
or
```
even_numbers = [ x for x in range(1,20) if x % 2 == 0]
```
```
[2, 4, 6, 8, 10, 12, 14, 16, 18]
```

Show the first letter of each word using Python

```
# a list of the names of popular authors
authors = ["Ernest Hemingway","Langston Hughes","Frank Herbert","Toni Morrison",
    "Emily Dickson","Stephen King"]

# create an acronym from the first letter of the author's names
letters = [ name[0] for name in authors ]
print(letters)
```
```
['E', 'L', 'F', 'T', 'E', 'S']
```
or
```
# use list comprehension to print the letters in a string
letters = [ letter for letter in "20,000 Leagues Under The Sea"]

print(letters)
```
```
['2', '0', ',', '0', '0', '0', ' ', 'L', 'e', 'a', 'g', 'u', 'e', 's', ' ', 'U', 'n', 'd', 'e', 'r', ' ', 'T', 'h', 'e', ' ', 'S', 'e', 'a']
```

Lower/Upper case converter using Python

```
lower_case = [ letter.lower() for letter in ['A','B','C'] ]
upper_case = [ letter.upper() for letter in ['a','b','c'] ]

print(lower_case, upper_case)
```
```
['a', 'b', 'c'] ['A', 'B', 'C']
```

Print numbers only from a given string

```
# user data entered as name and phone number
user_data = "Elvis Presley 987-654-3210"
phone_number = [ x for x in user_data if x.isdigit()]

print(phone_number)
```
```
['9', '8', '7', '6', '5', '4', '3', '2', '1', '0']
```

Parsing a file using list comprehension

```
# open the file in read-only mode
file = open("dreams.txt", 'r')
poem = [ line for line in file ]

for line in poem:
    print(line)
```
```
Hold fast to dreams

For if dreams die

Life is a broken-winged bird

That cannot fly.

-Langston Hughs
```

Using functions in list comprehensions

```
# list comprehension with functions
# create a function that returns a number doubled
def double(x):
    return x*2

nums = [double(x) for x in range(1,10)]
print(nums)
```
```
[2, 4, 6, 8, 10, 12, 14, 16, 18]
```
or
```
# add a filter so we only double even numbers
even_nums = [double(x) for x in range(1,10) if x%2 == 0]
print(even_nums)
```
```
[4, 8, 12, 16]
```
or
```
nums = [x+y for x in [1,2,3] for y in [10,20,30]]
print(nums)
```
```
[11, 21, 31, 12, 22, 32, 13, 23, 33]
```

Reference [List Comprehensions](https://www.pythonforbeginners.com/basics/list-comprehensions-in-python)

[Back to Home](../../README.md)
