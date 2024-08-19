In JavaScript, arrays are dynamic and can hold different types of elements.
# Init
## 1D Array
```js
// Initialize an array using the Array constructor
let arr1 = new Array(5); // Creates an array with 5 empty slots
let arr2 = new Array(1, 2, 3, 4, 5); // Creates an array with specified elements
let arr3 = new Array(5).fill(0); // Creates an array of 5 zeros. 
```
## 2D Array
Using `Array.from`
```js
const array = Array.from({ length: rows }, () => Array(cols).fill(0))
```
Using `fill`
```js
const array = new Array(rows).fill(null).map(() => new Array(cols).fill(0))
```
**Caution**: Do not use 
```js
const array = new Array(rows).fill(new Array(cols).fill(0)) 
```
since `fill` will use the same reference if passed in object, not primitive. 
# Methods
JavaScript arrays have numerous built-in methods to manipulate arrays:
```js
let arr = [1, 2, 3, 4, 5];

// Adding elements 
arr.push(6); // Adds to the end: [1, 2, 3, 4, 5, 6] 
arr.unshift(0); // Adds to the beginning: [0, 1, 2, 3, 4, 5, 6]

// Removing elements 
arr.pop(); // Removes from the end: [0, 1, 2, 3, 4, 5] 
arr.shift(); // Removes from the beginning: [1, 2, 3, 4, 5]

// Slicing and splicing 
let subArr = arr.slice(1, 3); // [2, 3] 
arr.splice(2, 1); // Removes one element at index 2: [1, 2, 4, 5]

// Iterating 
arr.forEach((element) => console.log(element)); // Prints each element

// Mapping 
let newArr = arr.map((element) => element * 2); // [2, 4, 8, 10]

// Filtering 
let filteredArr = arr.filter((element) => element > 2); // [4, 5] 

// Reducing 
let sum = arr.reduce((acc, element) => acc + element, 0); // 12 

// Finding 
let found = arr.find((element) => element > 2); // 4
```