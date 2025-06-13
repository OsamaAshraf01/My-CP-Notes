#number_theory 
Suppose you're asked to compute `GCD(x, y)` where:
- `x = a^b`, a normal number raised to a normal number (but `x` is too large to store),
- `y` is normal storable number.

### Insight:
recall that essence of GCD: finding the greatest number that divides both x and y = $\max{(divisors_x \cap divisors_y)}$

### Approach:

1. Let `divisors_y` be all divisors of `y`.
2. For each `d` in `divisors_y` (sorted descending):
    - Compute `x mod d = a^b mod d` using fast power.
    - If `x % d == 0`, then `d` divides `x` too ⇒ **GCD = d**.
    - Stop at the first match (since we iterate from largest to smallest).

---

this note is related to [[Modular Arithmetic]], [[GCD]]
### Related Problems

- [CODECHEF GCDMOD](https://www.codechef.com/problems/GCDMOD)