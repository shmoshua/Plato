#Definition #GraphTheory #Algorithms 

> [!definition]
> Let $G=(V,E)$ be an [[graph|undirected graph]]. For a [[Metric Space|metric]] $d$ on $V$ and a [[normed space|normed vector space]] $(W,\|\cdot\|)$, a ***metric embedding*** is a map $\phi:V\to W$ s.t. 
> 1. there exists $\alpha\leq 1$ s.t. for all $u,v\in V$:  $\alpha\cdot d(u,v)\leq \left\| \phi(u)-\phi(v) \right\|\leq d(u,v)$

---
##### Properties
> [!lemma] Theorem 1 (Existence of l1-metric Embedding)
> For any pseudo-metric $d$ on $V$, consider:
> ```pseudo
> \begin{algorithm} \caption{$L_{1}$-Embedding$(d,G)$}
> \begin{algorithmic}
> \For{$i=1,\dots,L:=\log n$}
> \For{$h=1,\dots,H:=1000\log n$}
> \State $S_{i,h}\gets$ Subset of $V$ where each vertex is sampled independently with $\mathbb{P}(v\in S_{i,h})=2^{-i}$
> \State $\phi_{(i-1)H+h}(u)\gets d(u,S_{i,h}) / LH$ for all $u\in V$
>\EndFor\EndFor \Return $\phi:V\to \mathbb{R}^{LH}$
> \end{algorithmic}
> \end{algorithm}
> ```
> Then, it holds that:
> 1. $\frac{d(u,v)}{\Theta(\log |V|)}\leq \|\phi(u)-\phi(v)\|_{1}\leq d(u,v)$

> [!proof]+
> Let $\phi_{i,h}:=\phi_{(i-1)H+h}$. Then, $$\left\| \phi(u)-\phi(v) \right\| =\sum_{i=1}^{L}\sum_{h=1}^{H}\left| \phi_{i,h}(u)-\phi_{i,h}(v) \right|=\sum_{i=1}^{L}\sum_{h=1}^{H}\frac{\left| \phi_{i,h}(u)-\phi_{i,h}(v) \right|}{LH} $$
---
