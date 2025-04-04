- The best way to calculate overlap size between 2 intervals $(l_1,\ r_1)$ and $(l_2,\ r_2)$: 
    $L = max(l_1,\ l_2)$
    $R = min(r_1,\ r_2)$
    if ($R\ <\ L$)
	    return $0$; // No overlap
    else
	    return $R - L + 1$;

- <b style="color:cyan;">Kadane’s Algorithm:</b>
   1. loop over all elements
   2. add element to `max_ending_here`
   3. if `max_ending_here` > `max_so_far` --> update `max_so_far`
   4. if `max_ending_here` < 0 --> `max_ending_here` = 0

- Palindromic subsequence is common subsequence between string and its reverse. --> LPS(s) = LCS(s, reverse(s));
