#binary_search
When you encounter a pattern in an array such as:
- `0, 0, 0, 1, 1, 1, 1`
- or `1, 1, 0, 0, 0`
...and you're asked to **find the first or last occurrence** of a specific value (like the **first 1**, **last 0**, etc.), **think of using binary search with a custom check function**.

## Key Ideas:
- Typically, you're **binary searching for the value of `ans`**
- Design your **check function** to match the pattern you're exploiting.


## Helpful Strategy:
Use the concepts of **"at least"** and **"at most"** to define your check function.

For example, when you're trying to **maximize `ans`**, consider:
- If your check function is simply `f(x) = ans`, you might get a messy result like:  
    `1 0 0 0 0 1 0 0 0 0 0` → _not monotonic_, hard to binary search.
    
- Instead, if you redefine the check as `f(x) ≥ ans`, the pattern becomes monotonic:  
    `1 1 1 1 1 1 0 0 0 0 0` → ideal for binary search!
    

This approach ensures a **[[Monotonic Behavior]]**, which is crucial for a valid binary search.
