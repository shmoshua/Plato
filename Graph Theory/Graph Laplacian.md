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

> [!proof]-
> We have that: 
> 2. From Proposition 2, for unit weights, $L=D-A\geq 0$. Now, we have that: $$x^\top (D+A)x=x^\top Ax=\sum_{u}d(u)x_{u}^{2}+\sum_{uv\in E}^{}2x_{u}x_{v}=\sum_{uv\in E}(x_{u}+x_{v})^{2}\geq 0$$Hence, $D+A\geq 0$ and $-A\leq D$. Therefore, it follows that $L\leq 2D$ and by [[Positive Definite|Proposition 3.5]] $$\lambda_{n}(G)\leq 2\lambda_{n}(D)=2\Delta(G)$$
- **Remark**: This is tight on a single edge with $\lambda_{2}(G)=2$. 
---
> [!lemma] Proposition 3 (Loewner Order for Graphs)
> Let $G$ be a unit weight graph and $H\leq G$ a unit weight subgraph. Then, 
> 1. $H\leq G$. 

> [!proof]-
> We have that: $$x^\top L_{G}x = \sum_{uv\in E_{G}}^{}(x_{u}-x_{v})^{2}\geq  \sum_{uv\in E_{H}}^{}(x_{u}-x_{v})^{2}=x^\top L_{H}x$$

---
> [!lemma] Theorem 4 (The Path Inequality)
> Let $G_{i,j}$ be the graph on $[n]$ with a single edge $ij$. Then, 
> 1. $(n-1)P_{n}\geq G_{1,n}$

> [!proof]-
> We want to show that: $$(n-1)\sum_{i=1}^{n-1}(x_{i+1}-x_{i})^{2}\geq( x_{n}-x_{1})^{2}$$Let $\xi_{i}:= x_{i+1}-x_{i}$. Then, $$(x_{n}-x_{1})^{2}=\left( \sum_{i=1}^{n-1}\xi_{i} \right) ^{2}\leq (n-1)\sum_{i=1}^{n-1}\xi_{i}^{2}=(n-1)\sum_{i=1}^{n-1}(x_{i+1}-x_{i})^{2} $$
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
> 2. $1\leq \lambda_{n}(P_{n})\leq 4$

^da60b7

> [!proof]+
> We have that:
> 1. Consider $x_{i}:=(n+1)-2i$. Then, $x\bot 1$ and by Courant-Fischer, $$\lambda_{2}(P_{n})\leq \frac{x^\top Lx}{x^\top x}=\frac{\sum_{i\in[n-1]}(x_{i}-x_{i+1})^{2}}{\sum_{i\in[n]}^{}x_{i}^{2}}=\frac{4(n-1)}{\sum_{i\in[n]}(n+1-2i)^{2}}\leq \frac{12}{n(n+1)}\leq \frac{12}{n^{2}}$$For the lower bound, $$$$
> 2. Consider $x\in\mathbb{R}^V$ where $x_{1}=-1$, $x_{n}=1$ and 0 everywhere else. Then, $$\lambda_{n}(P_{n})\geq \frac{x^\top Lx}{x^\top x}=\frac{2}{2}=1$$The upper bound is given by Proposition 2.

^31dc20

