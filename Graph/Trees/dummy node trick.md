#Graph 
In rooted trees, the root node often requires special handling due to the absence of a parent. To simplify traversal logic (especially in DFS or BFS), you can add a dummy node as the parent of the root. This makes the root behave like any other node, avoiding edge cases and ensuring uniform processing.


# Related Problems
[CF2117-D3-F](https://codeforces.com/contest/2117/problem/F) --> compare [323708086(bad)](https://codeforces.com/contest/2117/submission/323708086) and [323709757(good)](https://codeforces.com/contest/2117/submission/323709757). by the way, the WA I got for this problem was because of this edge case handling :)



---
this note is related to [[trees traversal]]