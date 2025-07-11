#doubles 
while trying to solve [UVA-10218](https://vjudge.net/problem/UVA-10218), it was surprising to find someone who solved this problem using the normal iterative approach(using [[Binomial Distribution]]), and here's why his solution is correct:
- He used `long double` to store very big values of combinations (e.g. $\binom{100}{50}$)
- but this will lead to precision errors (e.g. $10^{30}$ will be $1000000000000000000024696061952$)
- here is the trick, that's right that there will be precision error, *but* this value will be multiplied by very small values ($p^k$ and $p^{n - k}$) and finally it will be a probability $\le 1$. So this error will have a very diminishing effect :)
- So the lesson is when you are tolerant with some small precision errors, go with doubles to store big numbers but still **be careful**.