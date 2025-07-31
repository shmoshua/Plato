#Definition #GraphTheory 

> [!definition]
> Let $G=(V,E)$ be an undirected [[Graph|simple graph]].
> 1. $G$ is ***$k$-degenerate*** if every subgraph of $G$ has a vertex of degree $\leq k$.

^3c0f00
- **Remark**: If $G$ is $k$-degenerate, $G$ is $k'$-degenerate for every $k\leq k'$.
- **Related definition**: The ***degeneracy number*** is given by: $$\text{dg}(G):=\min \{ k\geq 1:G \text{ is }k\text{-degeneate} \}$$
---
##### Properties
> [!lemma] Proposition 1
> Let $G$ be a graph. TFAE:
> 1. $G$ is $k$-degenerate. 
> 2. there exists an ordering $v_{1},..,v_{n}$ of the vertices s.t. $\left| N(v_{i})\cap\{v_{j} \}_{j<i} \right|\leq k$ for all $i$.

> [!proof]-
> We have that:
> 1. (1=>2): Let $G$ be $k$-degenerate. We show by induction over $n$. 
> 	- If $n=1$, then the statement is trivial.
> 	- For $n\geq 2$, as $G$ is $k$-degenerate there is a vertex $v_{n}$ with $d_{G}(v_{n})\leq k$. Let $G':= G \backslash v_{n}$. Then, $G'$ is also $k$-degenerate by definition and by induction hypothesis there is an ordering $v_{1},\dots,v_{n-1}$. By adding $v_{n}$, we have the statement.
> 2. (2=>1): Let $v_{1},\dots,v_{n}$ be such ordering. For any subgraph $H\leq G$, let $$j= \max\{ i\in[n] :v_{i}\in V(H)\}$$Then, $v_{j}$ has $\leq k$ neighbors in $H$. This shows that $G$ is $k$-degenerate.

---
> [!lemma] Proposition 2
> Let $G$ be a graph. We have that:
> 1. $\delta(G)\leq \text{dg}(G)\leq \Delta(G)$.

> [!proof]-
> We have that:
> 1. For any subgraph $H$ and $v\in H$, $d_{H}(v)\leq d_{G}(v)\leq \Delta(G)$. Hence, $$\text{dg}(G)\leq \Delta(G)$$Conversely, $G$ doesn't have a vertex of degree less than $\delta(G)$. Hence, $\delta(G)\leq \text{dg}(G)$.