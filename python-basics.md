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

``` python
string_4 = chr(number) # number is ASCII code
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

String Methods and functions
``` python
my_string.upper()		# uppercase
my_string.lower()		# lowercase
len(my_string)			# number of characters in a string
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

```python
a = True
b = True
c = False

a and b		# True
a or c		# True
not c		# True
```



### Lists

`list` - a collection of items with an order; `array` in many other languages
`[item_1, item_2, item_3]`

``` python
 list_1 = [item_1, item_2, item_3]

 list_2 = [2, 4, 6, 8, 0]

 list_3 = ['string 1', 'string 2', 'string 3', 'string 4']

 list_4 = [variable_1, 32.2, "string"]

 list_5 = list(range(5))

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
my_list.clear()						# removes all elements from a list
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

#### List Comprehensions
``` python
[transformation(element) for element in my_list]
```
Result is always a list

Examples
``` python
my_list = [1, 2, 3, 4, 5]
new_list = [x**2 for x in my_list]
```

List Comprehension with conditional logic
``` python
nums = list(range(20))

odds_squared = [num**2 for num in nums if num % 2 == 1]

new_list = [num*2 if num % 2 == 0 else num/2 fir num in nums]
```

``` python
full_text = "I am surprised that this works!"

''.join(char for char in full_text if char ot in "aeiou")
```

#### Nested Lists
```python
nested_list = [[11, 12, 13], [21, 22, 23], [31, 32, 33]]

element_2_3 = nested_list[1][2]
```
slicing works only for most outer list
looping requires nested looping

Nested List Comprehension
``` python
[[transformation(element) for element in inner_list] for inner_list in outer_list]
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


### Dictionaries
Data structure consisting of key value pairs
- keys - describe data
- values - represent data

``` python
my_dictionary = {
	key_1: value_1,
	key_2: value_2,
	key_3: value_3,
	key_4: value_4
}
```
keys are almost always strings of numbers
values can be any data structure

``` python
my_dictionary = dict(
	key_1 = value_1,	# key_1 is the actual value, no variable name
	key_2 = value_2		# key_2 is the actual value, no variable name
)
```

``` python
list_1 = ["CA", "NJ", "RI"]
list_2 = ["California", "New Jersey", "Rhode Island"]
 
my_dictionary = dict(zip(list_1,list_2))  
```

Accessing values
``` python
my_dict[my_key]
```

Adding new data
``` python
my_dict[my_key] = value_1
```

#### Functions and methods
``` python
my_dictionary.values()
my_dictionary.keys()
my_dictionary.items()

element in my_disctionary		# checks if element is in keys
element in my_disctionary.keys()		# checks if element is in keys
element in my_disctionary.values()		# checks if element is in values

my_dictionary.clear()		# clears all keys and values in a dictionary
my_dictionary.copy()		# makes a copy of a dictionary, can be assigned to new variable
my_dictionary.pop(key_1)		# removes entry corresponding to key_1, returns the value
my_dictionary.popitem()		# removes a random entry from a dictionary
my_dictionary.update(dictionary_2)		# update a dictionary with another dictionary


new_dict = {}.fromkeys(["key_1", "key_2", "key_3"], "default_value")
# or
new_dict = dict.fromkeys(["key_1", "key_2", "key_3"], "default_value")

my_dictionary.get("key_value")		# a safer way of retrieving data form a dictionary

len(my_dictionary)		# number of keys
```

#### Looping over dictionaries
``` python
for v in my_dictionary.values():
	print(v)
```

``` python
for k in my_dictionary.keys():
	print(k)
```

``` python
for k, v in my_dictionary.items():
	print(k)
	print(v)
```

#### Dictionary comperhensions
``` python
{key: value for item in iteratable_object}
```

``` python
numbers = {'first': 1, 'second': 2, 'third': 3}
squared_numbers = {key: value ** 2 for key, value in numbers.items()}
```

``` python
numbers = [1, 2, 3, 4]
squared_numbers_2 = {num: num ** 2 for num in numbers}
```

``` python
string_1 = 'ABCD'
string_2 = '1234'
my_dict = {string_1[i]: string_2[i] for i in range(len(string_1))}
```

