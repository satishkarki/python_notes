# Summary: Python Lists - Mutability and References

## Key Concept
In Python, lists are **mutable** objects, meaning you can change their contents (like elements or length) after creation without making a whole new list. This is super efficient but can surprise you with **references**: when you assign one list to another (e.g., `list_2 = list_1`), both variables point to the *same* object in memory. Modifying one affects the other—it's like two remotes controlling one TV!

- **Why it matters**: Saves memory (no duplicates), but watch for "side effects" in bigger code.
- **Check it**: Use `id(my_list)` to see the memory address—same ID means shared reference.
- **Immutable contrast**: Strings or ints don't do this (e.g., `a = "hi"; b = a; a = "bye"` leaves `b` as `"hi"`).

## Example: The Sneaky Shared List (Original Gotcha)
```python
list_1 = [1]      # Create a list
list_2 = list_1   # Shared reference, not a copy
list_1[0] = 2     # Modify list_1
print(list_2)     # Output: [2]  (list_2 changed too!)
print(id(list_1) == id(list_2))  # Output: True (same object)
```
# Python Guide: List Slicing (Quick Extract & Copy)

## Core Idea
Slicing `my_list[start:stop:step]` pulls a *new* shallow copy of a list chunk—original stays safe. Non-destructive magic for subsets, copies, or reverses.  
- **start**: Begin (default 0, inclusive).  
- **stop**: End (default len, exclusive).  
- **step**: Jump (default 1; -1 reverses).  
Shortcuts: `[:]` (full copy), `[2:]` (from 2), `[:-1]` (all but last), `[::-1]` (reverse). Negatives from end.  

*Watch*: Shallow means nested lists share inners—use `copy.deepcopy` for full split.

## Example: Copy & Chunk
```python
# Full copy (beats shared refs)
list_1 = [1]
list_2 = list_1[:]  # New: [1]
list_1[0] = 2
print(list_2)  # [1] (untouched!)

# Partial: Indices 1 to <3
my_list = [10, 8, 6, 4, 2]
chunk = my_list[1:3]  # [8, 6]
print(chunk)  # Original safe

# Fun: Reverse + step
cart = ['milk', 'eggs', 'bread']
print(cart[::-1])  # ['bread', 'eggs', 'milk']
print(cart[::2])   # ['milk', 'bread']