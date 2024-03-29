#Definition #Topology 

> [!definition]
> A [[Topological Space|topological space]] is ***separable*** if it contains a countable, [[Dense Subset|dense subset]], i.e. there exists a sequence $\{ x_{i} \}_{i\geq 1}$ of elements of the space such that every nonempty open subsets of the space contains at least one element of the sequence.
---
##### Examples
> [!h] Example 1
> We have:
> 1. $\mathbb{R}^n, \mathbb{C}^n$ is separable.
---
> [!h] Example 2
> Every [[compact metric space]] is separable.

> [!proof]-
> Let $X$ be compact metric. Then, $X$ is totally bounded and let $X_{\varepsilon}$ define the $\varepsilon$-net for $\varepsilon>0$. Therefore, $Y:=\bigcup_{n=1}^{\infty}X_{1 / n}$ is a countable dense subset.
---
> [!h] Example 3
> For a compact set $K\subseteq \mathbb{R}$, $C(K)$ is separable.

> [!proof]-
> Weierstrass
---
> [!h] Example 4 (Non-separable Hilbert space)
> Let $X$ be an uncountable set and consider $L^2(X,\#)$. Then, $$\{ B_{< \sqrt{ 2 }/2}(\chi_{\{ x \}}): x\in X \}$$is an uncountable family of disjoint balls. Therefore, $L^2(X,\#)$ is not separable.
---