# Python Basics
## Absolute basics

### Intro
Data types in Python
- numbers (integer, float, long, complex)
- strings
- sets
- lists
- tuples
- dictionaries
- booleans

``` python
type(my_variable)	# prints type of a variable

int(my_var) 		# converts to an integer
float(my_var)		# converts to a float
str((my_var)		# converts to a string
```

`None` - a special value in Python representing "nothingness"

#### Variables
Variables store information that can be used in your program such as to hold user inputs, local states of your program etc.
Variables are also known as names in Python.
Variable names must:
- begin with a letter or underscore (`_`)
- contain no special characters (only letters, numbers and underscore)
- contain no Python keywords

``` python
my_variable_1 = 123
my_variable_2 = "string"
```

Updating variables
``` python
x = x + 1
# or
x += 1

# works for -, *, / as well
```

Python is a dynamic typing language, which means that you don't have to set data type while creating a variable and easily change it afterwards

#### Comments
``` python
# comment, will not execute
```


### Printing
``` python
print("Some text")

print(3.14)

my_text = "Some other text"
print(my_text)
```


### Math and Numbers
``` python
1234				# integer
3.14				# float
```

#### Operators
``` python
a + b 		# addition
a - b		# subtracion
a * b		# multiplication
a / b 		# division
a // b 		# integer division (floor division)
a % b		# remainder (modulo)
a ** b 		# exponentiation
```
Order of operations (typical math):
1. Parentheses
2. Exponentiation
3. Multiplication and division
4. Addition and subtraction


### Strings
``` python
string_1 = "String in double quotes"

string_2 = 'String in single quotes'

string_3 = "String with 'quotation' inside of it"
```

#### Python escape sequences
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

#### Concatenation
``` python
variable_1 = "Some text"
variable_2 = "and some more text"

variable_1 + " " + variable_2
```

Concatenation works only with strings
``` python
string_variable = "Some text that should be followed by a number \n"
number_variable = 123

variable_1 + str(number_variable)
```

Concatenating using `.join` method
``` python
'any string in here or empty space'.join('pam', 'param', 'pampam')
# result is 'pamparampampam'
```

#### Formatting strings
``` python
a_number = 10
formatted_string = f"I am adding number {a_number} to a string."
```


















### Functions

``` python
def function(arg_1, arg_2):
	result = (arg_1 + arg_2)**2
	return result

function(a, b)
# or
print(function(a, b))
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
len(my_string) 			# number of characters in a string
input("Some text: ")	# collects data from user. Result is string
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

  


## Virtual Environments
### venv Module
`pip3 list` - list all installed packages in base Python 3

`python3 -m venv environment_name` - creates an environment in current directory, uses same verion of Python as the installation
`source path/environment_name/bin/activate` - activates envoronment
`pip list` - lists all packages installed in current venv environment
`pip freeze` - lists all packages installed in current venv environment with version
`pip freeze > requirements.txt` - creates a requirements.txt file in current directory

### conda

### virtualenv