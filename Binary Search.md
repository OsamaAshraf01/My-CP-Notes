- **`lower_bound` meaning:** first element that is >= target
    **`upper_bound` meaning:** first element that is > target

    if target is in the array:
		`lower_bound` returns target index 
		`upper_bound` returns target index + 1 
    else:
	    `lower_bound` returns index of first element > target
	    `upper_bound` returns index of first element > target

    **REMEMBER:** When target is not in the array, `upper_bound` and `lower_bound` will have the **same** functionality.

- If you want to search for the closest item for some target in array, check: 
    `upper_bound(all(arr), target)` and `upper_bound(all(arr), target) - 1` 
    and not 
    `lower_bound(all(arr), target)` and `lower_bound(all(arr), target) + 1`

    _Why?_ 
    let $arr = \{2,\ 4,\ 6,\ 8,\ 10\}$, and $target = 7$ 
    using `lower_bound`, we will check index 3 and 4 
    using `upper_bound`, we will check index 3 and 2 
    (for more clarification, revise previous point.

- When see pattern in array like 0, 0, 0, 1, 1, 1, 1 or 1, 1, 0, 0, 0 -(i.e. you need to find the last 0/first 0/last 1/first 1) -> think in binary search with a check function.
	- usually we binary search for $ans$ (trying different values of ans)
	- you may think with "at least" and "at most" to make the function in the previous format. for example, if we are trying to maximize $ans$:
		- if our check for $x$ is $f(x)=ans$, we may get : 1 0 0 0 0 1 0 0 0 0 0
		- but if our check for $x$ is $f(x) \ge ans$, we get:  1 1 1 1 1 1 0 0 0 0 0

- Naturally sorted search spaces:
	- integer numbers
	- x-axis / y-axis
	- dictionaries

- **bool std::binary_search(It first, It last, T target)**: return a boolean value indicated if target exists in the given range
- **pair<It, It> std:equal_range(It first, It last, T target)**: returns 2 iterators indicating the begin and of the range that all its values = target. for example: {1, 3, 4, 4, 4, 4, 6}, target=4 -> {2, 6}
	- if item not in the array the returned pair will not construct a valid range like {0, -1} or {5, 4}
	- it's equivalent to {lower_bound, upper_bound} 
