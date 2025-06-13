you can define a new function $f$ that maps from the given functions. This can help reveal patterns and simplify your thinking. 
- If this new function has overlapping properties, you can preprocess it in `O(N)` time and then answer queries for $f_i$ in `O(1)` time—similar to how prefix sums work.
- Preprocessing can be done using [[DP]], [[Prefix Sum]], or cumulative techniques.
- Map → Preprocess/Identify Patterns → Query Efficiently.