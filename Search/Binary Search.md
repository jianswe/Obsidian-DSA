O(logN)
# Three templates of BS 
## Template I 
```python
def binarySearch(nums, target):
    """
    :type nums: List[int]
    :type target: int
    :rtype: int
    """
    if len(nums) == 0:
        return -1

    left, right = 0, len(nums) - 1
    while left <= right:
        mid = (left + right) // 2
        if nums[mid] == target:
            return mid
        elif nums[mid] < target:
            left = mid + 1
        else:
            right = mid - 1

    # End Condition: left > right
    return -1
```
* No post-processing required because at each step, you are checking to see if the element has been found. If you reach the end, then you know the element is not found. 
## Template II
```python 
def binarySearch(nums, target):
    """
    :type nums: List[int]
    :type target: int
    :rtype: int
    """
    if len(nums) == 0:
        return -1

    left, right = 0, len(nums) - 1
    while left < right:
        mid = (left + right) // 2
        if nums[mid] == target:
            return mid
        elif nums[mid] < target:
            left = mid + 1
        else:
            right = mid

    # Post-processing:
    # End Condition: left == right
    if nums[left] == target:
        return left
    return -1
```
* Guarantees Search Space is at least 2 in size at each step. 
* Post-processing required. Loop/Recursion ends when you have 1 element left. Need to assess if the remaining element meets the condition. 
## Template III
```python 
def binarySearch(nums, target):
    """
    :type nums: List[int]
    :type target: int
    :rtype: int
    """
    if len(nums) == 0:
        return -1

    left, right = 0, len(nums) - 1
    while left + 1 < right:
        mid = (left + right) // 2
        if nums[mid] == target:
            return mid
        elif nums[mid] < target:
            left = mid
        else:
            right = mid

    # Post-processing:
    # End Condition: left + 1 == right
    if nums[left] == target: return left
    if nums[right] == target: return right
    return -1
```
* Guarantees Search Space is at least 3 in size at each step. 
* Post-processing required. Loop/Recursion ends when you have 2 elements left. Need to assess if the remaining elements meet the condition. 

# LeetCode 
## [162. Find Peak Element](https://leetcode.com/problems/find-peak-element/)
### Solution 1: Using Template II
```typescript
function findPeakElement(nums: number[]): number {
    let left = 0, right = nums.length-1
    while(left<right) {
        const mid = Math.floor((left+right)/2)
        const numLeft = mid-1<0 ? -Infinity : nums[mid-1]
        const numRight = mid+1===nums.length ? -Infinity : nums[mid+1]
        if (numLeft<nums[mid] && nums[mid]>numRight) return mid 
        else if (numLeft<nums[mid] && nums[mid]<numRight) left = mid+1
        else right = mid
    }
    return left 
};
```
### Solution 2: Using Template III 
```ts
function findPeakElement(nums: number[]): number {
	let left = 0, right = nums.length-1
	while(left+1<right) {
		const mid = Math.floor((left+right)/2)
		const numLeft = mid-1<0 ? -Infinity : nums[mid-1]
		const numRight = mid+1===nums.length ? -Infinity : nums[mid+1]
		if (numLeft<nums[mid] && nums[mid]>numRight) return mid
		else if (numLeft<nums[mid] && nums[mid]<numRight) left = mid
		else right = mid
	}
	if ((nums[left-1]??-Infinity)<nums[left] && nums[left]>nums[right]) return left
	return right
};
```