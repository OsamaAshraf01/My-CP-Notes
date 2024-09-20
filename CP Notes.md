# My CP Notes

1. To loop over a map to extract keys or values:
   `for(auto const &[k, v] : mp)`

2. Don't use `INT_MAX` if you are going to add to this variable (as this will lead to overflow).

3. Don't define `memo` in the function as this will lead to stack overflow.

4. in DP, initialize memory(i.e. `clr`) for each test case.

5. if the string is palindrome then it contains 2 adjacent letters that are the same or there are two letters separated by another which are the same. \
   **Some usage:** if there aren't any 2 equal adjacent letters or separated by char, then this string is not palindrome and all its substrings(with size $\ge$ 2) are not palindromes.

6. <b style="color:cyan;">Kadane’s Algorithm:</b>

   1. loop over all elements
   2. add element to `max_ending_here`
   3. if `max_ending_here` > `max_so_far` --> update `max_so_far`
   4. if `max_ending_here` < 0 --> `max_ending_here` = 0

7. $(2ab + 2bc + 2ca) = (a + b + c)^2 - (a^2 + b^2 + c^2)$ \
   Example: \
   for $n$ numbers: \
   $(a - b)^2 + (a - c)^2 + (b - c)^2 + ...$ \
   $= (n - 1)(a^2 + b^2 + c^2 + ...) - (2ab + 2bc + 2ca + ...)$ \
    $= (n)(a^2 + b^2 + c^2 + ...) - (a + b + c + ...)^2$

8. Read Problem statement carefully, take care from "pair", "at most", "at least", "once", ....

9. if you have the bitwise AND $(\&)$ of two elements, you can factorize it to $(x, x|y)$

10. if you have a global vector that used in multiple testacies, DO NOT just resize it in each test case as this will lead to a $RTE$ (it is only resized not cleared). You can either clear it before resizing or just reinitialize it with '=' operator.

11. <b style="color:cyan;">Fermat's Little Theorem:</b> if $$ is a prime number and $a$ is not divisible by $p$ then, \
    $a^p\ \%\ p = a\ \%\ p$ \
    and $a^{p - 1}\ \%\ p = 1$ \
    and $a^{-1}\ \%\ p = a^{p - 2}\ \%\ p$ ----> important for factions and Combinations

    **Correction:** In the case of fractions, Not if p is prime, but if and only if gcd(a,p)=1. In other words, the denominator must be relatively prime to the modulus.

12. Modulus meaning with fractions:

    when you say: $(a/b)\%n$, you're referring to a number $x$ such that $(b*x) \% n ≡ a \% n$.

13. $a + b = (a\ \&\ b) + (a\ |\ b)$

14. to get the minimum of more than one number use: `min({a, b, c, ...});`

15. If you want to search for the closest item for some target in array, check: \
    `upper_bound(all(arr), target)` and `upper_bound(all(arr), target) - 1` \
    and not \
    `lower_bound(all(arr), target)` and `lower_bound(all(arr), target) + 1`

    _Why?_ \
    let $arr = \{2,\ 4,\ 6,\ 8,\ 10\}$, and $target = 7$ \
    using `lower_bound`, we will check index 3 and 4 \
    using `upper_bound`, we will check index 3 and 2 \
    (for more clarification, revise point 16)

16. lower_bound meaning: first element that is >= target \
     upper_bound meaning: first element that is > target \

    if target in arr:\
    `lower_bound` -> target_index \
    `upper_bound` -> target_index + 1 \
     else:\
    `lower_bound` -> index of first element > target\
    `upper_bound` -> index of first element > target\

    **REMEMBER:** When target is not in arr, upper_bound and lower_bound will have the **same** functionality.

17. The best way to calculate overlap size between 2 intervals $(l1,\ r1)$ and $(l2,\ r2)$: \
     $L = max(l1,\ l2)$ \
    $R = min(r1,\ r2)$ \
     if ($R\ <\ L$) return $0$; \
    else return $R - L + 1$;

18. Instead of using `map<pii, int>` with complexity $O(log(n))$, use `vector<vector<int>>` with a pre-defined size to reduce complexity to $O(1)$.

