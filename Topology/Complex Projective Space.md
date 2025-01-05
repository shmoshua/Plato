#Definition #AlgebraicTopology #Topology 

> [!definition]
> The ***complex projective space*** $\mathbb{C}\mathbb{P}^n$ is given by the [[Quotient Topology|quotient space]]:$$\mathbb{C}\mathbb{P}^n:=(\mathbb{C}^{n+1} \backslash \{ 0 \}) /\{(z,\lambda z):z\in \mathbb{C}^{n+1} \backslash \{ 0 \},\lambda \in \mathbb{C}^{\times} \}$$Alternatively, it can be written as orbits$$\mathbb{C}\mathbb{P}^n:=(\mathbb{C}^{n+1} \backslash \{ 0 \}) / \mathbb{C}^\times$$given by the [[group action]] $(\lambda,z)\mapsto \lambda z$.
- **Notation**: For the quotient map $\pi:\mathbb{C}^{n+1} \backslash \{ 0 \}\to \mathbb{C}\mathbb{P}^n$, we have that $[z_{0}:\dots :z_{n}]:=\pi(z_{0},\dots,z_{n})$.

---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. $\mathbb{C}\mathbb{P}^n$ is compact Hausdorff.

> [!proof]+
> We have that:
> 1. We define: $$\Psi:(\mathbb{C}^{n+1} \backslash \{ 0 \}) / \mathbb{C}^\times\to \mathbb{C}\mathbb{P}^n,\quad \mathbb{C}^\times z\mapsto \pi(z)$$
> 	Then, 
> 2. Let $X:=\mathbb{C}^{n+1} \backslash \{ 0 \}$. To show that $\mathbb{C}\mathbb{P}^n$ is Hausdorff, by [[Proper Group Action|Theorem 1]], it suffices to show that the group action is proper, i.e. $$\rho:\mathbb{C}^\times \times X\to X\times X,\quad (\lambda,z)\mapsto (z,\lambda z)$$is [[proper map|proper]]. As $\mathbb{C}^\times \times X$ is Hausdorff and $X\times X$ is LCH, by [[Proper Map|Proposition 1]], we only need to show that for all compact $K\subseteq X\times X$, $\rho ^{-1}(K)$ is compact.