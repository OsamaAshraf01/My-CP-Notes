#Graph 
Given an undirected graph where every edge has a weight as either 0 or 1. The task is to find the ****shortest path**** from the source vertex to all other vertices in the graph.

Naive Approach: Using Dijkstra Algorithm - $O(E * log (V))$ Time and $O(V)$ Space.
Better Approach: Using **Deque** - $O(V + E)$ time and $O(V + E)$ space
The idea is to adapt BFS to efficiently handle graphs with binary weights (0 or 1) by using a deque instead of a queue. When we encounter an edge with weight 0, we add its destination to the front of the deque (higher priority - process first) because it doesn't increase the distance. When we encounter an edge with weight 1, we add its destination to the back of the deque because it increases the distance by one unit.