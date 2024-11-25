#Definition #Algorithms 

> [!definition]
> Let $G=(V,E)$ be an [[graph|undirected graph]]. The ***sparsest cut*** problem is given as: $$S^{*}\in \underset{ S\subseteq V }{ \text{argmin} } \frac{\left| E(S,V \backslash S) \right| }{\left| S \right| \cdot \left| V \backslash S \right| }$$
---
##### Properties
> [!lemma] Theorem (LP)
> Consider the following LP: $$\begin{array}{rll} \min& \sum_{\{ u,v \}\in E}^{}d_{uv}\\\text{subject to}& d_{u,v}\geq 0,\quad d_{uv}=d_{vu}&\forall u,v\in V\\&d_{u,v}\leq d_{v,w}+d_{w,v}&\forall u,v,w\in V\\&\sum_{u,v}^{}d_{uv}=1\end{array}$$
> Let $d^{*}$ be the LP minimum. 

> [!proof]+
> 