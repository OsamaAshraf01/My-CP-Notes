#data-structures
Monotonic Stack maintaining elements in either _increasing_ or _decreasing_ order. It is commonly used to efficiently solve problems like:
- Next Greater Element (NGE)
- Next Smaller Element (NSE)
- Previous Greater Element (PGE) 
- Previous Smaller Element (PSE)

---
tips for solving next/previous grater/smaller elements in array questions:
1. **Direction of Traversal**:
    - **Next**: Traverse **from the end to the start** (right to left).
    - **Previous**: Traverse **from the start to the end** (left to right).

2. **Stack Order**:
    - **Greater** queries: Use a **monotonic decreasing stack** (elements decrease from bottom to top).
    - **Smaller** queries: Use a **monotonic increasing stack** (elements increase from bottom to top).



this note may be related to [[Monotonic Patterns]]