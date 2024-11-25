#Definition #GraphTheory #Algorithms 

> [!definition]
> Let $G=(V,E)$ be an [[graph|undirected graph]]. For a [[Metric Space|metric]] $d$ on $V$ and a [[normed space|normed vector space]] $(W,\|\cdot\|)$, a ***metric embedding*** is a map $\phi:V\to W$ s.t. 
> 1. there exists $\alpha\leq 1$ s.t. for all $u,v\in V$:  $\alpha\cdot d(u,v)\leq \left\| \phi(u)-\phi(v) \right\|\leq d(u,v)$

---
##### Properties
> [!lemma] Theorem 1 (Existence of l1-metric Embedding)
> For any metric $d$ on $V$, there exists $\phi:V\to \mathbb{R}^k$ for $k\in \text{O}(\log^2|V|)$ s.t. 
> 1. $\frac{d(u,v)}{\log |V|}\leq \|\phi(u)-\phi(v)\|_{1}\leq d(u,v)$
---
