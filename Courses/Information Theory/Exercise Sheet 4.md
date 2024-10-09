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
2. Assume that it is not prefix-free, i.e. $x_{i}$ is the prefix of $x_{j}$. By the length construction, we have that $\ell_{i}\leq\ell_{j}$.  If $\ell_{i}=\ell_{j}$, then $x_{i}=x_{j}$ and wlog let $i<j$. If $\ell_{i}<\ell_{j}$, then $p_{i}>p_{j}$ and $i<j$. 

	Now, let $b_{1},\dots ,b_{\ell_{j}}\in \{ 0,1 \}$ s.t. $x_{j}=b_{1}\dots b_{\ell_{j}}$. Then, $$p_{i}\leq \text{F}_{j}-\text{F}_{i}< \sum_{k=1}^{\ell_{j}}2^{-k}\cdot b_{k}+2^{-\ell_{j}}-\sum_{k=1}^{\ell_{i}}2^{-k}\cdot b_{k}=\sum_{k=\ell_{i}+1}^{\ell_{j}}2^{-k}+2^{-\ell_{j}}=2^{-\ell_{i}}\leq p_{i}$$which is a contradiction. Hence, Shannon code is prefix free. 
	
	For the average length, we have that: $$H(X)=\sum_{i=1}^{m}p_{i}\text{log} \frac{1}{p_{i}}\leq\sum_{i=1}^{m}p_{i}\left\lceil\text{log} \frac{1}{p_{i}}\right\rceil <\sum_{i=1}^{m}p_{i}\left( \text{log} \frac{1}{p_{i}} +1\right)=H(X)+1$$

---
##### Problem 3

Let $\frac{1}{n}, \frac{1}{n}, \frac{1}{n}, \frac{1}{2n}$. Then, $$\sum_{i=1}^{n} \frac{1}{n}\ell_{i}+\frac{1}{2n}$$
	
	

