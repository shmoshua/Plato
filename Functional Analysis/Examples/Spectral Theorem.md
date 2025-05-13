#Theorem #FunctionalAnalysis 

##### Symmetric Matrix
> [!lemma] Theorem (Symmetric Matrix)
> Let $A\in \mathbb{R}^{n,n}$ be a symmetric matrix. Then,
> 1. $A$ admits a decomposition $A=V\Lambda V^\top$ where $\Lambda\in \mathbb{R}^{n,n}$ is diagonal and $V\in\mathbb{R}^{n,n}$.
> 2. the columns of $V$ form an ONB.
> 3. $\Lambda=\text{diag}(\lambda_{1}(A),\dots,\lambda_{n}(A))$

^9a1dbe

---
> [!lemma] Theorem (Courant-Fischer)
> Let $A\in \mathbb{R}^{n,n}$ be symmetric with $\lambda_{1}\leq\lambda_{2}\leq\dots\leq \lambda_{n}$. Then,
> 1. $$\lambda_{i}=\min_{W\leq \mathbb{R}^n:\text{dim}(W)=i}\max_{0\neq x\in W} \frac{x^\top Ax}{x^\top x}$$
> 2. $$\lambda_{i}=\max_{W\leq \mathbb{R}^n:\text{dim}(W)=n-i+1}\min_{0\neq x\in W} \frac{x^\top Ax}{x^\top x}$$

^9514ed

> [!proof]-
> We have that:
> 1. Let $W:=\braket{ v_{1} , \dots,v_{i} }$ where $A=V\Lambda V^\top$ and $V=(v_{1},\dots,v_{n})$. Now, let $x\in W$ and assume wlog $\|x\|_{2}=1$. Then, $x=\sum_{j=1}^{i}c_{j}v_{j}$ for some $c\in \mathbb{R}^i$ and $\|c\|_{2}=1$. Now, $$x^\top Ax=x^\top V\Lambda V^\top x=\sum_{j=1}^{i}\lambda_{j}c_{j}^{2}\leq \lambda_{i}\|c\|^{2}_{2}=\lambda_{i}$$Therefore, $$\min_{W\leq \mathbb{R}^n:\text{dim}(W)=i}\max_{0\neq x\in W} \frac{x^\top Ax}{x^\top x}\leq \lambda_{i}$$
---
##### Compact, Self-adjoint Operators
> [!lemma] Theorem
> Let $T\in \mathcal{ B}(\mathcal{H},\mathcal{H})$ be a [[Compact Operator|compact]], [[Adjoint Linear Map|self-adjoint]] operator, where $\mathcal{H}$ is a [[Hilbert Space|Hilbert space]]. Then, 
> 1. $\mathcal{H}$ has an orthonormal basis consisting of eigenvalues $\lambda$ of $T$. 
> 2. If $\lambda \neq 0$, then the corresponding eigenbasis has a finite dimension, i.e. $\text{dim} \mathcal{H}_{\lambda}<+\infty$.
> 3. All eigenvalues are real.
> 4. For all $\varepsilon>0$: $$\{ \lambda\in \mathbb{R}:\left| \lambda \right|\geq \varepsilon,\text{dim}\mathcal{H}_{\lambda}>0  \}$$is finite.

---
