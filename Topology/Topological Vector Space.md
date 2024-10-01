#Definition #Topology 

> [!definition]
> A ***topological vector space*** is a $\mathbb{K}$-vector space $V$ endowed with a [[Topological Space|topology]] s.t. 
> 1. $\mathbb{K}\times V\to V,(\lambda,v)\mapsto\lambda v$ is continuous and
> 2. $V\times V\to V,(x,y)\mapsto x+y$ is continuous.
> 
- **Related definition**: For $\lambda\in \mathbb{K}$, we define:
  1. the ***multiplication map***: $M_{\lambda}:V\to V,v\mapsto \lambda v$
  2. the ***translation map***: $L_{v}:V\to V,w\mapsto v+w$
---
##### Properties
> [!lemma] Lemma 1
> For all $\lambda\neq 0$ and all $v\in V$, $M_{\lambda}$ and $L_{v}$ are [[Homeomorphism|homeomorphisms]]. 

> [!proof]-
> We know that $M_{\lambda}$ is continuous with a continuous inverse $M_{\lambda ^{-1}}$, and $L_{v}$ is continuous with a continuous inverse $L_{-v}$.
---
> [!lemma] Theorem 2 (Riesz)
> A Hausdorff TVS is locally compact if and only if it is finite dimensional.

> [!proof]-
> Let $X$ be a locally compact topological vector space. 
> https://www.math.uni-konstanz.de/~infusino/Lect8.pdf
---
