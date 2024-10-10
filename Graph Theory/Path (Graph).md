#Definition #GraphTheory 

> [!definition]
> Let $G=(V,E)$ be a [[graph]] and $s,t\in V$.
> 1. A ***$(s,t)$-path*** is a $(s,t)$-[[walk]] $W=(v_{1},\dots,v_{k})$ s.t. $v_{i}\neq v_{j}$ for all $i\neq j$.
> 2. A **cycle** is a walk $W=(v_{1},\dots,v_{k})$ where $v_{1}=v_{k}$ and $(v_{1},\dots,v_{k-1})$ is a path.
- **Related Notation**: For an edge $e\in E$ and a walk $W$, $e\in W$ if $e=(v_{i},v_{i+1})$ for some $i$. The ***length*** of $W$ is given by the number of edges in $W$.
- **Related Definition**: A graph $G$ is ***connected*** if for every $v,w\in G$, there exists a $(v,w)$-path.
- **Related Definition**: Two paths are ***independent*** if they do not share an inner node.
- **Related Definition**: For $s,t\in V$, the ***distance*** $d_{G}(s,t)$ is the length of the shortest $(s,t)$-path in $G$. If such path doesn't exist, $d_{G}(s,t)=\infty$.
- **Related Definition**: The dia
---
##### Properties
> [!lemma] Proposition 1
> For a finite graph $G$ with $\delta(G)\geq 2$,
> 1. $G$ has a path of length $\delta(G)$. 
> 2. $G$ has a cyclic of length at least $\delta(G)+1$.

> [!proof]+
> We have:
> 1. Let $x_{0}\dots x_{k}$ be the longest path in $G$. Then, all the neighbors of $x_{k}$ are on the path. Hence, $k\geq d(x_{k})\geq\delta(G)$.