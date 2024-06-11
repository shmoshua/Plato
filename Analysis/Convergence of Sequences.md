#Definition #Analysis  #LST
> [!definition]
> Let $X$ be a [[topological space]]. A sequence $(x_{n})_{n}\subseteq X$ ***converges to $x\in X$*** if for any (open) neighborhood $U$ of $x$, there exists $N\geq 0$ s.t. $x_{n}\in U$ for all $n\geq N$. Then, Then, $x$ is a ***limit*** of our sequence and is written as $x=\lim_{ n \to \infty }x_{n}$.
- **Remark**: It suffices to check for $U$ in a [[Local Base of Topology|fundamental system of neighborhoods]].
- **Remark**: If $X$ is a [[metric space]], this is equivalent to: for all $\varepsilon>0$, there exists $N\geq 0$ s.t. $d(x_{n},x)<\varepsilon$ for all $n\geq N$. Furthermore, $x=\lim_{ n \to \infty }x_{n}$ if and only if $\lim_{ n \to \infty }d(x_{n},x)=0$.

---
##### Properties
> [!lemma] Proposition 1
> In a Hausdorff space $X$,  a sequence $(x_{n})_{n}$ can only have at most one limit.

> [!proof]-
> Suppose $x_{n}\to a$ and $x_{n}\to b$ where $a\neq b$. Let $U,V$ be the disjoint neighborhoods of $a$ and $b$. Then, there exists $N,M\in \mathbb{N}$ s.t. 
> 1. $x_{n}\in U$ for all $n\geq N$
> 2. $x_{m}\in V$ for all $m\in M$
> 
> Therefore, $U\cap V\neq \varnothing$.
---
##### Examples
> [!h] Example 1
> $X=\mathbb{R}$ with the cofinite topology doesn't have unique limits.