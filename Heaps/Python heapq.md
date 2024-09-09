# Purpose 
Implements a binary heap for efficiently handling priority queues, where the smallest (min-heap) or largest (max-heap, with extra work) element can always be accessed quickly.
# Usage
Min-heaps are common in use cases like Dijkstra's algorithm or finding the k smallest/largest elements.
# Performance 
Offers `O(log n)` time complexity for insertion and extraction.
# Methods 
* `heapq.heappush(heap, item)`: Adds an item to the heap.
* `heapq.heappop(heap)`: Removes and returns the smallest item.
* `heapq.heapify(iterable)`: Converts an iterable into a heap in `O(n)` time.
* `heapq.nlargest(n, iterable)`: Returns the `n` largest elements.
* `heapq.nsmallest(n, iterable)`: Returns the `n` smallest elements.
* `heapq.heappushpop(heap, item)`: Push the item onto the heap, then pop and return the smallest item from the heap. The combined action runs more efficiently than `heappush()` followed by a separate call to `heappop()`. 
* `heapq.heapreplace(heap, item)`: Pop and return the smallest item from the heap, and then push the new item. The heap size is unchanged. If the heap is empty, an `IndexError` is raised.  
# Example
```python
import heapq

# Create an empty heap
heap = []

# Push some values onto the heap
heapq.heappush(heap, 10)
heapq.heappush(heap, 20)
heapq.heappush(heap, 5)

# Pop the smallest value off the heap
smallest = heapq.heappop(heap)
print(smallest)  # Output: 5

# Push and pop in one step
heapq.heappushpop(heap, 15)

# Replace the smallest value and return it
replaced = heapq.heapreplace(heap, 25)
print(replaced)  # Output: 10

# Transform a list into a heap
data = [1, 3, 5, 7, 9, 2, 4, 6, 8, 0]
heapq.heapify(data)
print(data)  # Output: [0, 1, 2, 3, 9, 5, 4, 6, 8, 7]

# Get the 3 largest values
largest = heapq.nlargest(3, data)
print(largest)  # Output: [9, 8, 7]

# Get the 3 smallest values
smallest = heapq.nsmallest(3, data)
print(smallest)  # Output: [0, 1, 2]
```