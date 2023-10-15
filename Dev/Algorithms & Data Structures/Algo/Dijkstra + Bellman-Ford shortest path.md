![[unnamed (45).gif]]

not on the interview but may get a question on which one to use or most likely DFS


special cases algorithm to figure out the shortest path problem.  
  
You see breadth-first search is great for the shortest path problem but there's one thing  
  
If we go back here it is assumed that each path has the same weight with a depth-first search in a breath.  
  
First search we don't really care what kind of weight an edge has. For example, in real life such as Google Maps, some roads are faster than others. We have perhaps more traffic on one road maybe the distance from one note to another. It's shorter than the other and these weighted graphs which we've talked about have a number associated with their edges. Remember a node is called a vertex in a graph and the connection between two nodes is an edge and depth-first search doesn't really allow us to take into account these weights. We need something else.  
  
And in an interview, if somebody asked you this your answer should either be Belman Ford or disaster the algorithm that allows us to find the shortest path between two nodes of a weighted graph now Belman and Dijkstra are two real people that are academics that came up with their own algorithm to solve the shortest path problem of a weighted digraph such as Google Maps trying to figure out the closest way for you to get your burrito for example.  
  
  
Now both of these algorithms are quite complex and it takes a lot of time to really get it encoded. So I will leave resources for you if you want to learn more about these algorithms because in an interview it's very very rare that you'd ever have to code these algorithms.  
  
Most of the time you just have to know that they exist and when to use them. the Belman Ford algorithm is very effective at solving the shortest path algorithm because it can accommodate negative weights. So if a weighted graph has negative weights or a negative number Belman Ford algorithm is going to be able to solve the shortest path problem. While Dijkstra won't be able to. Now, why would you ever use Dijkstra then if the Belman Ford algorithm can do better, the Bellman-Ford algorithm can take a long time to run in terms of complexity and it's not the most efficient algorithm.  
  
The worst-case for Belman forward algorithm is usually the time complexity of all of and squit. So it's not very efficient.  
  
Dijkstra algorithm on the other hand is a little bit faster than that and a little bit more efficient with the downside that it can accommodate for negative waits between nodes.  
  
If an interviewer shows you this diagram and tells you I want to find the shortest path from 0 to 4 on this way to the graph, you now know why you should say.  
  
What algorithm are you going to use?  
  
Are you going to use a breath?  
First search Belman Ford algorithm or Dijkstra algorithm.  
  
The answer well it should be the Dijkstra algorithm.  
  
There are no negative weights on this graph. It's a weight graph.  
  
So, Dijkstra, is algorithm is going to solve that problem.  
using DFS for a graph feels like checking each path in a maze until you run through each path