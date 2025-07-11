---
sr-due: 2025-07-12
sr-interval: 1
sr-ease: 230
---

#Graph #review 
****Kahn's Algorithm**** works by repeatedly finding vertices with no incoming edges, removing them from the graph, and updating the incoming edges of the vertices connected from the removed edges. This process continues until all vertices have been ordered.

### Algorithm:

- Add all nodes with in-degree 0 to a queue.
- While the queue is not empty:
    - Remove a node from the queue.
    - For each outgoing edge from the removed node, decrement the in-degree of the destination node by 1.
    - If the in-degree of a destination node becomes 0, add it to the queue.
- If the queue is empty and there are still nodes in the graph, the graph contains a cycle and cannot be topologically sorted.
- the popping order from the queue represent the topological ordering of the graph.

Kahn's algorithm is a [[Multi-Source BFS]] algorithm.