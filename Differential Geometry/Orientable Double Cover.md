#Definition #DifferentialGeometry 

> [!definition]
> Let $M^n$ be a [[Topological Manifold|manifold]]. 
> 1. the ***orientable double cover*** is given by: $$\text{O}M:=\{ (x,\mu_{x}): x\in M,\mu_{x}\in H_{n}(M|x) \}$$where $\mu_{x}$ is a [[Local Homology|local orientation]]. The covering map is given by $p:\tilde{M}\to M,(x,\mu_{x})\mapsto x$.

^9fc8dd

- **Related Definition**: The orientable double cover is endowed with the following topology: For a chart $\varphi:\mathbb{R}^n\to U\subseteq M$, let $B:=\varphi(B_{<r}(0))\subseteq U$ be a ball chart. As $H_{n}(M|B)\cong H_{n}(M|y)\cong \mathbb{Z}$ for any $y\in B$ per [[Local Homology|Proposition 2]], we can choose a generator $\mu_{B}\in H_{n}(M|B)$ and define:$$\mathcal{W}(\mu_{B}):=\{ (x,L_{x}(\mu_{B})) \}_{x\in B}\subseteq \text{O}M$$Then, the base of the topology is defined as $\{ \mathcal{W}(\mu_{B}) \}_{B,\mu_{B}}$ ^6460ba
---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. the topology is well-defined.

> [!proof]+
> We have:
> 1. We need to show that $\{ \mathcal{W}(\mu_{B}) \}_{B,\mu_{B}}$ forms a base. Firstly, for any $(x,\mu_{x})\in \text{O}M$, let $B$ be a ball chart containing $x$. Then, by choosing $\mu_{B}:=L^{-1}_{x}(\mu_{x})$, we have that $(x,\mu_{x})\in\mathcal{W}(\mu_{B})$. 
