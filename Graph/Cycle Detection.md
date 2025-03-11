- An efficient way for Cycle Detection using DFS
```C++
// On Matrix
bool dfs(int r, int c){
	auto cycle_detected = [&](pii& p){
	    auto [x, y] = p;
	    return valid(i, j) && dfs(i + x, j + y);
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

- Tortoise-Hare Algorithm

- 