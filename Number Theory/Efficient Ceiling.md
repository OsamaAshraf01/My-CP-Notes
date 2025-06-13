#number_theory
To divide $n$ by $x$ and ceil the result, avoid using `ceil(1.0 * n / x)`. Instead, you can use one of the following approaches:
    1. $n / x + ((n\ \%\ x) != 0)$
    2. $(n + x - 1) / x$ -> better
	- Associated Problem: [CF2013-D2-A](https://codeforces.com/problemset/problem/2013/A)