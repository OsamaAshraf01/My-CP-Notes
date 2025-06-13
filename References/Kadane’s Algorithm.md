#references
### Usage
Kadane's Algorithm ==efficiently solves the Maximum Subarray Sum Problem==. It finds the contiguous subarray within a one-dimensional array of numbers that has the largest sum. The algorithm achieves this with a linear time complexity ($O(n)$), making it significantly faster than brute-force approaches that have quadratic time complexity ($O(n^2)$).

### Code

```C++
int maxSubarraySum(vector<int> &arr) {
    int global_max = arr[0];
    int local_max = arr[0];

    for (int i = 1; i < arr.size(); i++) {
      
        // Find the maximum sum ending at index i by either extending 
        // the maximum sum subarray ending at index i - 1 or by
        // starting a new subarray from index i
        local_max = max(local_max + arr[i], arr[i]);
      
        // Update res if maximum subarray sum ending at index i > res
        global_max = max(global_max, local_max);
    }
    return global_max;
}
```
