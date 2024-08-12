# What is a spanning tree? 
A **spanning tree** is a connected subgraph in an undirected graph where **all vertices** are connected with the **minimum number** of edges. 
![[spanning tree.png]]
# What is minimum spanning tree? 
A **minimum spanning tree** is a spanning tree with the minimum possible total edge weight in a "weighted undirected graph". 
![[minimum spanning tree.png]]
# Cut Property 
## What is a "cut"? 
* First, in Graph theory, a "cut" is a partition of vertices in a "graph" into two disjoint subsets. 
* Second, a crossing edge is an edge that connects a vertex in one set with a vertex in the other set. 
![[graph with a cut.png]]
The "cut property" refers to: 
For any cut C of the graph, if the weight of an edge E in the cut-set of C is strictly smaller than the weights of all the other edges of the cut-set of C, then this edge belongs to all MSTs of the graph. 
# Kruskal's Algorithm 
produces Minimum Spanning Tree 
1. Ascending sort all edges by their weight 
2. Add edges in that order into the Minimum Spanning Tree. Skip the edges that would produce cycles in the Minimum Spanning Tree. 
3. Repeat step 2 until N-1 edges are added. 