- $(2ab + 2bc + 2ca) = (a + b + c)^2 - (a^2 + b^2 + c^2)$
   **Example:**
   for $n$ numbers:
		$(a - b)^2 + (a - c)^2 + (b - c)^2 + ...$
		$= (n - 1)(a^2 + b^2 + c^2 + ...) - (2ab + 2bc + 2ca + ...)$
		$= (n)(a^2 + b^2 + c^2 + ...) - (a + b + c + ...)^2$

- <b style="color:cyan;">Fermat's Little Theorem:</b> if $p$ is a prime number and $a$ is not divisible by $p$ then,
    $a^p\ \%\ p = a\ \%\ p$
    and $a^{p - 1}\ \%\ p = 1$
    and $a^{-1}\ \%\ p = a^{p - 2}\ \%\ p$ ----> important for factions and Combinations

    **Correction:** In the case of fractions, Not if $p$ is prime, but if and only if $gcd(a,\ p) = 1$. 
    In other words, the denominator must be *relatively prime* to the modulus.

- Modulus meaning with fractions:
    when you say: $(a/b)\%n$, you're referring to a number $x$ such that $(b*x) \% n ≡ a \% n$.

- The $MEX$ of $N$ numbers **cannot** exceed $N$.

- When using %, Be careful from:
    - subtraction: $\quad (a - b)\ \%\ M$ $=$ $(a - b + M)\ \%\ M$ ~ in case that $a-b$ can be negative. Generally, adding or subtracting M from number does not affect the result of modulus.
    - division: $\quad (a / b)\ \%\ M$ $=$ $((a\ \%\ M)\ *$ `fast_power(b, M - 2, M)`$)\ \%\ M$
    - multiplication: $\quad (a * b)\ \%\ M$ $=$ $((a\ \%\ M) * (b\ \%\ M))\ \%\ M$

- $\sum_{i=0}^{n}{\sum_{j=i+1}^{n}{(a_i*a_j)}}$
	$= \sum_{i=0}^{n}{(a_i * \sum_{j=i+1}^{n}{a_j})}$
	$= {(\sum_{i=0}^{n}{a_i})}^2 - \sum_{j=0}^{n}{(a_j^2)}$ 
	- **For more clarification**, revise First point in this file.

- To compare 2 double numbers, don't use the direct comparison. Use the following approach:
```C++
int dcmp(double a, double b, double EBS = 1e-10){
	if(fabs(a - b) < EBS)
		return 0; // Equal

	if(a < b)
		return -1; // a is greater

	return 1; // b is greater
}
```

- To divide $n$ by $x$ and ceil the result, avoid using `ceil(1.0 * n / x)`. Instead, you can use one of the following approaches:
    1. $n / x + ((n\ \%\ x) != 0)$
    2. $(n + x - 1) / x$ -> better
	- Associated Problem: [CF2013-D2-A](https://codeforces.com/problemset/problem/2013/A)

- **Goldbach's conjecture:** Every even integer >= 4 can be expressed as the sum of 2 prime numbers.

- Average of averages can be equal to total population average iff sub groups are from same size, otherwise it will not be the same.
	- Associated Problem: [CF2078-D2-A](https://codeforces.com/contest/2078/problem/A)

