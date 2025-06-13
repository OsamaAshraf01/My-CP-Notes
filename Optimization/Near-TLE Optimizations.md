#optimization #loop-optimization #time-limit

If your code is near TLE, **increase the loop step size strategically** to reduce total iterations *without increasing work per iteration*. This works when you can:  
1. **Pre-process edge cases** outside the loop, and  
2. **Skip redundant checks** in the main loop.  

**Example: Primality Check**  
```cpp
bool is_prime(int n) {
    if (n <= 1) return false;
    if (n % 2 == 0) return (n == 2); // Pre-process even case
    
    // Main loop skips even numbers (i += 2)
    for (int i = 3; i*i <= n; i += 2) { 
        if (n % i == 0) return false;
    }
    return true;
}
```  
- **Before**: Loop runs `O(√n)` times (checking all numbers 2, 3, 4, 5, ...).  
- **After**: Loop runs `O(√n / 2)` times (only checks 3, 5, 7, ...).  

By handling even numbers upfront, the main loop skips 50% of iterations *with the same work per iteration* (one modulus operation).

**Bad Example** (No Net Gain):  
```cpp
bool is_prime(int n) {
    if (n <= 1) return false;
    
    for (int i = 3; i*i <= n; i += 2) { 
        if (n % i == 0) return false;
        if (n % (i + 1) == 0) return false;
    }
    return true;
}
```  
Here, `i += 2` reduces the iterations to the half, but we double the work per iteration, which means no net gain.

**When It Works**  
- When pre-processing allows you to **eliminate a subset of cases permanently** (e.g., even numbers in primes), or you can skip some cases by improving your logic.
- When skipped iterations **don’t need separate checks** inside the loop.  