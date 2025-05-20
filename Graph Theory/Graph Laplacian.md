#Definition #GraphTheory #AGAO 

> [!definition]
> Let $G=(V,E)$ be an undirected [[graph]] with weights $w$.
> 1. the ***Laplacian*** of $G$ is defined as $$L:=BWB^\top$$ where $B$ is the [[Graph Matrices|edge-vertex incidence matrix]] and $W:= \text{diag}(w)$ is the weight matrix.

^0a9fe6

- **Related definition**: $\lambda_{i}(G):= \lambda_{i}(L)$. ^ebe958
---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. $L=D-A$.
> 2. for any $x\in \mathbb{R}^V$, $x^\top Lx=\sum_{uv\in E}^{}w_{uv}(x_{u}-x_{v})^{2}$.
> 3. $1$ is an eigenvector of $L$ with eigenvalue $0$.

^0b2b13

> [!proof]-
> We have that:
> 1. Let $v,w\in V$. Then: $$(BR^{-1}B)_{vw}=\sum_{e,e'\in E}^{}B_{ve}R^{-1}_{ee' }B_{we'}=\sum_{e\in E}^{}\frac{B_{ve}B_{we}}{r(e)}$$
>    1. if $v\neq w$, then: $$(BR^{-1}B)_{vw}=-\frac{\mathbb{1}_{(v,w)\in E}}{r_{vw}}=0-\frac{\mathbb{1}_{(v,w)\in E}}{r_{vw}}=D_{vw}-A_{vw}$$
>    2. if $v=w$, then: $$(BR^{-1}B)_{vv}=\sum_{e\in E}^{}\frac{B_{ve}^{2}}{r(e)}=\sum_{u:(u,v)\in E} \frac{1}{r(u,v)}=w(v)=D_{vv}-A_{vv}$$
> 2. Notice that: $$x^\top Lx=x^\top B WB^\top x = \sum_{uv\in E}^{}w_{uv}(B^\top x)_{uv}^{2}=\sum_{uv\in E}^{}w_{uv} (x_{u}-x_{v})^{2}$$
> 3. Notice that: $$L1= BWB^\top 1= 0$$

^c29c29

---
> [!lemma] Proposition 2
> For any unit weight graph, 
> 1. $\lambda_{n}(G)\leq 2 \Delta(G)$.

> [!proof]+
> We have that: 
> 1. From Proposition 2, for unit weights, $L=D-A\geq 0$. Now, we have that: $$x^\top (D+A)x=$$
---
##### Examples
> [!h] Example 1 (Complete Graph)
> Let $G=K_{n}$ be the unweighted complete graph. Then, 
> 1. $D=(n-1)I$.
> 2. $A=1 1^\top - I$.
> 3. $L=nI-11^\top$.
> 4. $\lambda_{2}(K_{n})=\lambda_{3}(K_{n})=\dots=\lambda_{n}(K_{n})= n$

> [!proof]-
> First 3 are trivial. For the last, we have that for any $y\  \bot\  1$, $$y^\top L y=n\|y\|^{2}_{2}-(1^\top y)^{2}=n\|y\|^{2}_{2}$$Therefore, by Courant-Fischer, we have our statement.

---
> [!h] Example 2 (Path Graph)
> Let $G=P_{n}$ be the unweighted path graph. Then, 
> 1. $\lambda_{2}(P_{n})\leq \frac{12}{n^{2}}$
> 2. $1\leq \lambda_{n}(P_{n})\leq$

^da60b7

> [!proof]+
> We have that:
> 1. Consider $x_{i}:=(n+1)-2i$. Then, $x\bot 1$ and by Courant-Fischer, $$\lambda_{2}(P_{n})\leq \frac{x^\top Lx}{x^\top x}=\frac{\sum_{i\in[n-1]}(x_{i}-x_{i+1})^{2}}{\sum_{i\in[n]}^{}x_{i}^{2}}=\frac{4(n-1)}{\sum_{i\in[n]}(n+1-2i)^{2}}\leq \frac{12}{n(n+1)}\leq \frac{12}{n^{2}}$$
> 2. Consider $x\in\mathbb{R}^V$ where $x_{1}=-1$, $x_{n}=1$ and 0 everywhere else. Then, $$\lambda_{n}(P_{n})\geq \frac{x^\top Lx}{x^\top x}=\frac{2}{2}=1$$

^31dc20

