#Graph
Vertex Multiplexing is a technique where **a single logical vertex in a graph is split into multiple physical vertices (layers)** to simulate states.
think of it like you are adding another dimension to vertices, you move them from 1D (just the number of edge) to higher dimensions to allow further information to be embed in each node. This way, each node can be represented by many different nodes based on different states.
![[Vertex Multiplexing.webp]]


### Implementation
In Dijkstra/BFS/DFS, your node isn’t just an integer anymore—it’s `(vertex, state)`.

### Why Do This?
In many problems, vertices have **states**, **time steps**, **parities**, or **limits** that affect traversal. Since standard graph algorithms (like Dijkstra, BFS) work on simple graphs, we simulate those states by **duplicating vertices**—each copy represents a specific version or context of that node.

### When to Use?
Use vertex multiplexing when:
- The path/state depends on **history** (e.g., used teleport, moved even times).
- Constraints can't be expressed purely through edge weights.
- You're told “**do something at most once / at most k times**”.


### Summary
**Vertex Multiplexing** means:
> “Turning each logical vertex into multiple physical nodes to simulate different states.”



---
### Related Problems

- [AtCoder-ABC410-D](https://atcoder.jp/contests/abc410/tasks/abc410_d)


this note is related to [[graph traversal]]