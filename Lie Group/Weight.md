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
> [!lemma] Lemma 2
> Let $G$ be a connected Lie group and $\rho:G\to \text{GL}(V)$ a complex representation. For $H\unlhd G$ and a weight $\chi:H\to \mathbb{C}^\times$ w.r.t. $\rho|_{H}$, 
> 1. $V_{\chi}$ is an $G$-invariant subspace.

> [!proof]-
> Let $g\in G$, $h\in H$ and $v\in V_{\chi}$. Then,$$\rho(h)\rho(g)v=\rho(g)\rho(\underbrace{ g^{-1}hg }_{ \in H })v=\chi(g ^{-1}hg)\rho(g)v$$And $\chi(g^{-1}hg)\in \text{Spec}(\rho(h))$ for all $g\in G$. Therefore, $G\to \text{Spec}(\rho(h)),g\mapsto \chi(g ^{-1}hg)$ is a continuous function and as $G$ is connected, the image is connected. However, as $\text{Spec}(\rho(h))$ is a discrete set, the function is constant and $\chi(g^{-1}hg)=\chi(h)$ for all $g\in G$. Therefore, $$\rho(h)\rho(g)v=\chi(h)\rho(g)v$$and $\rho(g)v\in V_{\chi}$.
---
> [!lemma] Theorem 3 (Existence of Weights for Connected Solvable Lie Groups)
> Let $G$ be a connected solvable Lie group. Then, for any complex representation $\rho:G\to \text{GL}(V)$, 
> 1. there exists a weight $\chi$ of $G$ in $V$.

> [!proof]+
> We proceed with induction over $n:=\text{dim}(G)$. 
> 
> If $n=1$, then $\text{dim }\mathfrak{g}=1$. Hence, there exists $x\in \mathfrak{g}$ s.t. $\mathfrak{g}=\mathbb{R}x$. Let $0\neq v_{0}$ be an eigenvector of $d_{e}\rho(x)$, which exists as any complex matrix has an eigenvector. Then, $$d_{e}\rho(y)\mathbb{C}v$$