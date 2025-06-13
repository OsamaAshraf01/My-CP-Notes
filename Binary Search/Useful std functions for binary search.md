#binary_search
- **bool std::binary_search(It first, It last, T target)**: return a boolean value indicated if target exists in the given range.

- **pair<It, It> std:equal_range(It first, It last, T target)**: returns 2 iterators indicating the begin and of the range that all its values = target. for example: {1, 3, 4, 4, 4, 4, 6}, target=4 -> {2, 6}
	- if item not in the array the returned pair will not construct a valid range like {0, -1} or {5, 4}
	- it's equivalent to {lower_bound, upper_bound} 
