**Backtracking** is an optimization that involves abandoning a "path" once it is determined that the path cannot lead to a solution. 
Abandoning a path is also sometimes called "pruning". 
## Implementation
Backtracking is almost always implemented with recursion. 
Here is some pseudocode for a general backtracking format:
```
// let curr represent the thing you are building
// it could be an array or a combination of variables

function backtrack(curr) {
    if (base case) {
        Increment or add to answer
        return
    }

    for (iterate over input) {
        Modify curr
        backtrack(curr)
        Undo whatever modification was done to curr
    }
}
```

## LeetCode 
### [46. Permutations](https://leetcode.com/problems/permutations/)
![[backtrack - permutations.png]]
```ts
function permute(nums: number[]): number[][] {
	let ans = []
	function backtrack(perm) {
		if (perm.length === nums.length) {
			// When adding to the answer, we need to create a copy of `perm` because `perm` is only a reference to the array's address
			ans.push([...perm])
			return
		}
		for (const num of nums) {
			if (!perm.includes(num)) {
				perm.push(num)
				backtrack(perm)
				perm.pop(num)
			}
		}
	}
	backtrack([])
	return ans
};
```
#### Time Complexity
Let `n = nums.length`, 
the backtrack function will be called `n*(n-1)*...*1 = n!` times, 
inside the backtrack function, we have a loop over the `n` input elements, and the `includes` function cost `O(n)`, so the function call cost `O(n^2)` 
Overall, `O(n^2*n!)`, or `O(n*n!)` if we use a separate hash set to track elements in `perm`. 
### [78. Subsets](https://leetcode.com/problems/subsets/)
![[backtrack - subsets.png]]
```ts
function subsets(nums: number[]): number[][] {
	let ans = []
	
	function backtrack(i, subset) {
		if (i>nums.length) return
		ans.push([...subset])
		for (let j=i; j<nums.length; j++) {
			subset.push(nums[j])
			backtrack(j+1, subset)
			subset.pop(nums[j])
		}
	}
	
	backtrack(0, [])
	return ans
};
```
