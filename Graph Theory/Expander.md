#Definition #GraphTheory 

> [!definition]
> Let $G=(V,E)$ be an [[Graph|undirected graph]]. For any $0<\phi\leq 1$, 
> 1. A [[Cut (Graph)|cut]] $(S, V\backslash S)$ is ***$\phi$-sparse*** if $\left| E(S, V \backslash S) \right|<\phi\min \left\{  \sum_{v\in S}^{}d(v), \sum_{v\in V \backslash S}^{}d(v)  \right\}$.
> 2. $G$ is a ***$\phi$-expander*** if $G$ contains no $\phi$-sparse cut.
---
##### Properties
---
##### Examples
> [!h] Example 1
> $K_{n}$ is a $\frac{1}{2}$-expander.

> [!proof]-
> Let $S\subseteq V$ with $\left| S \right|=k\leq n / 2$. Assume $(S,V\backslash S)$ is a $\frac{1}{2}$-sparse cut. Then, $$\frac{kn}{2}\leq|S||V \backslash S|=\left| E(S,V \backslash S) \right| < \frac{1}{2}(n-1)k$$which is a contradiction.
---
