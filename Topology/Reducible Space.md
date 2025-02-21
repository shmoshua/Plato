#Definition #AlgebraicGeometry 

> [!definition]
> Let $X$ be a non-empty [[topological space]].
> 1. $X$ is ***reducible*** if $X=X_{1}\cup X_{2}$ for two proper closed subsets $X_{1},X_{2}\subseteq X$.
> 2. $X$ is ***irreducible***, if it is not reducible.

^30a488

- **Remark**: Conventionally, $\varnothing$ is reducible. ^02173d

---
> [!lemma] Proposition 1
> Let $X$ be an irreducible space.
> 1. if $X$ is Hausdorff then $X$ has only one element.
> 2. $X$ is [[Connected Space|connected]].

^2239df

> [!proof]-
> We have:
> 1. if $p_{1},p_{2}\in X$ with $p_{1}\neq p_{2}$, then by Hausdorff, we have $U,V$ open s.t. $p_{1}\in U$ and $p_{2}\in V$. Then, $$X=X \backslash U\cup X \backslash V$$which is reducible.
> 2. if $X$ is not connected, i.e. if there exists two disjoint closed $C_{1},C_{2}$ with $X=C_{1}\cup C_{2}$, s.t. $C_{1},C_{2}\subsetneq X$, then $X$ is reducible.

^055bf8

---
##### Example
> [!h] Example 1
> We have that:
> 1. $\mathbb{A}^1$ is irreducible with [[Zariski topology]] as the proper closed subsets are finite.
> 2. A disconnected space is always reducible

^c2e554

---
> [!h] Example 2 
> We have that:
> 1. $V(xy)\subseteq \mathbb{A}^2$ is a reducible but not disconnected space.
> 2. $V(x(x-1))\subseteq \mathbb{A}^2$ is a disconnected and reducible space.

^043276

---
