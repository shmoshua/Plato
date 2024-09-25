#Definition #GraphTheory 

> [!definition]
> For a [[graph]] $G$, the ***girth*** of $G$, denoted by $g(G)$, is defined as the shortest length of a cycle in $G$

^803604

---
##### Properties
> [!lemma] Theorem 1 (Erdös)
> For any $k,\ell$, there exists a graph $G$ s.t. $\chi(G)>k$ and $g(G)>\ell$.

> [!proof]+
> Let $G$ be a random graph on $n$ vertices where between two vertices $x,y$ there exists an edge with a probability $p=n^{-1+1/(\ell+1)}$ independently.
> 1. **Claim 1: with probability $\geq2/3$ the number of cycles of length $\leq \ell$ is $\leq \frac{n}{3}$**
>    Let $X$ be the number of cycles of length $\ell$. Then, $$\mathbb{E}[X]=\sum_{i=3}^{\ell} {n \choose i}p^i\leq\sum_{i=3}^{\ell} (np)^i=\sum_{i=3}^{\ell}n^{i/(\ell+1)}$$
> 2. **Claim 2: with probability $\geq \frac{2}{3}$ we have $\alpha(G)\leq \frac{n}{3}$**