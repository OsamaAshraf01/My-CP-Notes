- Don't use `INT_MAX` if you are going to add to this variable (as this will lead to overflow).

- Read Problem statement carefully, take care from "pair", "at most", "at least", "once", ....

- if you have a global vector that used in multiple testacies, DO NOT just resize it in each test case as this will lead to a $RTE$ (it is only resized not cleared). You can either clear it before resizing or just reinitialize it with '=' operator.

- $(2^{32} - 1)$ is `UINT_MAX` not `INT_MAX`

- **PLEASE**, use `long long` if you are not sure, memory is not paid :/

- **Whenever** you initialize a GLOBAL variable, clear it in each case :/

- Instead of using `map<pii, int>` with complexity $O(log(n))$, use, if applicable, `vector<vector<int>>` with a pre-defined size to reduce complexity to $O(1)$.

- For a relation $<$ to be a **strict weak order**, it needs to satisfy two properties:
    1. **Irreflexivity:** No element is less than itself. For any element $a$ in the set, $a\ \nless a$. (in graph language: No self-loops)
    2. **Asymmetry:** if `compare(a, b)` is `true`, then `compare(b, a)` must be `false`. (in graph language: No bidirectional edges)
    3. **Transitivity:** if $a < b$ and $b < c$, then $a < c$. (in graph language: Edge paths imply direct edges).
    Visual Representation:
    ![[Strict Week Order.svg]]


- Different approaches for handling input and searching queries:
    1. `vector → sort → upper_bound(all(v), val)`: This approach is the best when the input is a static (batch processing) because:
       - Minimal space overhead (set space is bigger than vector because of its internal structure).
       - Sorting is one time cost (And if your input will be result of a pre-processing step, it may be already sorted).
       - `vector` has better cache locality for large datasets, making sorting and querying faster.
    2. `set → s.upper_bound(val)`: Better if input is dynamic and overlapping with queries:
       - Maintains a sorted order automatically.
       - Allows efficient insertions and queries on the fly.
    3. `vector → set → upper_bound`:
       - Almost as `approach 1` but with more space overhead.
       - Not logical to use, if you need the input as a vector, use `approach 1`, and if you need the input as a set use `approach 2`

