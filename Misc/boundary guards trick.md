to safely access `arr[i-1]` and `arr[i+1]` without need for special handling, you can add guards at the boundaries of the array with proper dummy value. 

```C++
vector<int> arr(n + 2); 

arr[0] = arr[n + 1] = INT_MIN // Guards 

lp(i, n) cin >> arr[i + 1];
```


## Example

```C++
// without guards
lp(i, n) {
	if(i == 0)
		// do special logic or simply skip
	else if(arr[i] > arr[i - 1])
		// do some logic
}


// with gurads of proper values
lpi(i, 1, n) {
	if(arr[i] > arr[i - 1])
		// do unified logic
}
```
