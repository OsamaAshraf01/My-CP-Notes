#DP 
- $O(n^3)$
- ABCDEF ==> (((A)((B)(C)))((D)(E))(F))
- its difficult is that you will be given the problem in bottom-up approach, and you need to think reversely and solve it top-down 
- typically, you try all different variations for last step (split point) and solve for new splitted sub-ranges. In other words, it's like you say: let's assume that this split will be the last split, how can we split the rest optimally?
- usually, your states will contain are the start and end of the current range
- usual ideas:
	- what is the best order of operations to minimize/maximize ...? 