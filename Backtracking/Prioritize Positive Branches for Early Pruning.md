#Backtracking

When using backtracking with pruning, prioritize exploring the **positive branches** first — those that actively **do work** (e.g., take an element, set a color, make a move, etc.). These paths are more likely to reach complete or partial solutions quickly, which in turn enables **earlier and more effective pruning** of invalid or suboptimal paths.

In contrast, the **negative branch** is the one that **does not perform any action** (e.g., skip, ignore), and typically contributes less to pruning early on.

> **Tip:** The **order** of recursive calls significantly affects performance when pruning is involved. Explore the more promising branches first to maximize pruning potential.
