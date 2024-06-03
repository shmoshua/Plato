#Definition #DifferentialGeometry #LieGroups 

> [!definition]
> Let $M$ be a [[smooth manifold]]. For $1\leq n\leq m$,
> 1.  a ***$n$-dimensional distribution*** $\mathcal{D}$ on $M$ is a family of $n$-dimensional spaces $(\mathcal{D}_{p})_{p\in M}$ s.t. $\mathcal{D}_{p}\subseteq \text{T}_{p}M$ is a vector subspace.
> 2. A distribution $\mathcal{D}$ is ***smooth*** if for each $p\in M$, there exists a neighborhood $U\ni p$ s.t. there exist $n$ [[Vector Field|smooth vector fields]] $X_{1},\dots,X_{n}\in \Gamma(\text{T}M)$ on $U$ that give a basis of $\mathcal{D}_{q}$ for all $q\in U$.
- **Related definition**: $X\in \Gamma(\text{T}M)$ ***belongs to*** $\mathcal{D}$ if $X_{p}\in \mathcal{D}_{p}$ for all $p\in M$, denoted as $X\in \mathcal{D}$.
- **Related definition**: For a smooth distribution $\mathcal{D}$, an [[Submanifold|immersed submanifold]] $\varphi(N)$ is an ***integral submanifold*** of $\mathcal{D}$ if $d_{p}\varphi(\text{T}_{p}N)=\mathcal{D}_{\varphi(p)}$ for all $p\in M$.
- **Related definition**: A smooth distribution $\mathcal{D}$ is called 
	1. ***involutive*** if for any local basis $X_{1},\dots,X_{n}$ on $U\ni p$, $[X_{i},X_{j}]_{p}\in \mathcal{D}_{p}$ for all $i,j\in [n]$.
	2. ***completely integrable*** if it admits an integral submanifold through each point.
---
##### Examples
