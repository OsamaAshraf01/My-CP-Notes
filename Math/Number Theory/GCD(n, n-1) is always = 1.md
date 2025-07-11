#number_theory
Proof 1:
$gcd(n, n - 1) = gcd(n - 1, n \% (n - 1))$
since $n \% (n - 1) = 1$ (because $n = 1 \cdot (n - 1) + 1$), then
$gcd(n, n - 1) = gcd(n - 1, 1) = 1$


Proof 2:
let's call $gcd(n, n - 1)$ as $g$, then g divides both $n$ and $n - 1$.
If $g$ divides $n$ and $n - 1$, then it must also divide their difference
then $g$ divides $n - (n - 1) = 1$, which means that $g = 1$.