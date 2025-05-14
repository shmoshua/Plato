#Definition #GraphTheory #AGAO 

> [!definition]
> Let $G=(V,E)$ be an undirected [[graph]] with weights $w$.
> 1. the ***Laplacian*** of $G$ is defined as $$L:=BWB^\top$$ where $B$ is the [[Graph Matrices|edge-vertex incidence matrix]] and $W:= \text{diag}(w)$ is the weight matrix.

---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. $L=D-A$.
> 2. for any $x\in \mathbb{R}^V$, $x^\top Lx=\sum_{uv\in E}^{}w_{uv}(x_{u}-x_{v})^{2}$.

> [!proof]-
> We have that:
> 1. Let $v,w\in V$. Then: $$(BR^{-1}B)_{vw}=\sum_{e,e'\in E}^{}B_{ve}R^{-1}_{ee' }B_{we'}=\sum_{e\in E}^{}\frac{B_{ve}B_{we}}{r(e)}$$
>    1. if $v\neq w$, then: $$(BR^{-1}B)_{vw}=-\frac{\mathbb{1}_{(v,w)\in E}}{r_{vw}}=0-\frac{\mathbb{1}_{(v,w)\in E}}{r_{vw}}=D_{vw}-A_{vw}$$
>    2. if $v=w$, then: $$(BR^{-1}B)_{vv}=\sum_{e\in E}^{}\frac{B_{ve}^{2}}{r(e)}=\sum_{u:(u,v)\in E} \frac{1}{r(u,v)}=w(v)=D_{vv}-A_{vv}$$
> 2. Notice that: $$x^\top Lx=x^\top B WB^\top x = \sum_{uv\in E}^{}w_{uv}(B^\top x)_{uv}^{2}=\sum_{uv\in E}^{}w_{uv} (x_{u}-x_{v})^{2}$$