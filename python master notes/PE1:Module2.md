# Python Primer

## Function
A list of all [built-in Functions](https://docs.python.org/3.12/library/functions.html)
```python
print("Bye World!")
```
A function may have an effect or result. There is also a thrid very important function component- the **argument(s)**. 
* Functions strongly demands a pair of parentheses
* If you want to deliver one or more arguments to a function, you place them inside the parentheses. If you're going to use a function which doesn't take any argument, you still have to have the parentheses.
* String as the print() function's argument- The string is delimited with quotes- **"Bye World!"** or **'Bye World!'**

```python
print("Hello\nWorld") # New Line
print ("\") # It will throw error
print("\\") # It will print \
```
* The backslash( \ ) when used inside a string is called the escape character- kind of like an nnouncement
* The letter **n** placed after the backslash comes from the word newline

```python
print("Max Verstappen", "Carlos Sainz", "Lewis Hamilton")
```
* a print() function invoked with more than one argument outputs them all on one line
* the print() function puts a space between the outputted arguments on its own initiative.





``` Python
print("Hello", "World", sep="---", end="!!!")
print("Next")
#Output
Hello---World!!!Next

print(sep="&", "Max", "Verstappen")
#Output
SyntaxError: positional argument follows keyword argument

# Under the hood
print(*objects, sep=' ', end='\n', file=sys.stdout, flush=False)
```
Keyword arguments are the ones whose meaning is not dictated by their location, but by a special word (keyword) used to identify them.
* sep="---": Keyword argument that changes the separator between objects from a space to ---.
* end="!!!": Keyword argument that ends the output with !!! instead of a newline.
* `Remember`: Keyword arguments should be passed after any required positional arguments.

## Python Literals
A literal is data whose values are determined by the literal itself.

The characteristic of the numeric value which determines its kind, range, and application, is called the type.

### Integers

* can be represented as `111111111` or `111_111_111`
* Python 3.6 has introduced underscores in numeric literals, allowing for the placement of single underscores between digits and after base specifiers for improved readability. This feature is not available in older versions of Python.
* Negative Number can be representes as `-111111111` or `-111_111_111`
### Octal and hexadecimal numbers
* If an integer number is preceded by an `0O` or `0o` prefix (zero-o), it will be treated as an octal value. This means that the number must contain digits taken from the [0..7] range only.
* Hexadecimal number should be preceded by the prefix `0x` or `0X` (zero-X)

### Floats
```python
.4 # 0.4
4. # 4.0
3E8 # 3*10^8
6.62607E-34 # 6.62607*10^-34

print(0.00000000000000000000001)
# output
1e-22 #
```
* The letter E (you can also use the lower-case letter e ‒ it comes from the word exponent) is a concise record of the phrase times ten to the power of.
* the exponent (the value after the E) has to be an integer
* the base (the value in front of the E) may be either an integer or a float
* Python always chooses the more economical form of the number's presentation

### Strings
```python
print("I like \"F1\"")
print('I like "F1"')
```
Strings need quotes the way floats need points.

#### Boolean values
```python
print(True > False)
print(True < False)
# Output
True
False

print(True + True)
# Output
2
```
* Python in a binary reptile, True=1 and False=0
* True and False are case-sensitive- insecure about lowercase

### None
```python
a = None
b = None
print(a is b)  # Output: True (same object)

print(type(None))  # Output: <class 'NoneType'>

if not None:
    print("None is falsy")  # Output: None is falsy
print(None == False)  # Output: False (None is not False)

value = None
if some_condition:
    value = 42
print(value)  # Output: None (if some_condition is False)
```
None is commonly used to indicate that a variable or expression has no meaningful value, is undefined, or has not been assigned yet.




