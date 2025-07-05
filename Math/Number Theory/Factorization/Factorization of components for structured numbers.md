#number_theory 
Core Problem: Direct factorization of large structured numbers → **TLE**
Key Insight: Multiplicative Property: **If `a|A` and `b|B`, then `(a×b)|(A×B)`**
Core Idea: Instead of factoring `A×B` directly, factor `A` and `B` separately, then combine.

If you need to factorize a very large number (typically > $10^{16}$) and know that it's composed of two smaller components (like perfect numbers), then it's better to factorize each component separately and combine the two sets using dot-product.

Direct factorization: $O(\sqrt{n}) = O(\sqrt{ab})$
using above technique: $O(\sqrt{a} + \sqrt{b} + f_a * f_b)$ where $f_a$ is the count of factors of a

---
Related Problem: 
[TLE Solution](https://vjudge.net/solution/61383495/h0ODvTvaTfAc6kxbnfZF)  
This version tries to factorize $n$ directly each time — which is slow as $n > 2 \times 10^{18}$

[AC Solution](https://vjudge.net/solution/61383010/EXk6wVTKvJwBYXsYyJZ8)  
This version uses the factorization of components $a$ and $b$ and combines them efficiently.
