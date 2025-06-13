#number_theory
Be careful when taking modulo of a negative number. Instead of using `(ans + MOD) % MOD`, which fails for values like `-2*MOD`, use:

`((ans % MOD) + MOD) % MOD;`
This ensures `ans` is always in the range `[0, MOD)` efficiently.


This works for all integers, including large negative ones. Here's why:
- `ans % MOD` may be negative `[-MOD, MOD)`.
- Adding `MOD` ensures it's in the `[0, 2*MOD)` range.
- Applying `% MOD` again brings it to `[0, MOD)`.