# Graphs
A graph is a non-linear data structure that can be looked at as a collection of vertices (or nodes) potentially connected by line segments named edges.
## Terminology
1. Vertex - A vertex, also called a “node”, is a data object that can have zero or more adjacent vertices.
2. Edge - An edge is a connection between two nodes.
3. Neighbor - The neighbors of a node are its adjacent nodes, i.e., are connected via an edge.
4. Degree - The degree of a vertex is the number of edges connected to that vertex.
## Directed vs Undirected
### Undirected Graphs
An Undirected Graph is a graph where each edge is undirected or bi-directional. This means that the undirected graph does not move in any direction.
### Directed Graphs (Digraph)
A Directed Graph also called a Digraph is a graph where every edge is directed.
Unlike an undirected graph, a Digraph has direction. Each node is directed at another node with a specific requirement of what node should be referenced next.

## Complete vs Connected vs Disconnected
### Complete Graphs
A complete graph is when all nodes are connected to all other nodes.
### Connected Graphs
A connected graph is graph that has all of vertices/nodes have at least one edge.

### Disconnected Graphs
A disconnected graph is a graph where some vertices may not have edges.

## Acyclic vs Cyclic
## Acyclic Graph
An acyclic graph is a directed graph without cycles.

A cycle is when a node can be traversed through and potentially end up back at itself.
## Cyclic Graphs
A Cyclic graph is a graph that has cycles.

A cycle is defined as a path of a positive length that starts and ends at the same vertex.

## Graph Representation
### Adjacency Matrix
An Adjacency matrix is represented through a 2-dimensional array. If there are n vertices, then we are looking at an n x n Boolean matrix

Each Row and column represents each vertex of the data structure. The elements of both the column and the row must add up to 1 if there is an edge that connects the two, or zero if there isn’t a connection

**a sparse graph is when there are very few connections. a dense graph is when there are many connections**

### Adjacency List
An adjacency list is a collection of linked lists or array that lists all of the other vertices that are connected.

## Weighted Graphs
A weighted graph is a graph with numbers assigned to its edges. These numbers are called weights. 

## Traversals
### Breadth First
- Enqueue the declared start node into the Queue.
- Create a loop that will run while the node still has nodes present.
- Dequeue the first node from the queue
- If the Dequeue‘d node has unvisited child nodes, add the unvisited children to visited set and insert them into the queue.
- If there are any disconnected nodes (such as islands) with the graph data structure, they will not be traversed.

## Depth First
- Push the root node into the Stack and mark as visited.
- Start a while loop that runs as long as the stack is not empty.
- Pop the top node off of the stack and check its neighbors.
- If a neighbor hasn’t been visited, push it onto the stack and mark as visited.
- Repeat until the stack is empty.