#Definition #GraphTheory 

> [!definition]
> Let $G=(V,E)$ be a [[graph]] and $s,t\in V$.
> 1. A ***$(s,t)$-path*** is a $(s,t)$-[[walk]] $W=(v_{1},\dots,v_{k})$ s.t. $v_{i}\neq v_{j}$ for all $i\neq j$.
> 2. A **cycle** is a walk $W=(v_{1},\dots,v_{k})$ where $v_{1}=v_{k}$ and $(v_{1},\dots,v_{k-1})$ is a path.
- **Related Notation**: For an edge $e\in E$ and a walk $W$, $e\in W$ if $e=(v_{i},v_{i+1})$ for some $i$. The ***length*** of $W$ is given by the number of edges in $W$.
- **Related Definition**: A graph $G$ is ***connected*** if for every $v,w\in G$, there exists a $(v,w)$-path.
---
