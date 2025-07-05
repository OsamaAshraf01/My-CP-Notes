#bit_manipulation
$x = x\ \&\ (x\ |\ y)$, i.e. if you have the bitwise AND (&) of two elements as value, you can factorize it to $(x, x\ |\ y)$

e.g. $9 = 9\ \& \ (9\ |\ x)$ and with different values of $x$, you can get different pairs that their bitwise AND is $9$
when $x = 3$ -> $9\ |\ 3 = 11$, then $9 = 9\ \&\ 11$
in the same way, $9 = 9\ \&\ 9$(trivial) $= 9\ \&\ 11 = 9\ \&\ 13 = 9\ \&\ 15$