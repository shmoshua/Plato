#Definition #Topology 

> [!definition]
> A [[topological space]] $X$ is ***locally connected***, if every $x\in X$ has a [[fundamental system]] of [[Connected Space|connected]] neighborhoods.
---
##### Properties
> [!lemma] Proposition 1
> Let $X$ be a topological space. The following are equivalent:
> 1. $X$ is locally connected.
> 2. for all $U\subseteq X$ open, all $x\in U$, the connected component of $x$ in $U$ is open.

> [!proof]-
> Let $U\subseteq X$ be open and $x\in U$. Let $V$ be a connected component of $x$ in $U$. Let $W$ be the connected neighborhood of $x$ in $U$. Then, $W\subseteq V$ by the definition of a connected component. Therefore, $V$ is open.
> 
> Conversely, let $x\in X$ and $U$ is an open neighborhood of $x$. Since the connected component of $x$ in $U$ is open, it is an open neighborhood of $x$ contained in $U$.
- **Remark**: If $X$ is locally connected, the connected components of $X$ are open and closed.

---
##### Examples

> [!h] Example 1
> We have: 
> 1. Any discrete space $X$ is locally connected.
> 2. $\mathbb{R}^n$ is locally connected.
> 3. Any topological manifold is locally connected.
---
> [!h] Example 2
>  $L^2([0,1])$ is locally connected.