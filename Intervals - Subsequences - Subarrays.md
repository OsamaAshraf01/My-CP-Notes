- The best way to calculate overlap size between 2 intervals $(l1,\ r1)$ and $(l2,\ r2)$: 
    $L = max(l1,\ l2)$
    $R = min(r1,\ r2)$
    if ($R\ <\ L$)
	    return $0$; // No overlap
    else
	    return $R - L + 1$;

- <b style="color:cyan;">Kadane’s Algorithm:</b>
   1. loop over all elements
   2. add element to `max_ending_here`
   3. if `max_ending_here` > `max_so_far` --> update `max_so_far`
   4. if `max_ending_here` < 0 --> `max_ending_here` = 0

