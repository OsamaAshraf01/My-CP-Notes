#references 
In number theory, the **Calkin–Wilf tree** is a tree in which the vertices correspond one-to-one to the positive rational numbers. 
The tree is rooted at the number 1, and any rational number q expressed in simplest terms as the fraction ⁠$\frac{a}{b}$⁠ has as its two children the numbers ⁠$\frac{1}{1+\frac{1}{q}}⁠ = ⁠\frac{a}{a + b}⁠$ and $q + 1 = ⁠\frac{a + b}{b}$⁠. Every positive rational number appears exactly once in the tree.

## Some Properties of Calkin-Wilf Tree
1. Left child is smaller than parent, while the right is greater.
2. Every rational number appears in the tree exactly once
3. On the leftmost branch of the tree, all the numbers have 1 as the numerator, and on the rightmost branch of the tree, all the numbers have 1 as the denominator.
4. The numerator and denominator at each vertex are [[Co-primes]].
5. There is a hidden [[Fibonacci Sequence]], if you move R-L-R-L-R..., you will see it :)
6. If we represented any fraction as a binary sequence `b` (a 0 denoting a left turn and a 1 denoting a right turn), then the reciprocal of this fraction will be represented as `~b`.
	- example: 001 ~ $\frac{4}{3}$, and 100 ~ $\frac{3}{4}$
7. As each vertex has two children, the Calkin–Wilf tree is a binary tree. However, it is not a Binary Search tree: its in-order does not coincide with the sorted order of its vertices. However, it is closely related to a different binary search tree on the same set of vertices, the [[Stern–Brocot tree]]: the vertices at each level of the two trees coincide, and are related to each other by a [[bit-reversal permutation]]. If we applied bit-reversal on Calkin-Wilf tree, it will result in Stern-Brocot tree (BST), and vice-versa.


## Some Visuals

![[Calkin-Wilf Tree.webp]]
![[Calkin-Wilf Tree Simulation.gif]]

# Related Problems:
- [CF344-D2-C](https://codeforces.com/contest/344/problem/C)
- 