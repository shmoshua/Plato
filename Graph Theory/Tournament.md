#GraphTheory #Definition 

> [!definition]
> A ***tournament*** $T_{n}$ is a directed graph obtained by orienting the edges of the [[complete graph]] $K_{n}$. 
- **Related definition**: A tournament $T_{n}$ has a ***$S_{k}$-property*** if for all $S\subseteq V(T_{n})$ with $\left| S \right|= k$, there is a vertex in $T_{n}$ that dominates all vertices in $S$. 
---
##### Properties
> [!lemma] Theorem 1 (Erdös)
> If $n\geq 3k^22^k$, then there exists a tournament $T_{n}$ with the $S_{k}$-property.

> [!proof]+
> Consider $K_{n}$ and we will orient the edges uniformly independently at random with probability $\frac{1}{2}$. Then, let $S$ be a set of vertices with size $k$. For a fixed vertex $v\notin S$, $P(v\text{ dominates }S)=2^{-k}$. Then, for a fixed $S$, the probability that there is no vertex that dominates all vertices in $S$ is given by $(1-2^{-k})^{n-k}$. 
> 
> Since there are $n \choose k$ such sets $S$, $$P(\exists S\text{ not dominated}) \leq {n \choose k}(1-2^{-k})^{n-k}\leq n^ke^{-(n-k)/2^k}=e^{k\ln n-(n-k) / 2^k}<1$$