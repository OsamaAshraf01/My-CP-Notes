#bit_manipulation
Useful Blog: [Some equations using bitwise operators](https://codeforces.com/blog/entry/94470)

## Addition
- $a + b = (a$ & $b) + (a\ |\ b)$
- $a + b = a ⊕ b + 2(a\ \&\ b)$
- Sum without carry propagation = $a$ ^ $b$   (Bitwise XOR)

## Subtraction
- $a - b = (a ⊕ (a\ \&\ b))-((a\ |\ b) ⊕ a)$
- $a - b = ((a\ |\ b) ⊕ b)-((a\ |\ b) ⊕ a)$
- $a - b = (a ⊕ (a\ \&\ b))-(b ⊕ (a\ \&\ b))$
- $a - b = ((a\ |\ b) ⊕ b) - (b ⊕ (a\ \&\ b))$
