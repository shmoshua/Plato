#Series #InformationTheory 

##### Problem 1
1. Consider the rooted binary tree constructed from the code. Then, there must exist an empty leaf, i.e. a leaf that is not a legitimate codeword. Otherwise, all the leafs are valid codewords and $\sum_{i=1}^{m}2^{-\ell_{i}}=1$. Hence, find an empty leaf. Consider its sibling. 
	1. The sibling is also an empty leaf. This is not possible by construction.
	2. The sibling is a leaf with $x\in \mathcal{X}$. Then, move $x$ up and we have a deterministically better code.
	3. The sibling is a inner node. Then, there exists a leaf $x\in \mathcal{X}$ in the offspring. Move this up to the empty leaf and we have a deterministically better code.

