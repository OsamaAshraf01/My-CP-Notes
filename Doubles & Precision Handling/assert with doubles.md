#doubles
Don't use direct comparison, always use `dcmp`. Revise [[Safe Doubles Comparison]]

Example:
`assert(dcmp(x, 1) != -1)` instead of `assert(x <= 1)`.