#optimization #Greedy #DP #Backtracking #binary_search 
if you are facing an optimization problem, think in the follow:
1. **Brute Force**: do problem constraints enable us to brute force?
2. **Greedy**: Can you come up with a greedy assumption that will lead to global optimal?
	- yes? prove it
	- or try to refute it using counterexamples. If can't, give it a try!
3. **DP**: can you make an array that can store all different states of the problem completely?
4. **Backtracking with pruning**: if you wrote a brute force recursive solution, can you define subtrees as hopeless so you can prune it?
5. **Binary Search**: Can you define a function $f$ that is monotonic and can be evaluated in at most O(n), such that you can guess answer in O(log(n))?
6. **Mathematical Observations**: Can you reduce the problem using **mathematical insight**?
    - Convexity/Concavity    
    - Modular arithmetic
    - Counting or combinatorial simplifications
