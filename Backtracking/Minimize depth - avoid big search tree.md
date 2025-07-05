#Backtracking

Instead of iterating over **all nodes** and trying decisions at each one, you can **skip nodes that have only one valid decision**. Focus instead on jumping directly to the **next node with multiple decision options**.

This reduces unnecessary recursion and speeds up the search, since nodes with only one path contribute no branching and thus no meaningful choices.

> **Tip:** Preprocess or track nodes with multiple choices to guide the recursion more efficiently.
