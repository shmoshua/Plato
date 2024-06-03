#Definition #DifferentialGeometry #LieGroups 

> [!definition]
> Let $M$ be a [[smooth manifold]]. For $1\leq n\leq m$,
> 1.  a ***$n$-dimensional distribution*** $\mathcal{D}$ on $M$ is a family of $n$-dimensional spaces $(\mathcal{D}_{p})_{p\in M}$ s.t. $\mathcal{D}_{p}\subseteq \text{T}_{p}M$ is a vector subspace.
> 2. A distribution $\mathcal{D}$ is ***smooth*** if for each $p\in M$, there exists a neighborhood $U\ni p$ s.t. there exist $n$ [[Vector Field|smooth vector fields]] $X_{1},\dots,X_{n}\in \Gamma(\text{T}M)$ on $U$ that give a basis of $\mathcal{D}_{q}$ for all $q\in U$.
- **Remark**: A smooth distribution is a smooth subbundle of $\text{T}M$.
- **Related definition**: $X\in \Gamma(\text{T}M)$ ***belongs to*** $\mathcal{D}$ if $X_{p}\in \mathcal{D}_{p}$ for all $p\in M$, denoted as $X\in \mathcal{D}$.
- **Related definition**: For a smooth distribution $\mathcal{D}$, a non-empty [[Submanifold|immersed submanifold]] $\varphi(N)$ is an ***integral submanifold*** of $\mathcal{D}$ if $d_{p}\varphi(\text{T}_{p}N)=\mathcal{D}_{\varphi(p)}$ for all $p\in M$.
- **Related definition**: A smooth distribution $\mathcal{D}$ is called 
	1. ***involutive*** if for any local basis $X_{1},\dots,X_{n}$ on $U\ni p$, $[X_{i},X_{j}]_{p}\in \mathcal{D}_{p}$ for all $i,j\in [n]$.
	2. ***completely integrable*** if it admits an integral submanifold through each point.
- **Related definition**: A ***maximal integral manifold*** $(N,\varphi)$ of a distribution $\mathcal{D}$ on a manifold $M$ is a connected integral submanifold of $\mathcal{D}$ whose image in $M$ is not a proper subset of any other connected integral manifold of $\mathcal{D}$.
---
##### Properties
> [!lemma] Theorem 1 (Frobenius)
> A smooth distribution $\mathcal{D}$ is completely integrable if and only if it is involutive.
---
> [!lemma] Theorem 2
> Given an involutive distribution $\mathcal{D}$ on $M$ and $p\in M$, there exists a unique maximal integral submanifold through $p$. 
---
##### Examples
> [!h] Example 1
> Let $M=\mathbb{R}^{n+k}$ and $X_{i}:=\frac{ \partial  }{ \partial x^i }$ for $i=1,\dots,n$. Then, 
> 1. $\mathcal{D}:=\text{span}\{ X_{1},\dots,X_{n} \}$ defines a smooth $n$-dimensional distribution.
> 2. $\mathcal{D}$ is involutive.
---
> [!h] Example 2
> Let $M=\mathbb{R}^3$ and $\mathcal{D}:=\text{span}\left\{  \frac{ \partial  }{ \partial x },\frac{ \partial  }{ \partial y }+x\frac{ \partial  }{ \partial z }  \right\}$. Then, 
> 1. $\mathcal{D}$ is not involutive.

 > [!proof]-
 > We have that: $$[\partial_{x},\partial_{y}+x\partial_{z}]=[\partial_{x},\partial_{y}]+[\partial _{x},x\partial_{z}]=0+\partial_{x}(x\partial_z)-x\partial_{z}\partial_{x}=\partial_{z}+x\partial_{x}\partial_{z}-x\partial_{z}\partial_{x}=\partial_{z}$$which is not in the span.
 ---
 > [!h] Example 3
 > Let $X$ be a non-vanishing complete smooth vector field of $M$. Then, 
 > 1. $\mathcal{D}:=\text{span}(X)$ is a smooth $1$-dimensional distribution. 
 > 2. Let $\gamma$ be an [[integral curve]] of $X$. Then, $\gamma(\mathbb{R})$ is an integral manifold of $\mathcal{D}$.

> [!proof]-
> We have that 1 is obvious. For 2, we have that $d_{t}\gamma(s)=\gamma'(t)\cdot s=X_{\gamma(t)}\cdot s$. Therefore, $\gamma$ is an immersion and $\gamma$ is injective. Further, $$d_{t}\gamma(\mathbb{R})=X_{\gamma(t)}\cdot \mathbb{R}=\mathcal{D}_{\gamma(t)}$$
---

