#binary_search
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