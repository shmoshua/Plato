#Definition #AGAO 

> [!definition]
> Let $G=(V,E)$ be an undirected [[graph]].
> 1. The ***vertex-edge incidence matrix*** $B\in\mathbb{R}^{V,E}$: $$B(v,e):=\begin{cases}1&\text{if }e=(u,v)\\-1&\text{if }e=(v,u) \\0&\text{otherwise}\end{cases}$$
> 2. The ***degree matrix*** $D\in \mathbb{R}^{V,V}$ is given by $D:= \text{diag}(d)$ where $d(v):=\sum_{u\in N(v)}^{}w(u,v)$
> 3. The ***weighted adjacency matrix*** $A\in \mathbb{R}^{V,V}$ is given as: $$A(u,v):= w(u,v)\cdot \mathbb{1}_{uv\in E}$$

^41f1d4

- **Remark**: As $G$ is undirected, $A=A^\top$. ^f42544

---
