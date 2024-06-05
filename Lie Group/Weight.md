#Definition #RepresentationTheory #LieGroups 

> [!definition]
> Let $G$ be a [[Lie group]] and $\rho:G\to \text{GL}(V)$ be a [[Lie group representation]] to a $\mathbb{C}$-vector space $V$. A ***weight*** of $G$ in $V$ is a group homomorphism $\chi:G\to \mathbb{C}^\times$ s.t. 
> 1. $V_{\chi}:=\{ v\in V:\rho(g)v=\chi(g)v,\forall g\in G \}\neq \{ 0 \}$.

- **Related definition**: For weight $\chi$, $V_{\chi}$ is called the ***weight space*** of $\chi$ and any non-zero element in $V_{\chi}$ is called a ***weight vector.***
---
##### Properties
> [!lemma] Proposition 1
> Any weight $\chi$ is smooth.

> [!proof]-
> We first show that $\chi$ is continuous. Let $0\neq v\in V_{\chi}$ be a weight vector. Let $(g_{n})_{n}\subseteq G$ s.t. $g_{n}\to 0$. Then, $$\lim_{ n \to \infty } \left| \chi(g_{n}) \right| = \frac{1}{\left| v \right| }\lim_{ n \to \infty } \left| \rho(g_{n})v \right|=0 $$Hence, $\chi$ is continuous. Then, let $\Gamma:G\to \text{graph}(\chi),g\mapsto (g,\chi(g))$ be the graph map. One can see that $\Gamma$ is a homeomorphism with its inverse as restriction of the projection $G\times \mathbb{C}^\times\to G$. Therefore, $\text{graph}(\chi)$ is closed and by [[Lie Group|closed subgroup theorem]], $\text{graph}(\chi)$ is a Lie subgroup.
> 
> Further, $\Gamma ^{-1}$ is a projection, hence as a smooth homomorphism has constant rank. Therefore, $\Gamma$ is a diffeomorphism. For second smooth projection $q:\text{graph}(\chi)\to \mathbb{C}^\times$, we have: $$\chi=q\circ \Gamma$$
---
> [!lemma] Theorem 2 (Existence of Weights for Connected Solvable Lie Groups)
> Let $G$ be a connected solvable Lie group. Then, for any complex representation $\rho:G\to \text{GL}(V)$, 
> 1. there exists a weight $\chi$ of $G$ in $V$.