``` python
numbers_2 = list(range(12))
even_odd = {num:('even' if num % 2 == 0 else 'odd') for num in numbers_2}
```


### Tuples
Ordered collection or grouping of items. 
Tuples are immutable, can't be changed
Tuples are faster than lists
Tuples be keys in a dictionary (lists can't)

``` python
tuple_1 = (item_1, item_2, item_3)

tuple_2 = (2, 4, 6, 8, 0)

tuple_3 = ('string 1', 'string 2', 'string 3', 'string 4')

tuple_4 = (variable_1, 32.2, "string")

tuple_5 = tuple(item_1, item_2, item_3)
```

``` python
item in my_tuple	# checking if item is in tuple
len(my_tuple)		# returns number of elements

my_tuple.count(my_item)		# returns the number of occurences of my_item
my_tuple.index(my_item)		# returns the first index number of my_item
```

``` python
my_tuple = (1, 2, 3, 4, 5, 6, 7, 8, 9, 10)

for num in my_tuple:
	print(num)
```

``` python
my_tuple = (1, 2, 3, 4, 5, 6, 7, 8, 9, 10)
i = 11

while i >= 0:
	print(my_tuple[i])
	i -= 1
```

#### Accessing Values in a Tuple
``` python
element = my_tuple[index]					# indexing starts at 0

element_1 = my_tuple[0]
element_last = my_tuple[-1]

element_6_to_10 = my_tuple[5:10]
element_from_4 = my_tuple[3:]
element_to_9 = my_tuple[:9]

element_6_to_10_step2 = my_tuple[5:10:2]
element_from_4_step2 = my_tuple[3::2]
```




### Sets
Sets are like formal mathematical sets:
- Collection of data that has no duplicate values, every item is unique
- Sets don't have any order

``` python
set_1 = {item_1, item_2, item_3}

set_2 = set({item_1, item_2, item_3})

set_3 = (variable_1, 32.2, "string")

set_4 = {2, 4, 6, 8, 8} 	# set will remove duplicated values
```

``` python
item in my_set		# checking if item is in my_set
len(my_set)			# returns number of elements

my_set.add(my_item)		# adds an item to a set
my_set.remove(my_item)		# removes an item from a set, returns an error is my_item is not in a set
my_set.discard(my_item)		# removes an item from a set
my_set.copy()		# makes a copy of a set, can be assigned to a new variable
my_set.clear()		# removes all items from a set

set_1 | set_2		# union of sets (or)
set_1 & set_2		# intersection of sets (and)
set_1 - set_2		# symmetric difference (set_1 to set_2)
```

``` python
my_set = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10}

for num in my_set:
	print(num)
```

#### Set comperhensions
``` python
my_set = {transformation for item in iteratable_object}
```

``` python
my_set = {x**2, for x in range(10)}
```



### Functions

Function - a process for executing a task

``` python
def my_function(arg_1, arg_2):
	result = (arg_1 + arg_2)**2
	return result

my_function(a, b)
# or
print(my_function(a, b))
```

``` python
def function_without_args():
	return "Hello world!"
```

```python
def function_with_default_arg(arg_1, arg_2 = 0):
	return (arg_1 + arg_2)**2
```

```python
def printing_function():
	print("That's a result of a function")
```

`return` - keyword in function that defines what the output of a function is. Tuples can be returned as well as single objects

- parameter - a variable in a method (or function) definition
- argument - passed into method's (function's) parameter

```python
def add(a, b):
    return a+b

def subtract(a, b):
    return a-b

def math(a, b, fun):
    return fun(a, b)
```



Keyword arguments

```python
def my_function(a, b):
	return (a + b)*(a - b)

my_function(b = 3, a = 1) # it will work
```



documenting functions

```python
def my_function(a):
    """This is a text explaining what this function does"""
    return a**3

my_function.__doc__ # returns the docstring
```



#### Scope

- variables created inside functions are available only in those functions
- global scope - defined outside any function or object global variables shouldn't be used inside functions

```python
total = 0

def increment():
    global total
    total += 1
    return total
```



#### *args

*args allows to put unspecified number of arguments to a function

```python
def my_function(*args):		# any name as long as starts with *
    print(args) 			# args is a tuple
```

