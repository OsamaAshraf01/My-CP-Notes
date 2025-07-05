#number_theory 
let's assume that we have numbers from $1$ to $N$, and we are asked to calculate the frequency of some given prime factor in this range.

we can follow the following approach:
1. define `multiple` = prime
2. while `multiple` $\le$ n
	1. count += n / `multiple`
	2. multiply `multiple` by prime
3. return count

so for example if range is from 1 to 8, and we're asked about 2:
we add 8/2=4 for {2, 4, 6, 8}
we add 8/4=2 for {4, 8}
we add 8/8=1 for {8}
then the frequency of prime factor 2 in range `[1, 8]` is 7


---
## Related Problems
- [UVA-1039](https://vjudge.net/problem/UVA-10139)