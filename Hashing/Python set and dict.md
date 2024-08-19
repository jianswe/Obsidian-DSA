# set
**Unordered**: The elements have no defined order.  
## Common Methods and Properties 
* **`set.remove(element)`**: Removes an element from the set. Raises a `KeyError` if the element is not found. 
* **`set.discard(element)`**: Removes an element if it is a member. If not, it does nothing. 
* **`set.pop()`**: Removes and returns an arbitrary set element. Raises a `KeyError` if the set is empty. 
* **`set.union(*others)`**: Returns a new set with elements from the set and all others. 
* **`set.intersection(*others)`**: Returns a new set with elements common to the set and all others.
* **`set.difference(*others)`**: Returns a new set with elements in the set that are not in the others.
* **`set.symmetric_difference(other)`**: Returns a new set with elements in either the set or other but not in both.
* **`set.issubset(other)`**: Checks whether another set contains this set.
* **`set.issuperset(other)`**: Checks whether this set contains another set.
* **`set.isdisjoint(other)`**: Returns True if two sets have a null intersection.
```python
my_set = {1, 2, 3, 4, 4}
print(my_set)  # Output: {1, 2, 3, 4}

my_set.add(5)
print(my_set)  # Output: {1, 2, 3, 4, 5}

my_set.discard(3)
print(my_set)  # Output: {1, 2, 4, 5}

my_set.remove(2)
print(my_set)  # Output: {1, 4, 5}

# Using set operations
another_set = {4, 5, 6, 7}
print(my_set.union(another_set))  # Output: {1, 4, 5, 6, 7}
print(my_set.intersection(another_set))  # Output: {4, 5}
print(my_set.difference(another_set))  # Output: {1}
```
# dict
A **dict** (short for "dictionary") is a collection of key-value pairs. Each key must be unique and immutable (such as strings, numbers, or tuples), while values can be any type. 
**Ordered**: As of Python 3.7, dictionaries maintain insertion order. 
* **`dict[key]`**: Accesses the value associated with the key. Raises a `KeyError` if the key is not found.
* **`dict[key] = value`**: Adds or updates the key-value pair.
* **`dict.get(key, default=None)`**: Returns the value associated with the key. If the key is not found, returns `default`.
* **`dict.pop(key, default=None)`**: Removes the key and returns its value. If the key is not found, returns `default`.
* **`dict.popitem()`**: Removes and returns the last inserted key-value pair.
* **`dict.keys()`**: Returns a view object displaying a list of all the keys.
- **`dict.values()`**: Returns a view object displaying a list of all the values.
- **`dict.items()`**: Returns a view object displaying a list of all key-value pairs.
- **`dict.clear()`**: Removes all key-value pairs from the dictionary.
* **`dict.update([other])`**: Updates the dictionary with the key-value pairs from `other`, overwriting existing keys.
```python
my_dict = {'name': 'Jian', 'age': 30}

# Accessing values
print(my_dict['name'])  # Output: Jian

# Adding or updating a key-value pair
my_dict['age'] = 31
print(my_dict)  # Output: {'name': 'Jian', 'age': 31}

# Using get() to access values
print(my_dict.get('name'))  # Output: Jian
print(my_dict.get('height', 'Not found'))  # Output: Not found

# Removing key-value pairs
my_dict.pop('age')
print(my_dict)  # Output: {'name': 'Jian'}

# Adding multiple key-value pairs
my_dict.update({'height': 175, 'weight': 70})
print(my_dict)  # Output: {'name': 'Jian', 'height': 175, 'weight': 70}

# Accessing keys, values, and items
print(my_dict.keys())  # Output: dict_keys(['name', 'height', 'weight'])
print(my_dict.values())  # Output: dict_values(['Jian', 175, 70])
print(my_dict.items())  # Output: dict_items([('name', 'Jian'), ('height', 175), ('weight', 70)])
```