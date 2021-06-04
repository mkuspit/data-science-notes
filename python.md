# Python Basics
## Absolute basics

### Data types
Python supports 
- numbers
- strings
- sets
- lists
- tuples
- dictionaries

 Variables store information that can be used in your program such as to hold user inputs, local states of your program etc.
 Variables are also known as names in Python.
 Variable names must:
- begin with a letter or underscore (`_`)
- contain no special characters
- contain no Python keywords

Data types:
``` python
1234				# integer
3.14				# float
"Some text"			# string
'More text' 		# string
'''Also text''' 	# string
'''Much longer
text in miltiple 
lines''' 			# string
```

  
``` python
type(my\_variable)	# prints type of a variable

int(my\_var) 		# converts to an integer
float(my\_var)		# converts to a float
str((my\_var)		# converts to a string
```
  

``` python
print(a)
print(1000)
print("Some random text")
```

  

### Operators
``` python
a + b 		# addition
a - b		# subtracion
a * b		# multiplication
a / b 		# division
a // b 		# floor division
a % b		# remainder
a ** b 		# exponentiation
```

Order of operations (typical math):
1. Parentheses
2. Exponentiation
3. Multiplication and division
4. Addition and subtraction

### Functions

``` python
def function(arg_1, arg_2):
	result = (arg_1 + arg_2)**2
	return result

function(a, b)
# or
print(function(a, b))
```

  

``` python
variable_1 = "Some text"
variable_2 = "and some more text"
variable_3 = 12
variable_4 = 2

variable_1 + variable_2

variable_1 + " " + variable_2

variable_3 + variable_4

variable_1 + " " + str(variable_4)
```

  

Keywords
- `and`
- `as`
- `assert`
- `break`
- `class`
- `continue`
- `def`
- `del`
- `elif`
- `else`
- `except`
- `exec`
- `finally`
- `for`
- `from`
- `global`
- `if`
- `import`
- `in`
- `is`
- `lambda`
- `nonlocal`
- `not`
- `or`
- `pass`
- `raise`
- `return`
- `try`
- `while`
- `with`
- `yield`
- `True`
- `False`
- `None`

``` python
len(my\_string) 		# number of characters in a string
input("Some text: ")	# collects data from user. Result is string
```

Updating variables
``` python
x = x + y
# or
x += y

# works for -, *, / as well
```


Importing
``` python
import module

from module import element

 from module import \*
```

  

## Repetition

``` python
for _ in range(5):
	print("Some text")
```

  
## Errors
1. Syntax error - statements aren't well formed
2. Runtime error - illegal operation (dividing by 0)
3. Semantic error - programmer’s error to create a proper statement

  
### Python escapes

``` python
\\ 				# Backslash
\' 				# Single-quote
\" 				# Double-quote
\a 				# ASCII bel
\b 				# ASCII backspace
\f 				# ASCII formfeed
\n 				# ASCII linefeed
{name} 			# Character named name in Unicode database
\r 				# Carriage return
\t 				# Horizintal tab
\uxxxx 			# Character with 16-bit hex value xxxx
\Uxxxxxxxx 		# Character with 32-bit hex value xxxxxxxx
\v 				# ASCII vertical tab
\xxx 			# Character with octal value xxx
\hh 			# Character with hex value hh
```


```python
''.join('string1', 'string2', 'string3')
# result is 'string1string2string3'
```
