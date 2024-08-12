# Terminologies
* Parent node: the direct parent node of a vertex. 
* Root node: a node without a parent node; it can be viewed as the parent node of itself.  
![[disjoint set.png]]
# Implementing "disjoint sets"
The two important functions in a "disjoint set": 
* The **find** function: finds the root node of a given vertex. 
* The **union** function: unions two vertices and makes their root nodes the same. 
## Quick Find 
In this case, the time complexity of the `find` function will be O(1). However, the `union` function will take more time with the time complexity of O(N). 
```ts
class UnionFind {
	root: number[]

	constructor(size: number) {
		this.root = new Array(size)
		for (let i=0; i<size; i++) {
			this.root[i] = i
		}
	}

	find(x: number): number {
		return this.root[x]
	}

	union(x: number, y: number) {
		const rootX = this.find(x)
		const rootY = this.find(y)
		if (rootX !== rootY) {
			for (let i=0; i<this.root.length; i++) {
				if (this.root[i] === rootY) {
					this.root[i] = rootX
				}
			}
		}
	}
}
```
## Quick Union
