#bit_manipulation
- $x \& (x - 1)$ -> first 1 bit from right removed
- $x \& ~(x - 1)$ -> only first 1 bit from right kept

```C++
int count_one_bits(int n){ // O(one bits count)
	int ans = 0;
	while(n){
		ans++;
		n &= (n - 1) // remove rightmost 1 bit
	}
	return ans;
}
```