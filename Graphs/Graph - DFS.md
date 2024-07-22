Example 1: [547. Number of Provinces](https://leetcode.com/problems/number-of-provinces/)

There are `n` cities. A province is a group of directly or indirectly connected cities and no other cities outside of the group. You are given an `n x n` matrix `isConnected` where `isConnected[i][j] = isConnected[j][i] = 1` if the 𝑖𝑡ℎith city and the 𝑗𝑡ℎjth city are directly connected, and `isConnected[i][j] = 0` otherwise. Return the total number of provinces.
```js
/**
 * @param {number[][]} isConnected
 * @return {number}
 */
var findCircleNum = function(isConnected) {
    let dfs = node => {
        for (const neighbor of graph.get(node)) {
            // the next 2 lines are needed to prevent cycles
            if (!seen[neighbor]) {
                seen[neighbor] = true;
                dfs(neighbor);
            }
        }
    }
    
    // build the graph
    let n = isConnected.length;
    let graph = new Map();
    for (let i = 0; i < n; i++) {
        graph.set(i, []);
    }
    
    for (let i = 0; i < n; i++) {
        for (let j = i + 1; j < n; j++) {
            if (isConnected[i][j]) {
                graph.get(i).push(j);
                graph.get(j).push(i);
            }
        }
    }
    
    let seen = new Array(n).fill(false);
    let ans = 0;
    
    for (let i = 0; i < n; i++) {
        if (!seen[i]) {
            ans++;
            seen[i] = true;
            dfs(i);
        }
    }
    
    return ans;
};
```

Back to [[README]]