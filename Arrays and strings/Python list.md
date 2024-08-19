In Python, lists are used to represent arrays, and they are also dynamic and can hold different types of elements.
# Init
## 1D Array
```python 
# Initialize a list with a specific size (filled with None) 
arr1 = [None] * 5
# Initialize a list with specific elements using a loop (e.g., a list of zeros) 
arr2 = [0 for _ in range(5)]
```
## 2D Array
Using List Comprehension 
```python
array_2d = [[0 for _ in range(cols)] for _ in range(rows)]
```
# Methods
Python lists have a variety of methods to manipulate them:
```python
arr = [1, 2, 3, 4, 5]

# Adding elements 
arr.append(6) # Adds to the end: [1, 2, 3, 4, 5, 6] 
arr.insert(0, 0) # Adds to the beginning: [0, 1, 2, 3, 4, 5, 6]

# Removing elements 
arr.pop() # Removes from the end: [0, 1, 2, 3, 4, 5] 
arr.pop(0) # Removes from the beginning: [1, 2, 3, 4, 5] 
arr.remove(3) # Removes the first occurrence of 3: [1, 2, 4, 5]

# Slicing 
sub_arr = arr[1:3] # [2, 4]

# Iterating 
for element in arr: 
	print(element) # Prints each element

# Mapping 
new_arr = list(map(lambda x: x * 2, arr)) # [2, 4, 8, 10]

# Filtering 
filtered_arr = list(filter(lambda x: x > 2, arr)) # [4, 5]

# Reducing 
from functools import reduce 
sum = reduce(lambda acc, x: acc + x, arr, 0) # 12

# Finding 
found = next((x for x in arr if x > 2), None) # 4
```