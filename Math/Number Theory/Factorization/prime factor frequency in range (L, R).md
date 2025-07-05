#number_theory 
this is a generalization of the previous note: [[prime factor frequency in range (1, n)]]

for a given prime factor x, the frequency of x in range `[L, R]` is frequency in range `[1, R]` - frequency in range `[1, L-1]`


Example:
frequency of 2 in range `[8, 16]`:
+16/2=8  {2, 4, 6, 8, 10, 12, 14, 16}
+16/4=4  {4, 8, 12, 16}
+16/8=2  {8, 16}
+16/16=1 {16}

-7/2=3   {2, 4, 6}
-7/4=1   {4}

this means that the contribution is as follows:
2, 4, 6 ==> 0
10, 14 ==> 1
12 ==> 2
8 ==> 3
16 ==> 4

then, the total frequency of prime factor 2 in range `[8, 16]` is 11 (8, 10, 12, 14)