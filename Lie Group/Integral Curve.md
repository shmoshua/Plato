#Definition #LieGroups 

> [!definition]
> Let $M$ be a [[smooth manifold]]. For a [[vector field]] $X$ an ***integral curve*** on $X$ is a smooth map $\gamma:(a,b)\to M$ with: $$\gamma'(t)=X_{\gamma(t)},\quad \forall t\in I$$
---
##### Properties
> [!lemma] Theorem 1 (Existence and Uniqueness of solutions of ODEs)
> Let $X\in \Gamma(\text{T}M)$. For every $p\in M$, there exists an open interval $I_{p}\subseteq \mathbb{R}$ ($(-\infty,b),(a,\infty)$ possible) and a smooth curve $\gamma_{p}:I_{p}\to M$ s.t. 
> 1. $0\in I_{p}$ with $\gamma_{p}(0)=p$.
> 2. $\gamma_{p}$ is an integral curve on $X$.
> 3. if $\mu:J\to M$ satisfies 1 and 2, $J\subseteq I_{p}$ and $\mu|_{J}=\gamma_{p}|_{J}$.
- **Related definition**: $X$ is called ***complete*** if $I_{p}=\mathbb{R}$ for all $p\in M$.
---
##### Examples
> [!h] Example 1 (Left-Invariant Vector Fields)
> Let $G$ be a [[Lie group]]. Then, 
> 1. if $X\in \Gamma(\text{T}M)$ is [[Vector Field|$G$-invariant]], $X$ is complete.
> 2. For every $v\in \mathfrak{g}=\text{T}_{e}G$, let $v^L\in \Gamma(\text{T}M)$ be the corresponding $G$-invariant vector field given as: $$(v^L)_{g}=d_{e}L_{g}(v)$$ (cf. [[Lie Algebra|Proposition 1]]) Let $\gamma_{v}:\mathbb{R}\to G$ be the integral curve with $\gamma_{v}(0)=e$. Then, $\gamma_{v}$ is a smooth group homomorphism.

> [!proof]+
> 