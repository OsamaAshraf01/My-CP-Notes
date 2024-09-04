1. To loop over a map to extract keys or values:
	```for(auto const &[k, v] : mp)```

2. Don't use ```INT_MAX``` if you are going to add to this variable (as this will lead to overflow).

3. Don't define ```memo``` in the function as this will lead to stack overflow.

4. in DP, initialize memory(i.e. ```clr```) for each test case.

5. if the string is palindrome then it contains 2 adjacent letters that are the same or there are two letters separated by another which are the same. <br>
**Some usage:** if there aren't any 2 equal adjacent letters or separated by char, then this string is not palindrome and all its substrings(with size $\ge$ 2) are not palindromes.

6. <b style="color:cyan;">Kadane’s Algorithm:</b> 
	1. loop over all elements
	2. add element to ```max_ending_here```
	3. if ```max_ending_here``` > ```max_so_far``` --> update ```max_so_far```
	4. if ```max_ending_here``` < 0 --> ```max_ending_here``` = 0

7. $(2ab + 2bc + 2ca) = (a + b + c)^2 - (a^2 + b^2 + c^2)$ <br>
   Example: <br>
   for $n$ numbers: <br>
   $(a - b)^2 + (a - c)^2 + (b - c)^2 + ...$ <br>
   $= (n - 1)(a^2 + b^2 + c^2 + ...) - (2ab + 2bc + 2ca + ...)$ <br>
    $= (n)(a^2 + b^2 + c^2 + ...) - (a + b + c + ...)^2$

8. Read Problem statement carefully, take care from "pair", "at most", "at least", "once", ....


9. if you have the bitwise AND $(\&)$ of two elements, you can factorize it to $(x, x|y)$


10. if you have a global vector that used in multiple testcases, DO NOT just resize it in each testcase as this will lead to a $RTE$ (it is only resized not cleared). You can either clear it before resizing or just reinitialize it with '=' operator.

11. <b style="color:cyan;">Fermat's Little Theorem:</b> if $$ is a prime number and $a$ is not divisible by $p$ then, <br>
    $a^p\ \%\ p = a\ \%\ p$ <br>
    and $a^{p - 1}\ \%\ p = 1$ <br>
    and $a^{-1}\ \%\ p = a^{p - 2}\ \%\ p$ ----> important for factions and Combinatinos

    **Correction:** In the case of fractions, Not if p is prime, but if and only if gcd(a,p)=1. In other words, the denominator must be relatively prime to the modulus.

12. Modulus meaning with fractions:

    when you say: $(a/b)\%n$, you're referring to a number $x$ such that $(b*x) \% n ≡ a \% n$.
 

13. $a + b = (a\ \&\ b) + (a\ |\ b)$


14. to get the minimum of more than one number use: ```min({a, b, c, ...});```


15. If you want to search for the closest item for some target in array, check: <br>
    ```upper_bound(all(arr), target)``` and ```upper_bound(all(arr), target) - 1``` <br>
    and not <br>
    ```lower_bound(all(arr), target)``` and ```lower_bound(all(arr), target) + 1```
    
    *Why?* <br>
    let $arr = \{2,\ 4,\ 6,\ 8,\ 10\}$, and $target = 7$ <br>
    using ```lower_bound```, we will check index 3 and 4 <br>
    using ```upper_bound```, we will check index 3 and 2 <br>
    (for more clarification, revise point 16)


16. lower_bound meaning: first element that is >= target <br>
    upper_bound meaning: first element that is > target <br>

    if target in arr:<br>
	```lower_bound``` -> target_index <br>
	```upper_bound``` -> target_index + 1 <br>
    else:<br>
	```lower_bound``` -> index of first element > target<br>
	```upper_bound``` -> index of first element > target<br>

    **REMEBER:** When target is not in arr, upper_bound and lower_bound will have the **same** functionality.


17. The best way to caluclate overlap size between 2 intervals $(l1,\ r1)$ and $(l2,\ r2)$: <br>
    $L = max(l1,\ l2)$ <br>
	$R = min(r1,\ r2)$ <br>
    if ($R\ <\ L$) return $0$; <br>
	else return $R - L + 1$;


18. Instead of using ```map<pii, int>``` with complexity $O(log(n))$, use ```vector<vector<int>>``` with a pre-customed size to reduce complexity to $O(1)$.
	

19. The $MEX$ of $N$ numbers cannot exceed $N$.
 

20. with %, Be careful from:
    - subtraction: $\quad (a - b)\ \%\ M$  ---->  $(a - b + M)\ \%\ M$
    - division: $\quad (a / b)\ \%\ M$  ---->  $((a\ \%\ M)*$ ```fast_power(b, M - 2, M)```$)\ \%\ M$
    - multiplication: $\quad (a * b)\ \%\ M$  ---->  $((a\ \%\ M) * (b\ \%\ M))\ \%\ M$


21. $\sum_{i=0}^{n}{\sum_{j=i+1}^{n}{(a_i*a_j)}}$ <br><br>
$= \sum_{i=0}^{n}{(a_i * \sum_{j=i+1}^{n}{a_j})}$ <br><br>
$= {(\sum_{i=0}^{n}{a_i})}^2 - \sum_{j=0}^{n}{(a_j^2)}$
- revise point **7**


22. $(2^{32} - 1)$ is ```UINT_MAX``` not ```INT_MAX```


23. PLEASE, use ```long long``` if you are not sure, memory is not paid :/



