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
```

``` python
print(3.14)
```

``` python
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
```

``` python
string_2 = 'String in single quotes'
```

``` python
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
''.join(['pam', 'param', 'pampam'])
# result is 'pamparampampam'

'_'.join(['pam', 'param', 'pampam'])
# result is 'pam_param_pampam'
```

#### Strings and Indices
Each character in a string has an index number
Numbers start at `0`
``` python
"Michal"[1] 		# = "i"
"Michal"[-2] 		# = "a"
```

#### Formatting Strings
``` python
a_number = 10
formatted_string = f"I am adding number {a_number} to a string."
```

String Methods
``` python
my_string.upper()		# uppercase
my_string.lower()		# lowercase
```

#### Getting User Input
``` python
my_variable = input("Write something: ")
```
The result is string



### Boolean Logic

#### Conditional Statements
``` python
if a > 10:					# there has to be exactly one if
	print("a is big")
elif a >= 0:				# elif is optional, there can be many of them
	print("a is small")
else:						# else is optional, there can be only one
	print("a is negative")
```

Truthiness - empty objects (including strings), `None`, `0` return `False` in conditinal statements

#### Operators
- `==` - is equal to (checking values)
- `is` - is equal to (checking if it's stored in the same place in memory), used for comparing to `None`	
- `!=` - is not equal to
- `>` - greater than 
- `<` - smaller than
- `>=` - greater or equal to 
- `<=` - smaller or equal to
- Logical operators: `and`, `or`, `not`

``` python
a = 1
a == 1			# True
a is 1			# True

b = [1, 2, 3]
c = [1, 2, 3]
b == c			# True
b is c			# False

d = b
b is d			# True
```

### Lists
`list` - a collection of items with an order; `array` in many other languages
`[item_1, item_2, item_3]`

``` python
 list_1 = [item_1, item_2, item_3]
```

``` python
 list_2 = [2, 4, 6, 8, 0]
```

``` python
 list_3 = ['string 1', 'string 2', 'string 3', 'string 4']
```

``` python
 list_4 = [variable_1, 32.2, "string"]
```

``` python
 list_5 = list(range(5))
```

``` python
 empty_list = []
```

#### Functions and methods
``` python
 element in my_list										# checks if element is in my_list
 
 my_list[index] = new_value								# updating values
 my_list[n1], my_list[n2] = my_list[n2], my_list[n1]	# swaping elements

 len(my_list)											# number of elements in a list
 ```
 
 ``` python
 my_list.append(new_element)		# adds an item to the end of the list
 my_list.extend(new_list)			# adds new_list as elements to the end of the list
 my_list.insert(index, new_element)	# adds new_element at the index position
 ```
 
 ``` python
 my_list.clear()					# removes all elements from a list
 my_list.pop(i)						# removes element at index i from a list
 my_list.remove(x)					# removes the first value x in a list and remove it
```
`pop` returns the deleted item so that can be stored in a variable; if no `i` is given, it pops the last item in the list
`remove` doesn't return the value

``` python
my_list.index(x)					# returns first index where value x is stored
my_list.index(x, start)				# returns first index after start (inclusive) where value x is stored
my_list.index(x, start, end)		# returns first index between start and end where value x is stored

my_list.count(x)					# returns number of occurences of x in a list
my_list.reverse()					# reverse order of a list (in place)
my_list.sort()						# sort itms in a list (in place) in ascending order
```


#### Accessing Values in a List
``` python
my_list = list(range(1, 16))

element = my_list[index]					# indexing starts at 0

element_1 = my_list[0]
element_last = my_list[-1]

element_6_to_10 = my_list[5:10]
element_from_4 = my_list[3:]
element_to_9 = my_list[:9]

element_6_to_10_step2 = my_list[5:10:2]
element_from_4_step2 = my_list[3::2]
```




### Loops

#### `for` Loop
``` python
for letter in "Hello world!":
	print(letter)
```

``` python
for number in range(1, 12):
	print(number)
```

``` python
for item in [2, 8, 6, 12]:
	print(item)
```

#### `while` Loop
``` python
while boolean_expression:
	print("Hello!")
	# repeat until boolean_expression == False
```
This loop can go on forever; `ctrl+c` to exit

#### Breaking a Loop with `break`
``` python
while True:
	msg = input("Type something: ")
	if msg == "exit":
		break		# immediately exits loop 
```
Works with both `for` and `while` loops





#### Ranges
A range is a slice in the number line
``` python
range(5)
# 0, 1, 2, 3, 4
```

``` python
range(3, 7)
# 3, 4, 5, 6
```

``` python
range(1, 10, 2)
# 1, 3, 5, 7, 9
```

``` python
range(2, -3, -1)
# 2, 1, 0, -1, -2
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