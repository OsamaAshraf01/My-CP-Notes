#bit_manipulation
while you are using left shifting operator `<<` be careful that normal one is considered normal integer (max 32 bits) and if you need more than 32 bits for shifting use `1LL << shifting`.

revise my solutions for problem [CF507-D2-C](http://codeforces.com/contest/507/problem/C):
- [Wrong Answer 1](https://codeforces.com/contest/507/submission/326063654)
- [Wrong Answer 2](https://codeforces.com/contest/507/submission/326063787)
- [Accepted (after using ll shifting)](https://codeforces.com/contest/507/submission/326063813)