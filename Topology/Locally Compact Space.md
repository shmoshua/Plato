#Definition #Topology 

> [!definition]
> A [[topological space]] $X$ is ***locally compact***, if every $x\in X$ has a [[Local Base of Topology|local base]] of [[Compact Space|compact]] sets.
---
##### Properties
> [!lemma] Proposition 1
> For a locally compact topological space $X$, every neighborhood $U$ of $x$ contains a compact neighborhood.

> [!proof]-
> Let $K$ be the compact neighborhood of $x$. Then, $U\cap K$
> Then, $U\cap V\subseteq U$ and $\overline{U\cap V}\subseteq \overline{V}$ which is compact.
---
##### Examples
> [!h] Example 1
> We have: 
> 1. Any discrete space $X$ is locally compact.
> 2. $\mathbb{R}^n$ is locally compact.
> 3. Any [[topological manifold]] is locally compact.
---
> [!h] Example 2
> Any [[compact space]] $X$ is locally compact.

> [!proof]-
> Let $x\in X$ and $U\subseteq X$ be an open neighborhood. Then, by [[Compact Space|Compact Hausdorff Lemma 2]], there exists a relatively compact set $x\in V$ s.t. $\overline{V}\subseteq U$. Therefore, $X$ is locally compact.
---