In Java, arrays are fixed in size and can only hold elements of a single type.
# Init
## 1D Array
```java
// Initialize an array with a specific size (default values) 
int[] arr1 = new int[5]; // Creates an array of integers with 5 elements initialized to 0 
// Initialize an array with elements 
int[] arr2 = {1, 2, 3, 4, 5};
```
## 2D Array
```java
// Initialize a 2D array with default values (0)
int[][] array2D = new int[rows][cols]; 
```
# Methods
Java arrays have fewer built-in methods compared to JavaScript and Python, but the `java.util.Arrays` class provides many static methods for array manipulation. Additionally, using `ArrayList` can offer more dynamic features.
```java
import java.util.Arrays; 
import java.util.ArrayList; 
import java.util.List;

int[] arr = {1, 2, 3, 4, 5};

// Adding elements (use ArrayList for dynamic arrays)
List<Integer> list = new ArrayList<>(Arrays.asList(1, 2, 3, 4, 5));
list.add(6); // Adds to the end: [1, 2, 3, 4, 5, 6] 
list.add(0, 0); // Adds to the beginning: [0, 1, 2, 3, 4, 5, 6]

// Removing elements 
list.remove(list.size() - 1); // Removes from the end: [0, 1, 2, 3, 4, 5] 
list.remove(0); // Removes from the beginning: [1, 2, 3, 4, 5]

// Slicing (not directly available, but can be achieved with Arrays.copyOfRange) 
int[] subArr = Arrays.copyOfRange(arr, 1, 3); // [2, 3]

// Iterating 
for (int element : arr) { 
	System.out.println(element); // Prints each element 
}

// Mapping, filtering, and reducing (requires streams in Java 8+) 
int[] newArr = Arrays.stream(arr).map(x -> x * 2).toArray(); // [2, 4, 6, 8, 10] 
int[] filteredArr = Arrays.stream(arr).filter(x -> x > 2).toArray(); // [3, 4, 5] 
int sum = Arrays.stream(arr).reduce(0, (acc, x) -> acc + x); // 15

// Finding 
int found = Arrays.stream(arr).filter(x -> x > 2).findFirst().orElse(-1); // 3
```