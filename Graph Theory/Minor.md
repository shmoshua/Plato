#Definition #GraphTheory 

> [!definition]
> Let $G$ be a [[graph]].
> 1. A graph $H$ is a ***minor*** of $G$ if it can be obtained from $G$ by deleting vertices and edges, and contracting edges. 

---
##### Properties
> [!lemma] Theorem 1 (Mader)
> Let $G$ be a graph.
> 1. if $d(G)\geq 2^{t-2}$ then $G$ admits $K_{t}$ as a minor. 

> [!proof]
> We prove it via induction on $t+n$. 
> 1. If $t=2$, then $d(G)\geq 1$. This means that $e(G)\geq 1$ and $K_{2}$ is an edge. 
> 2. In general, if $d(G)\geq 2^{t-2}$, i.e. $e(G)\geq 2^{t-3}n$. Let $v\in V(G)$.
> 	1. if there exists $u\in N(v)$ s.t. $\left| N(u)\cap N(v) \right|\leq 2^{t-3}-1$, then contract $e:=uv$. Then, $\left| G / e \right|=\left| G \right|-1$ and $e(G) - e(G / e)\leq (2^{t-3}-1)+1=2^{t-3}$. Therefore, $$d(G / e)=\frac{2e(G / e)}{n-1}\geq \frac{2(e(G)-2^{t-3})}{n-1}\geq 2^{t-2}$$However as $\left| G / e \right|=n-1$, we have that $G / e$ admits a $K_{t}$ as a minor so $G$ also has one. 
> 	2. if for all $u\in N(v)$, $\left| N(u)\cap N(v) \right|\geq 2^{t-3}$, then consider $G':=G[N(v)]$. We have that: $$d(G')$$