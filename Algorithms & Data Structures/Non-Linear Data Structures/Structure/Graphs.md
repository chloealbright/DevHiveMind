---
tags: 
author: jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
![[unnamed (44).gif]]

don't focus on too much for interview


Graph from discrete math with everything connecting to each other in some way by edges and vertices are also known as nodes  
  
Graphs are naturally concurrent meaning several things are happening at the same time  
  
Edges and vertices are usually in ordered or unordered pairs  
  
Edges are identified by the unique endpoints and can be of two types which are directed and undirected  
  
Directed it's usually ordered pairs consisting of origin and destination  
  
An undirected is usually unordered and is bidirectional and origin and destination isn't fixed  
  
A graph can consist of both directed and undirected edges  
  
  
Graphs can also be weighted and unweighted meaning the edges can have values when it comes to a weighted as opposed to unweighted where there are no values associated with the edges the reason that there are values associated with the edges when it comes to weighted is to determine the shortest path  
  
Graphs can be acyclic or cyclic meaning it could be like a triangle with three lines connecting each other or acyclic meaning the three lines don't all connect so it can almost look like an "L"  
  
cyclic graphs tend to be weighted and are used a lot for Google maps of all time this is my favorite crap  
  
Graphs can be built with trees and a linked list  
  
And edgeless is basically an array that stores nested pairs that are connected to each other  
  
Use object for graphs instead of arrays  
  
Graphs are good for relationships but are hard for scaling up  
  
Application of graphs  
_____________________  
Social media and websites like LinkedIn where you're connected to different people and they are connected to other people on your might have similar collections  
  
Web crawlers which use graph traversal what's your time to see and search engines when you searching for a website  
  
Graphs are used a lot with Google maps for determining the shortest path to a destination  
  
Trees are considered a type of graph



Yes, graphs can be implemented using linked lists. This is commonly referred to as an "adjacency list" representation of a graph. In an adjacency list, each vertex of the graph is associated with a list of its neighboring vertices. This approach is particularly useful for sparse graphs where the number of edges is much smaller than the maximum possible number of edges.

Here's how an adjacency list representation works using linked lists:

1. Create a linked list for each vertex in the graph.
2. For each vertex, populate its linked list with pointers or references to the neighboring vertices it's connected to.

Advantages of using linked lists for graph representations (adjacency lists) include:

1. Efficient memory usage: In sparse graphs, where there are relatively few edges, an adjacency list can be much more memory-efficient compared to an adjacency matrix (a 2D array representation of a graph).
2. Dynamic structure: Linked lists allow for dynamic resizing, making it easy to add or remove vertices and edges from the graph.

Comparing linked list-based graph implementations to array-based implementations (adjacency matrices):

- **Memory Usage:** Linked lists are generally more memory-efficient for sparse graphs, while adjacency matrices may be more memory-efficient for dense graphs. Adjacency matrices use O(V^2) memory, where V is the number of vertices, whereas adjacency lists typically use O(V + E) memory, where E is the number of edges.

- **Edge Lookup:** In an adjacency list, looking up edges connected to a vertex takes O(degree), where the degree is the number of neighbors. In an adjacency matrix, edge lookup is constant time (O(1)). Therefore, for dense graphs or when you need to perform frequent edge lookups, adjacency matrices can be more efficient.

- **Space and Insertion Complexity:** Linked lists are more space-efficient for sparse graphs, and they have lower insertion complexity when adding or removing edges. Adjacency matrices are better suited for dense graphs and have constant-time insertion or removal complexity.

In summary, the choice between using linked lists or arrays (adjacency lists or matrices) for graph implementation depends on the specific characteristics of your graph, such as its density and the operations you need to perform. Sparse graphs with dynamic requirements often favor linked list-based implementations, while dense graphs and frequent edge lookups may benefit from array-based representations.