```python
def my_sum(*nums):
	total = 0
    for i in nums:
        total += i
    return total
```

```python
def my_fun_2(arg_1, *args):
    my_list = []
    for i in args:
        my_list.append(arg_1 + i)
    return my_list
```



tuple / list unpacking

```python
def my_sum(*args):
	total = 0
    for i in args:
        total += i
    return total

nums_1 = [1, 2, 3, 4, 5]
my_sum(*nums_1)

nums_2 = (1, 2, 3, 4, 5)
my_sum(*nums_2)
```



#### **kwargs

**kwargs allows to put unspecified number of dictionary arguments to a function

```python
def my_fun_1(**kwargs):
	print(kwargs)
```

```python
def my_fun_2(**kwargs):
	print(kwargs.keys())
```



dictionary unpacking

```python
def my_fun_3(**kwargs):
	for name, number in kwargs.items():
		print(f"{name} is numeric {number}")

nums = {"one":1, "two":2, "three":3}
my_fun_3(**nums)
```

```python
def equation(n_1, n_2, n_3):
    return (n_1 + n_2)**n_3

data = dict(a=2, b=4, c=3)
equation(**data)
```



#### Parameter ordering

1. parameters
2. *args
3. default parameters
4. **kwargs



#### Lambdas

lambdas are single line functions that have no name

```python
lambda param: param * 3
```

```python
add = lambda a, b: a + b

add(2, 4)

print(add.__name__)			# <lambda> 
```

most common use-case: then a function has another function as a parameter



#### Some built in functions

`map` - a standard function that accepts at least two arguments: a function and an iterable object. It runs the function on each element in the iterable object and returns a map object. Often uses `lambda` as the function parameter

```python
my_map = map(my_function, my_object)
```

```python
def my_function(a):
    return (a / 2)**2
my_nums = [1, 2, 3, 4, 5, 6, 7, 8, 9]

my_map_1 = map(my_function, my_nums)
```

```python
my_nums = [1, 2, 3, 4, 5, 6, 7, 8, 9]

my_map_2 = map(lambda x: (x + 2)**3, my_nums)
```



`filter` - a standard function that allows to filter values out of an iterable object based on a scecific expression / condition (a function with boolean result)

```python
my_filter = filter(my_function, my_object)
```

```python
my_nums = [1, 2, 3, 4, 5, 6, 7, 8, 9]

my_filter = filter(lambda x: x % 2 == 0, my_nums)
```



`any` - function that takes an iterable object as input and returns `True` if at least one element in that object is "truthy"



`all` - function that takes an iterable object as input and returns `True` if all elements in that object are "truthy"



`sorted` - function that returns a new sorted list from an iterable object. Doesn't change the original object

```python
nums = [2, 5, 1, 7, 3, 4, 0, 6]
sorted_nums = sorted(nums)

descending_sorted = sorted(nums, reverse = True)
```

```python
my_users = [
	{"name":"Adam", "number":4},
    {"name":"Celine", "number":3},
    {"name":"Donald", "number":2},
    {"name":"Burt", "number":1},
]

sorted_users = sorted(my_users, key = lambda user: user['name'])
```



`min` and `max` - returns the smallest (largest) element in an iterable object or 2+ objects provided as an agument

```python
names = ['Adam', 'Tom', 'Daniel', 'Greg', 'Mike']

longest_name = max(names, key = lambda n: len(n))
```

```python
my_users = [
	{"name":"Adam", "number":4},
    {"name":"Celine", "number":3},
    {"name":"Donald", "number":2},
    {"name":"Burt", "number":1},
]

smallest_user = min(my_users, key = lambda user: user['number'])
```



`reversed` - returns a reversed iterable object



`len` - returns a length (number of items) of an object. uses a `__len__` method of that object



 

#### Generator expressions

list comprehensions that are not lists. temporary objects that are usually passed to a function, not for storage. 

```python
nums = [1, 2, 3, 4, 5, 6] 

my_list_comp = [n**2 for n in nums]
my_genexpr = (n**2 for n in nums)
```















___

  


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

    

    

    ## Importing

``` python
import module
from module import element
from module import \*
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