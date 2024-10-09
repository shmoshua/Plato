#Series #InformationTheory 

##### Problem 1
1. Consider the rooted binary tree constructed from the code. Then, there must exist an empty leaf, i.e. a leaf that is not a legitimate codeword. Otherwise, all the leafs are valid codewords and $\sum_{i=1}^{m}2^{-\ell_{i}}=1$. Hence, find an empty leaf. Consider its sibling. 
	1. The sibling is also an empty leaf. This is not possible by construction.
	2. The sibling $v$ is a leaf with $x\in \mathcal{X}$. Then, move $x$ up and we have a deterministically better code.
	3. The sibling $v$ is not a leaf. Then, there exists a non-empty leaf in the offspring of $v$. Move this up to the empty leaf and we have a deterministically better code.
2. Yes.
---
##### Problem 2
We have:
1. the $\text{F}_{i}$ are given by $(0,0.5,0.75,0.875)$ and then in binary, we have that $(0,0.1,0.11,0.111)$. Therefore, the codewords are $(0,10,110,111)$.
2. Assume that it is not prefix-free, i.e. $x_{i}$ is the prefix of $x_{j}$ then, by the length construction, we have that $\ell_{i}<\ell_{j}$ and $p_{j}<p_{i}$. Let $b_{1},\dots ,b_{\ell_{j}}\in \{ 0,1 \}$ s.t. $x_{j}=b_{1}\dots b_{\ell_{j}}$. 
	
   
   Then, $$$$
	$$$$
1. $$\sum_{i=1}^{\ell_{i}}2^{-i}\cdot b_{i}+\varepsilon_{i}+\sum_{k=i}^{j-1}p_{k}=\text{F}_{i}+\sum_{k=i}^{j-1}p_{k}=\sum_{k=1}^{i-1}p_{k}+\sum_{k=i}^{j-1}p_{k}=\sum_{k=1}^{j-1}p_{k}=\text{F}_{j}=\sum_{i=1}^{\ell_{j}}2^{-i}\cdot b_{i}+\varepsilon_{j}$$where $\varepsilon_{k}<2^{-\ell_{k}}$. Hence, $$2^{-\ell_{i}}=\sum_{k=\ell_{i}+1}^{\ell_{j}}2^{-k}+2^{-\ell_{j}}>\sum_{k=\ell_{i}+1}^{\ell_{j}}2^{-k}\cdot b_{k}+\varepsilon_{j}=\sum_{k=i}^{\ell_{i}}p_{k }+\varepsilon_{i}$$

