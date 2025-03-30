- $x = x\ \&\ (x\ |\ y)$, i.e. if you have the bitwise AND (&) of two elements as value, you can factorize it to $(x, x\ |\ y)$
	e.g. $9 = 9\ \& \ (9\ |\ x)$ and with different values of x, you can get different pairs that their bitwise AND is 9
	when $x = 3$ -> $9\ |\ 3 = 11$, then $9 = 9\ \&\ 11$
	in the same way, $9 = 9\ \&\ 9$(trivial) $= 9\ \&\ 11 = 9\ \&\ 13 = 9\ \&\ 15$

- $x >= x\ \& \ y$, such that x and y are 2 arbitrary non-negative integers.
	- $x > x\ \&\ y$ iff $x$ contains at least '1' bit that is '0' in $y$.

## XOR properties
1. $x ⊕ y ⊕ y = x$
2. $x ⊕ y = x + y + 2(x\ \&\ y)$
3. if $x ⊕ y = z$, then $x ⊕ z = y$ 
4. if $x ⊕ y = z ⊕ w$, then $x ⊕ z = y ⊕ w$ (Can be proved using the previous point)
5. $x ⊕ y = (x\ \& \ y) ⊕ (x\ |\ y)$
6. $(x ⊕ y) = (x\ |\ y) - (x\ \&\ y)$ (XOR is the same OR unless when 2 bits are ones, then we subtract those ones by subtracting the & of the two numbers)

## Addition
- $a + b = (a$ & $b) + (a\ |\ b)$
- $a + b = a ⊕ b + 2(a\ \&\ b)$
- Sum without carry propagation = $a$ ^ $b$   (Bitwise XOR)


## Subtraction
- $a - b = (a ⊕ (a\ \&\ b))-((a\ \|\ b) ⊕ a)$
- $a - b = ((a\ \|\ b) ⊕ b)-((a\ \|\ b) ⊕ a)$
- $a - b = (a ⊕ (a\ \&\ b))-(b ⊕ (a\ \&\ b))$
- $a - b = ((a\ \|\ b) ⊕ b) - (b ⊕ (a\ \&\ b))$


- Useful Blog: [Some equations using bitwise operators](https://codeforces.com/blog/entry/94470)
