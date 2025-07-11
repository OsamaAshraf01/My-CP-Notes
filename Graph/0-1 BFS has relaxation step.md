#Graph 
0/1 BFS has a relaxation step similar to which found in Dijkstra as when you reach a node it's not necessarily the min cost. 
For example:
imagine you are traversing a 2D grid, and you are on node {0, 0}, and assume that the cost from this node to {0, 1} is one
you may have another path {0, 0} -> {1, 0} -> {1, 1} -> {0, 1} with all edges' cost equal to zero, then this will be the shortest path.

But, in 0/1 BFS you don't need to keep track and extract the minimum value node as the deque handles this efficiently.


### My Submissions for problem [UVA-11573](https://vjudge.net/problem/UVA-11573)
- [WA solution - Normal BFS](https://vjudge.net/solution/61618029/ad5Ct3fYVJTb5wBtgQmU)
- [AC Solution - Relaxation Used](https://vjudge.net/solution/61618963/2NJVR0uOF2ZgEmrrkrfe)


---
this note is related to [[0-1 BFS]]