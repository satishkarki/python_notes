# Python Primer

## Function
```python
print("Bye World!")
```
A function may have an effect or result. There is also a thrid very important function component- the **argument(s)**. 
* Functions strongly demands a pair of parentheses
* If you want to deliver one or more arguments to a function, you place them inside the parentheses. If you're going to use a function which doesn't take any argument, you still have to have the parentheses.
* String as the print() function's argument- The string is delimited with quotes- **"Bye World!"**

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

# Under the hood
print(*objects, sep=' ', end='\n', file=sys.stdout, flush=False)
```
* sep="---": Keyword argument that changes the separator between objects from a space to ---.
* end="!!!": Keyword argument that ends the output with !!! instead of a newline.