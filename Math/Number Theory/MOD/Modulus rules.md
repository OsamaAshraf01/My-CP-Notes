#number_theory
- Modulus with subtraction:$$a - b\ (mod\ M) = ((a-b) \% M + M) \% M$$
	- Why? revise [[Modulus Handling for Negative Numbers]]
	- this is because $a-b$ can be negative. 
	- Generally, adding or subtracting M from number does not affect the result of modulus.

- Modulus with multiplication:
$$\quad (a * b)\ \%\ M = ((a\ \%\ M) * (b\ \%\ M))\ \%\ M$$

- Modulus with division, using [[Fermat's Little Theorem]]: (revise [[Modulus meaning with fractions]])
$$
\begin{aligned}
\frac{a}{b}\;\%\;M &= (a * b^{-1})\;\%\;M \\
  &= ((a\;\%\;M) * (b^{\,-1}\;\%\;M))\;\%\;M \\
  &= ((a\;\%\;M) * (b^{\,M-2}\;\%\;M))\;\%\;M &\text{(Fermat's Little Theorem)}\\
  &= ((a\;\%\;M) * fast\_power(b, M-2, M))\;\%\;M &\text{(fast power in O(log(M)))}\\
\end{aligned}
$$
