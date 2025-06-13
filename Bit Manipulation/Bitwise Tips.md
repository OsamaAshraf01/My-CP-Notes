#bit_manipulation
- $x = x\ \&\ (x\ |\ y)$, i.e. if you have the bitwise AND (&) of two elements as value, you can factorize it to $(x, x\ |\ y)$
	e.g. $9 = 9\ \& \ (9\ |\ x)$ and with different values of x, you can get different pairs that their bitwise AND is 9
	when $x = 3$ -> $9\ |\ 3 = 11$, then $9 = 9\ \&\ 11$
	in the same way, $9 = 9\ \&\ 9$(trivial) $= 9\ \&\ 11 = 9\ \&\ 13 = 9\ \&\ 15$

- $x >= x\ \& \ y$, such that x and y are 2 arbitrary non-negative integers.
	- $x > x\ \&\ y$ iff $x$ contains at least '1' bit that is '0' in $y$.

- Number's parity in addition is somehow related to XOR operations:
	- even + even = even
	- even + odd = odd
	- odd + even = odd
	- odd + odd = even
	so, if we represented even as 0 and odd as 1, then the following formula is right: $result_{parity} = x_{parity}  ⊕ y_{parity}$
	--> revise _[[Sierpinski Triangle]]_  