19. The $MEX$ of $N$ numbers cannot exceed $N$.

20. with %, Be careful from:

    - subtraction: $\quad (a - b)\ \%\ M$ ----> $(a - b + M)\ \%\ M$
    - division: $\quad (a / b)\ \%\ M$ ----> $((a\ \%\ M)*$ `fast_power(b, M - 2, M)`$)\ \%\ M$
    - multiplication: $\quad (a * b)\ \%\ M$ ----> $((a\ \%\ M) * (b\ \%\ M))\ \%\ M$

21. $\sum_{i=0}^{n}{\sum_{j=i+1}^{n}{(a_i*a_j)}}$ \
    \
    $= \sum_{i=0}^{n}{(a_i * \sum_{j=i+1}^{n}{a_j})}$ \
    \
    $= {(\sum_{i=0}^{n}{a_i})}^2 - \sum_{j=0}^{n}{(a_j^2)}$ - **For more clarification**, revise point **7**

22. $(2^{32} - 1)$ is `UINT_MAX` not `INT_MAX`

23. PLEASE, use `long long` if you are not sure, memory is not paid :/

24. - you can use **`std::any_of(InputIt first, InputIt last, UnaryPred p)`** to
      to iterate efficiently over some iterable object (vector, list, array, etc.)
      it will return `true` if any value satisfy the Unary Predicate `p`.
    - **_Unary Predicate:_** a lambda function that takes **one** argument and returns a bool value.

      - Example:

        ```C++
        auto p = [&](int x){return x == 5;}
        ```

    - Example of `find_of`:

      ```C++
      auto cycle_detected = [&](pii& p){
          auto [x, y] = p;
          return valid(i, j) && dfs(i + x, j + y);
      };

      // Cycle Detection
      vector<pii> directions = {{0, 1}, {0, -1}, {1, 0}, {-1, 0}};
      return any_of(all(directions), cycle_detected);
      ```

25. **More on Lambda Expressions**:

    - Pass variable by value/reference:

    ```C++
    vector<int> v = {1, 2, 3, 4};
    int val = 10;

    // [] capture clause

    // 1. pass outer variables as CONST VALUE
    auto add_val = [val](vector<int> &v){
        for(int& item : v)
            item += val;

        // val++ -> Error
    }
    add_val(v); // add 10 tp each element in v
    ```

    ```C++
    // 2. pass outer variables by VALUE
    auto add_val = [val](vector<int> &v) mutable{
        val += 5;
        for(int& item : v)
            item += val;
    }
    add_val(v); // add 15 to each element in v
    cout << val; // 10
    ```

    ```C++
    // 3. pass outer variables by REFERENCE
    auto add_val = [&val](vector<int> &v) {
        val += 5;
        for(int& item : v)
            item += val;
    }
    add_val(v); // add 15 to each element in v
    cout << val; // 15

    ```

    - Passing all variables by value/reference:

    ```C++
    // To pass all variables by VALUE
    auto add_val = [=](vector<int> &v) {
        val += 5;
        for(int& item : v)
            item += val;
    }
    ```

    ```C++
    // To pass all variables by REFERENCE
    auto add_val = [&](vector<int> &v) {
        val += 5;
        for(int& item : v)
            item += val;
    }
    ```

    ```C++
    [=, &b] // means all variables will be passed by value except for b, it will be passed by reference
    [&, b] // means all variables will be passed by reference except for b, it will be passed by value
    ```

    - **NOTE:**: Static variables are visible inside the lambda function

26. To compare 2 double numbers, don't use the direct comparison. Use the following approach:

    ```C++
    int dcmp(double a, double b, double EBS = 1e-10){
        if(fabs(a - b) < EBS)
            return 0; // Equal

        if(a < b)
            return -1; // a is greater

        return 1; // b is greater
    }

    ```

27. To divide `n` by `x` and ceil the result, avoid using `ceil(0.1 * n / x)`. Instead, you can use one of the following approaches:

    1. `n / x + (n % x != 0)`
    2. `(n + x - 1) / x`

    **Associated problems:**

    ![2013](https://img.shields.io/badge/2013-A-green?labelColor=blue&style=flat)
