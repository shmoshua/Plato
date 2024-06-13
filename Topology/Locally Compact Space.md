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
##### Non-Examples
> [!h] Non-Example 1 (L2 Space)
> Let $X=L^2([0,1])$. Then,
> 1. $B_{\leq\varepsilon}(f)$ is not compact for all $f\in X$.
> 2. $X$ is not locally compact.

> [!proof]-
> We have:
> 1. Assume $B:=B_{\leq \varepsilon}(f)$ is compact. As $B$ is metric, it is then sequentially compact. Let $f_{n}\in L^2([0,1])$ where $f_{n}(x)=\exp(2\pi i nx)$. As $f_{n}$ form the Hilbert basis, we have that $$\left\| f_{n}-f_{m} \right\| =2$$for all $n\neq m$. Therefore, $(f+\varepsilon f_{n})_{n}$ has no convergent subsequence in $B$ and this is a contradiction.
> 2. Because the closed balls form a local base.
---
