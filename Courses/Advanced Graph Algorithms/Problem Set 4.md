#Definition #AGAO 

#### Exercise 1
Let $M\in \mathbb{R}^{n,n}$ be a symmetric matrix. Then, $Z=\sum_{i,\lambda_{i}\neq 0}^{}\lambda_{i}^{-1}v_{i}v_{i}^\top$ where $\lambda_{i}$ is the $i$-th eigenvalue of $M$ and $v_{i}$ is a corresponding eigenvector s.t. $\{ v_{i} \}_{i}$ form an ONB.
1. The symmetry follows from the symmetry of $v_{i}v_{i}^\top$ for all $i$.
2. Let $r:= \text{rk}(M)$. Recall that $V_{0}:=\{ v_{r+1},\dots,v_{n} \}$ forms a basis for $\text{ker }M$. Hence, we have that for any $v_{i}\in V_{0}$, we have that $Mv_{i}=0$ and $\lambda_{i}=0$. Therefore, for any $v\in \text{ker } M$, $\braket{ v , v_{i} } =0$ for any $i\leq r$. It follows that for any $v\in \text{ker } M$, $$Zv=\sum_{i,\lambda_{i}\neq 0}^{}\lambda_{i}^{-1}v_{i}\underbrace{ v_{i}^\top v }_{ =0 }= 0$$
3. From above, we know that $\{ v_{1},\dots,v_{r} \}$ span $(\text{ker }M)^{{\bot}}$ as $\{ v_{1} \}_{i}$ form an ONB. Hence, for any $v=\sum_{i\leq r}^{}a_{i}v_{i}\in (\text{ker }M)^{\bot}$, we have that: $$M$$