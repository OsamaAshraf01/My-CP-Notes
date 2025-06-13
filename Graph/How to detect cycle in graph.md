#Graph
- An efficient way for Cycle Detection using  (revise lambda expressions)
```C++
// On Matrix
bool detect_cycle(int r, int c){
	if(!valid(r, c)) return false;

	auto cycle_detected = [&](pii& p){
	    auto [r_change, c_change] = p;
	    return detect_cycle(r + r_change, c + c_change);
	};
	
	// Cycle Detection
	vector<pii> directions = {{0, 1}, {0, -1}, {1, 0}, {-1, 0}};
	return any_of(all(directions), cycle_detected);
}

// On adjList
vector<vector<int>> adjList;
vector<bool> visited;
bool dfs(int node){
	auto cycle_detected = [&](int child){
	    return !visited[child] && dfs(child);
	};
	
	// Cycle Detection
	vector<int> children = adjList[node];
	return any_of(all(children), cycle_detected);
}
```

- [[Tortoise-Hare Algorithm]]

- 