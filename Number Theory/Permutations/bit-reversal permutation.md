#number_theory #permutations
In applied mathematics, a bit-reversal permutation is a permutation of a sequence of n items, where $n = 2^k$ is a power of two. It is defined by indexing the elements of the sequence by the numbers from 0 to n − 1, representing each of these numbers by its binary representation (padded to have length exactly k), and mapping each item to the item whose representation has the ___same bits in the reversed order___.

Repeating the same permutation twice returns to the original ordering on the items, so the [[bit reversal permutation is an involution]].

This permutation can be applied to any sequence in linear time while performing only simple index calculations. It has applications in the [[generation of low-discrepancy sequences]] and in the [[evaluation of Fast Fourier Transforms]].

# Example
Consider the sequence of eight letters _abcdefgh_. Their indexes are the binary numbers 
$\{000, 001, 010, 011, 100, 101, 110, 111\}$, 
which when reversed become 
$\{000, 100, 010, 110, 001, 101, 011, 111\}$. 
Thus, the letter _a_ in position 000 is mapped to the same position (000), the letter _b_ in position 001 is mapped to the fifth position (the one numbered 100), etc., giving the new sequence _aecgbfdh_. Repeating the same permutation on this new sequence returns to the starting sequence.

when k = 4 => permutation length = $2^4 = 16$:
0 8 4 12 2 10 6 14 1 9 5 13 3 11 7 15