# Graphs
A graph is a non-linear data structure that can be looked at as a collection of vertices (or nodes) potentially connected by line segments named edges.

##  common terminology  of a graph: 
- Vertex - A vertex, also called a “node”, is a data object that can have zero or more adjacent vertices.
- Edge - An edge is a connection between two nodes.
- Neighbor - The neighbors of a node are its adjacent nodes, i.e., are connected via an edge.
- Degree - The degree of a vertex is the number of edges connected to that vertex.



## Directed vs Undirected

- Undirected Graphs((Bigraph))

An Undirected Graph is a graph where each edge is undirected or bi-directional. This means that the undirected graph does not move in any direction.

-directed Graphs((Digraph))

 A Directed Graph also called a Digraph is a graph where every edge is directed.
Unlike an undirected graph, a Digraph has direction. Each node is directed at another node with a specific requirement of what node should be referenced next.


## Complete vs Connected vs Disconnected

- Complete Graphs

A complete graph is when all nodes are connected to all other nodes.

- Connected

A connected graph is graph that has all of vertices/nodes have at least one edge.

- Disconnected

A disconnected graph is a graph where some vertices may not have edges.



## Acyclic vs Cyclic

- Acyclic Graph

An acyclic graph is a directed graph without cycles.

A cycle is when a node can be traversed through and potentially end up back at itself.A directed acyclic graph is also called a `DAG`. This can also be represented as what we know as a `tree`.


- Cyclic Graphs

A Cyclic graph is a graph that has cycles.
A cycle is defined as a path of a positive length that starts and ends at the same vertex.


## Graph Representation

- Adjacency Matrix

An Adjacency matrix is represented through a 2-dimensional array. If there are n vertices, then we are looking at an n x n Boolean matrix

- Adjacency List

- Adjacency List

An adjacency list is the most common way to represent graphs.


## Weighted Graphs

A weighted graph is a graph with numbers assigned to its edges. These numbers are called weights. This is what a weighted graph looks like:




## Traversals

- Breadth First

In a breadth first traversal, you are starting at a specific vertex/node. This node must be specified when calling the BreadthFirst() method.  Traversing a graph that has cycles will result in an infinite loop . To prevent such behavior, we need to have some way to keep track of whether a vertex has been “visited” before. Upon each visit, we’ll add the previously-unvisited vertex to a visited set, so we know not to visit it again as traversal continues.

As a refresher of what breadth first actually means here it is: Breadth first traversal is when you visit all the nodes that are closest to the root as possible. From there you traverse outwards, level by level, until you have visited all the vertices/nodes.

1.  Enqueue the declared start node into the Queue.
2. Create a loop that will run while the node still has nodes present.
3. Dequeue the first node from the queue
4. if the Dequeue‘d node has unvisited child nodes, add the unvisited children to visited set and insert them into the queue.



- Depth First

In a depth first traversal, we approach it a bit different than the way we do when working with a depth first traversal of a tree. Similar to how the breadth-first uses a queue, we are going to use a Stack for our depth-first traversal.


## Real World Uses of Graphs


Graphs are extremely popular when it comes to it’s uses. Here are just a few examples of graphs in use:

- GPS and Mapping
- Driving Directions
- Social Networks
- Airline Traffic
- Netflix uses graphs for suggestions of products