#DP #data-structures
if you use memoization and have a very deep recursion tree, this may lead to stack overflow, so we can handle this either by using table method or by using manual stack as follows:

```C++
// simple memoization code - UVA-10739
int dp(int i, int j) {
    if(i >= j)
        return 0;

    int& ret = memo[i][j];
    if(ret != -1)
        return ret;

    return ret = min({
        dp(i + 1, j - 1) + (s[i] != s[j]),
        dp(i + 1, j) + 1,
        dp(i, j - 1) + 1
    });
}
```

```C++
// using manual stack
struct state{  
    int i, j;  
    bool seen;  
    state(int i, int j): i(i), j(j), seen(false){}  
};    
stack<state> st;  
  
void push_limits() {  
    st = {};  
  
    st.emplace(0, n - 1);  
    while(!st.empty()) {  
        state cur = st.top(); st.pop();  
        auto& [i, j, seen] = cur;  
  
        if(dp[i][j] != -1)  
            continue;  
  
        if(i >= j)  // base case
            dp[i][j] = 0;  
        else if(seen) { // evaluate  
            dp[i][j] = min({  
                dp[i + 1][j - 1] + (s[i] != s[j]),  
                dp[i + 1][j] + 1,  
                dp[i][j - 1] + 1  
            });  
        } else { // recurse
            seen = true;  
            st.push(cur);  
            st.emplace(i + 1, j - 1);  
            st.emplace(i + 1, j);  
            st.emplace(i, j - 1);  
        }  
    }    
    cout << dp[0][n - 1];  
}

```