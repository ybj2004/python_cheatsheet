## Index

---
## Basics
### Arithmetics
Operator | Operation | Example | Evaluates to
--- | --- | --- | --- 
``**`` | Exponent | ``2 ** 3`` | 8
``%`` | Modulus/Remainder | ``22 % 8`` | 6
``//`` | Integer division | ``22 // 8`` | 2
``/`` | Division | ``22 / 8`` | 2.75
``*`` | Multiplication | ``2 * 5`` | 10
``-`` | Substraction | ``5 - 2 `` | 3
``+`` | Addition | ``5 + 2`` | 7

### Variables
Valid name | Invalid name | Rule
--- | --- | ---
``balance`` | ``current-balance`` | __no hyphen allowed__
``currentBalance`` | ``current balance`` | __no space allowed__
``current_balance`` | ``4current_balance`` | __can't begin with number__
``_balance`` | ``4`` | __can't begin with number__
``BALANCE`` | ``$balance`` | __no special characters__
``current_balance_4`` | ``'current_balance'``| __no special characters__

#### Assignments
```python
# Multiple assignments
>>> a, b = 0, 1
>>> a
0
>>> b
1
```
## Strings ([->](https://docs.python.org/3/tutorial/introduction.html#strings "Python 3.6 - Strings"))
### Printing
```python
>>> 'A string'
'A string'
>>> "A 2nd string"
'A 2nd string'
>>> print("Print a string")
Print a string

# Multi line '\' prevents auto-add \n
print("""\
Multi line

strings.
""")

# Printing with arguments
>>> i = 42
>>> print("The value of i is", i)
The value of i is 42
```

### Concatination
```python
# Repetition + concat
>>> 3 * "ha" + "yes"
'hahahayes'

# Auto concat of string literals, need to be next to each other!
>>> 'test' 'case'
'testcase'

# Concat with variable
>>> prefix = "py"
>>> prefix + 'thon'
'python'

# Breaking down long strings
>>> string = ('Hello' 'World')
>>> string
'HelloWorld'

# Treat a string like a list/array. Note that there are no chars like in C, Just a string with size 1
>>> string
'HelloWorld'
>>> string = "Hello World"
>>> string[0]
'H'
>>> string[6]
'W'
>>> string[-1] # last character
'd'
>>> string [-2] # second-last character
'l'
```

### Slicing strings
Slicing will obtain a substring. __The start is always included, the end is always excluded__: ``s[:i] + s[i:] == s``. Default indices are 0 and length.
```python
>>> string[0:2] # Characters from pos 0 (incl) to pos 2 (excl)
'He'
>>> string[2:5] # Characters from pos 2 (incl) to pos 5 (excl)
'llo'
>>> string[:2] # Pos 0 - Pos 2
'He'
>>> string[2:] # Pos 2 - End
'llo World'
>>> string[:2] + string[2:]
'Hello World'
```
It's a good way to think of indices as marking the __borders__ of a position:
```python
 +---+---+---+---+---+---+
 | P | y | t | h | o | n |
 +---+---+---+---+---+---+
 0   1   2   3   4   5   6
-6  -5  -4  -3  -2  -1
```

### Behaviour
Strings are __immutable__.
```python
>>> string
'Hello World'

# Can't change a string
>>> string[0] = "c"
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'str' object does not support item assignment

# Need to create a new string!
>>> "Bye" + string[5:]
'Bye World'

# Returns length
>>> len(string)
11
```
For built-in string methods see [official doc](https://docs.python.org/3/library/stdtypes.html#string-methods "Python 3.6 - String Methods").

## Lists ([->](https://docs.python.org/3/tutorial/introduction.html#lists "Python 3.6 - Lists"))
A list is an unordered, comma-seperated, [sequence](https://docs.python.org/3/glossary.html#term-sequence "Python 3.6 - Gloassary") of values of either the same of different types. The first index is zero. __Lists are mutable__.
```python
# Standard list
>>> numbers = [1, 2, 3, 4, 5, 6]
>>> numbers
[1, 2, 3, 4, 5, 6]

# Lists can be nested too
>>> letters = ['a', 'b', 'c']
>>> list = [numbers, letters]
>>> list
[[1, 2, 3, 4, 5, 6], ['a', 'b', 'c']]
>>> list [0][2]
3
>>> list [1][2]
'c'
```

### Manipulation
All manipulation returns a new list.
```python
>>> numbers
[1, 2, 3, 4, 5, 6]

# Return value at index
>>> numbers[0]
1
>>> numbers[-2]
5

# Slicing
>>> numbers[3:]
[4, 5, 6]

>>> numbers [:-2]
[1, 2, 3, 4]

# Copy
>>> numbers[:]
[1, 2, 3, 4, 5, 6]

# Concat
>>> numbers + [1, 2, 4, 8]
[1, 2, 3, 4, 5, 6, 1, 2, 4, 8]

# Replace
>>> numbers[3] = 42
>>> numbers
[1, 2, 3, 42, 5, 6]

# Remove
>>> numbers[2:4] = []
>>> numbers
[1, 2, 5, 6]

>>> numbers[:] = []
>>> numbers
[]

>>> numbers[2:4] = [42, 23]
>>> numbers
[1, 2, 42, 23, 5, 6]

# Methods
>>> len(numbers)
6

>>> numbers.append(5 ** 2)
>>> numbers
[1, 2, 3, 42, 5, 6, 25]
```
For built-in list methods see [official doc](https://docs.python.org/3/tutorial/datastructures.html#more-on-lists "Python 3.6 - More on Lists").

## Sources
* [docs.python.org](https://docs.python.org/3/)
* [automatetheboringstuff.com](https://automatetheboringstuff.com)