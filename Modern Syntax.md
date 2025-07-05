- To loop over a map to extract keys or values:
   `for(auto const &[k, v] : mp)`

- To get the minimum of more than one number use: `min({a, b, c, ...});`

- Use **`std::any_of(InputIt first, InputIt last, UnaryPred p)`** to to iterate efficiently over some iterable object (vector, list, array, etc.). It will return `true` if any value satisfy the Unary Predicate `p`.
	- **_Unary Predicate:_** a lambda function that takes **one** argument and returns a bool value.

    - Example:
```C++
// Example of Unary Predicate - Revise Lambda Functions
auto p = [&](int x){return x == 5;}
```

- To get the max element in `set` or `multiset`, use `*s.rbegin()`

- to loop over set while you are erasing from it: 
```C++
set<int> s; 
for(auto it = s.begin(); it != s.end(); ) { 
	if(some_condition) { 
		ans[*it] = i + 1; c++; 
		it = s.erase(it); // erase(iterator) returns next valid iterator
	} else { 
		it++; 
	} 
}
```