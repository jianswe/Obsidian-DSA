## Graph terminology 
Vertices: Another term for nodes.
Edges: The connections between the nodes. Edges of a node can either be **directed or undirected**.
**Connected component**: A group of nodes that are connected by edges.
**Indegree**: The number of edges that can be used to reach the node
**Outdegree**: The number of edges that can be used to leave the node
**Neighbors**: Nodes that are connected by an edge
cyclic or acyclic: Cyclic means that the graph has a cycle, acyclic means that it doesn't.d
### How are graphs given in algorithm problems?
#### First input format: array of edges
In this input format, the input will be a 2D array. Each element of the array will be in the form `[x, y]`, which indicates that there is an edge between `x` and `y`.
![[Graph.png]]
This example graph can be represented by an array of directed edges: `edges = [[0, 1], [1, 2], [2, 0], [2, 3]]`.
Here's some example code for building `graph` from an array of edges:
```js
let buildGraph = edges => {
    let graph = new Map();
    for (const [x, y] of edges) {
        if (!graph.has(x)) {
            graph.set(x, []);
        }

        graph.get(x).push(y);

        // if (!graph.has(y)) {
        //     graph.set(y, []);
        // }

        // graph.get(y).push(x);
        // uncomment the above lines if the graph is undirected
    }
}
```

#### Second input format: adjacency list
In an adjacency list, the nodes will be numbered from `0` to `n - 1`. The input will be a 2D integer array, let's call it `graph`. `graph[i]` will be a list of all the outgoing edges from the 𝑖𝑡ℎ node.
The graph in the image above can be represented by the adjacency list `graph = [[1], [2], [0, 3], []]`.
**Notice**: with this input, we can already access all the neighbors of any given `node`. We don't need to do any pre-processing! This makes an adjacency list the most convenient format.
#### Third input format: adjacency matrix
the nodes will be numbered from `0` to `n - 1`. You will be given a 2D matrix of size `n x n`, let's call it `graph`. If `graph[i][j] == 1`, that means there is an outgoing edge from node `i` to node `j`. For example:
![[Graph - Adjacency matrix.png]]
#### Last input format: matrix
The last format we'll talk about is more subtle but very common. The input will be a 2D matrix and the problem will describe a story. Each square will represent something, and the squares will be connected in some way. For example, "Each square of the matrix is a village. Villages trade with their neighboring villages, which are the villages directly above, to the left, to the right, or below them."

In this case, each square `(row, col)` of the matrix is a node, and the neighbors are `(row - 1, col), (row, col - 1), (row + 1, col), (row, col + 1)` (if in bounds).


Back to [[README]]