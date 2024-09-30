#Definition #GraphTheory 

> [!definition]
> A ***hypergraph*** $G=(V,E)$ is a set of vertices $V$ with a set of edges $E$ where every edge is a subset of $V$. 

- **Related definition**: A hypergraph $(V,E)$ is ***$k$-uniform*** if $\left| e \right|=k$ for all $e\in E$.
- **Remark**: A standard graph is a $2$-uniform hypergraph.
- **Related definition**: A $k$-coloring of the vertices of a hypergraph $G$ is called ***proper***, if no edge in $G$ is monochromatic.
- **Related definition**: $m(k)$ is the smallest integer $m$ s.t. there exists a $k$-uniform hypergraph with $m$ edges for which there is no proper 2-coloring.
---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. $m(2)=3$
> 2. for $k\geq 2$, $2$-colorability is NP-complete.
---
> [!lemma] Proposition 2 (Erdös)
> $2^{k-1}< m(k)\leq ck^{2}2^k$ for some large constant $c>0$.

> [!proof]+
> We have that:
> 1. (Lower bound) Let $m\leq 2^{k-1}$ and $G=(V,E)$ be a $k$-uniform hypergraph with $m$ edges. Let us color its vertices uniformly at random with 2 colors. For an edge $e\in E$, let $A_{e}$ denote the event that $e$ is monochromatic. Then, we have that $\mathbb{P}(A_{e})=2\cdot 2^{-k}$. Therefore, $$\mathbb{P}(\exists \text{monochromatic edge})=\mathbb{P}\left( \bigcup_{e\in E}^{} A_{e}\right)< m\cdot 2\cdot 2^{-k} =\frac{m}{2^{k-1}}$$where the last inequality is strict as there are events that are not disjoint. 