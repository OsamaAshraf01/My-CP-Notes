#Graph  
When working with tree problems, always check whether the edges are directed or undirected:  
  
- If edges are given in a directed format (e.g., `{from, to}`), you can treat the tree as a directed graph. In this case, a **leaf node** is any node where `adjList[node]` is empty.  
  
- If edges are not ordered, the tree should be treated as an undirected graph. In this case, a **leaf node** is a node that has no unvisited children during traversal.


---
this note is important when in [[trees traversal]]