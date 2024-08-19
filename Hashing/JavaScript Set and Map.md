# Set
A **Set** can store any type of value, whether primitive or object references. 
**Order**: The values in a `Set` are ordered by insertion. 
## Common Methods and Properties
* **`set.delete(value)`**: Removes a value from the Set. Returns **`true`** if the value existed and was removed. 
```js
const mySet = new Set([1, 2, 3, 4, 4]);

console.log(mySet); // Set { 1, 2, 3, 4 }

mySet.add(5);
console.log(mySet); // Set { 1, 2, 3, 4, 5 }

console.log(mySet.has(3)); // true

mySet.delete(4);
console.log(mySet); // Set { 1, 2, 3, 5 }

mySet.clear();
console.log(mySet.size); // 0
```

## Implement Set Operations
JavaScript's `Set` does not natively include methods like `union`, `intersection`, or `difference`, which are common in other languages like Python. However, you can implement these operations using standard JavaScript functions.
### Union 
```js
function union(setA, setB) {
    return new Set([...setA, ...setB]);
}

const setA = new Set([1, 2, 3]);
const setB = new Set([3, 4, 5]);
const unionSet = union(setA, setB);
console.log(unionSet); // Output: Set { 1, 2, 3, 4, 5 }
```
### Intersection 
```js
function intersection(setA, setB) {
    return new Set([...setA].filter(element => setB.has(element)));
}

const intersectionSet = intersection(setA, setB);
console.log(intersectionSet); // Output: Set { 3 }
```
### Difference 
The difference of two sets (`setA` - `setB`) includes elements that are in `setA` but not in `setB`.
```js
function difference(setA, setB) {
    return new Set([...setA].filter(element => !setB.has(element)));
}

const differenceSet = difference(setA, setB);
console.log(differenceSet); // Output: Set { 1, 2 }
```
### Symmetric Difference

The symmetric difference of two sets includes elements that are in either `setA` or `setB`, but not in both.
```js
function symmetricDifference(setA, setB) {
    return new Set([...setA].filter(element => !setB.has(element))
                   .concat([...setB].filter(element => !setA.has(element))));
}

const symmetricDifferenceSet = symmetricDifference(setA, setB);
console.log(symmetricDifferenceSet); // Output: Set { 1, 2, 4, 5 }
```
# Map
A **Map** is a collection of key-value pairs where both keys and values can be of any type. 
**Ordered**: Maps remember the original insertion order of the keys. 
```js
const myMap = new Map();

myMap.set('name', 'Jian');
myMap.set(1, 'one');

console.log(myMap.get('name')); // Jian
console.log(myMap.get(1)); // one

console.log(myMap.has('name')); // true

myMap.delete('name');
console.log(myMap.has('name')); // false

console.log(myMap.size); // 1

myMap.clear();
console.log(myMap.size); // 0
```
