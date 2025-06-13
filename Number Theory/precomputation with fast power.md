 #number_theory
If the number of power cases is limited (e.g. only powers of 2), it's often more efficient to precompute them in an array for constant-time O(1) access during queries.

For example, to precompute powers of 2 modulo `MOD` up to `MAX`:
```cpp
pw[0] = 1;
for (int i = 1; i < MAX; i++) 
    pw[i] = (pw[i - 1] * 2) % MOD;
```

**Lesson:** When you need the same expensive operation multiple times, precompute it.