#number_theory
Avoid direct comparisons when working with `double` values due to precision errors.  
Use an epsilon-based comparison like this:
```C++
int dcmp(double a, double b, double EBS = 1e-10){
	if(fabs(a - b) < EBS)
		return 0; // Equal

	if(a < b)
		return -1; // a is greater

	return 1; // b is greater
}
```





