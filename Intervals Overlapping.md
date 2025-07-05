The best way to calculate overlap size between 2 intervals $(l_1,\ r_1)$ and $(l_2,\ r_2)$: 

$L = max(l_1,\ l_2)$
$R = min(r_1,\ r_2)$
if ($R\ <\ L$)
	return $0$; // No overlap
else
	return $R - L + 1$;
