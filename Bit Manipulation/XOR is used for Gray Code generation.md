#bit_manipulation
If we looked at the bits of number $n$ and the bits of number $G(n)$. We will notice that the $i^{th}$ bit of $G(n)$ equals 1 only when the $i^{th}$ bit of $n$ equals 1 and the $(i + 1)^{th}$ bit equals 0 or the other way around ($i^{th}$ bit equals 0 and $(i + 1)^{th}$ bit equals 1). Thus, $G(n) = n \oplus (n >> 1)$.

```C++
int G (int n) {
    return n ^ (n >> 1);
}
```


## Finding inverse Gray code

Given Gray code $g$, restore the original number $n$.

```C++
int rev_g (int g) {
    int n = 0;
    for (; g; g >>= 1)
        n ^= g;
    return n;
}
```

---
- Related Article: [CP Algorithms - Gray code](https://cp-algorithms.com/algebra/gray-code.html)
- this note is related to [[Gray Code]]

