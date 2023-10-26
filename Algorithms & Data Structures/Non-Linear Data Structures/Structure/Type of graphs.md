![[unnamed (46).gif]]

  
## Graph  
  
A collection of nodes or values called vertices that might be related relations between vertices are called edges.  
  
Many things in life can be represented by graphs for example, a social network can be represented by a graph whose vertices are users and whose edges are friendships between the users. Similarly, a city map, can be represented by a graph whose vertices are locations in the city and whose edges are roads between the locations  
  
## Graph Cycle  
  
Simply put, a cycle occurs in a graph when three or more vertices in the graph are connected so as to form a closed loop  
  
Note that the definition of a graph cycle is sometimes broadened to include cycles of length two or one: in the context of coding interviews, when dealing with questions that involve graph cycles, it's important to clarity what exactly constitutes a cycle.  
  
## Acyclic Graph  
  
A graph that has no cycles.  
  
## Cyclic Graph  
  
A graph that has at least one cycle  
  
## Directed Graph  
  
A graph whose edges are directed, meaning that they can only be traversed in one direction, which is specified.  
  
For example, a graph of airports and lights would likely be directed, since a flight specifically goes from one airport to another (i.e. It has a directions) without necessarily implying the presence of a flight in the opposite direction.  
  
## Un-directed Graph  
  
A graph whose edges are directed, meaning that they can be traversed in both directions For example, a graph of friends would likely be un-directed, since a friendship is, by nature, bidirectional  
  
## Connected Graph  
  
A graph is connected if for every pair of vertices in the graph, there's a path of one or more edges connecting the given vertices  
  
in the case of a directed graph, the graph is:  
  
strongly connected if there are bidirectional connections between the vertices of every pair of vertices (i.e, for every vertex-pair (u, v) you can reach v from u and u from v)  
  
weakly connected if there are connections (but not necessarily bidirectional anes) between the vertices of every pair of vertices  
  
A graph that isn't connected is said to be disconnected  
  
[https://anushsom.medium.com/graphs-and-graph-traversal-algorithms-for-dummies-by-a-dummy-dd19149f4882](https://anushsom.medium.com/graphs-and-graph-traversal-algorithms-for-dummies-by-a-dummy-dd19149f4882)  
  
  
[https://medium.com/geekculture/graphs-or-networks-chapter-1-57aa9497be06](https://medium.com/geekculture/graphs-or-networks-chapter-1-57aa9497be06)


Not built into java but  can implement the graph using Java Collections. 

[https://www.baeldung.com/java-graphs#:~:text=4.,the%20graph%20using%20Java%20Collections](https://www.baeldung.com/java-graphs#:~:text=4.,the%20graph%20using%20Java%20Collections).


## Edit Merge
A Undirected Graph
A Directed Graph

Directed Acyclic Graphs(DAG) - are directed graphs with no directed cycles.

Weighted DAG(directed networks)
Weighted DAG with negative edges

Each of graph type has a different representation, API and problem solved. Lets code non-recursive implementation for algorithm candidates and connect with Graphs type API.


Depth-first search (DFS) an algorithm for traversing or searching graph or tree. It uses a stack, and it delays checking whether a vertex has been discovered until the vertex is popped from the stack rather than making this check before adding the vertex.  

Time Complexity: O(E+V)  
Undirected Graph  
Directed Acyclic Graphs(DAG) without weight  


Breadth-first search (BFS) is an algorithm for traversing or searching tree or graph data structures. It uses a queue.  
Time Complexity: O(E+V)  
Undirected Graph  
Directed Acyclic Graphs(DAG) without weight  


Dijkstra’s algorithm is for finding the shortest path between nodes in the Graphs. It picks the unvisited vertex with the lowest distance, calculates the distance through it to each unvisited neighbor, and updates the neighbor’s distance if smaller. It uses a Priority queue.  
Time Complexity: O(E+V log V)  
non-negative weighted DAG  


The Bellman-Ford algorithm is an algorithm that computes the shortest paths from a single source vertex to all of the other vertices in a weighted digraph. It uses 2 for loop, what makes time complexity Vertex * Edges in worst cases.  
Time Complexity: O(VE)  
negative or positive weighted DAG  

Implementation pattern  
Stack - Depth-first search ((O(E+V)))  
Queue - Breadth-first search (O(E+V))  
Priority Queue - Dijkstra’s algorithm (O(E+V log V))  


Bellman-Ford is similar to Dijkstra's except that instead of utilizing a Priority Queue to visit nodes in order, Bellman-Ford looping iterates over every edge V times each, ensuring that all negative edge weights.  

Time Complexity different: O(E+V log V) vs O(N)  

Dijkstra’s algorithm work O(E+V log V) ONLY if the priority queue has O(log N) add/remove complexity.