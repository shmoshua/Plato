#Definition #DifferentialGeometry 

> [!definition]
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]] and $f:M\to N$ [[Differentiable Function|differentiable]] at $p\in M$. For $(U,\varphi)$ at $p$ and $(W,\psi)$ at $f(p)$, the ***rank*** of $f$ at $p$ is the rank of $d_{\varphi(p)}(\psi  f\varphi ^{-1}):\mathbb{R}^m\to \mathbb{R}^n$.
- **Related definition**: A value $y\in N$ is ***regular*** if $f$ has rank $n$ at every point in $f^{-1}(y)$.
---
##### Properties
![[Smooth Function#^374b28]]
![[Smooth Function#^c35ca3|p]]
![[Smooth Function#^a2f39f|p]]

---
> [!lemma] Corollary 1 
> Let $M,N$ be smooth manifolds and $f\in C^\infty(M,N)$. If $M$ is connected, then TFAE:
> 1. for each $p\in M$, there exists charts $(U,\varphi)$ and $(V,\psi)$ at $p$ and $f(p)$ s.t. the coordinate representation $\tilde{f}:=\psi f\varphi ^{-1}$ is linear.
> 2. $f$ has constant rank.

> [!proof]-
> We have:
> 1. (1=>2): since every linear map has constant rank, it follows that the rank of $f$ is constant in a neighborhood of each point, and thus by connectedness it is constant on all of $M$.
> 2. (2=>1): Corollary of Theorem 4.
---
> [!lemma] Theorem 2 (Global Rank Theorem)
> Let $M,N$ be smooth manifolds and $f\in C^\infty(M,N)$ has constant rank. 
> 1. if $f$ is surjective, it is a submersion.
> 2. if $f$ is injective, it is an [[Differential|immersion]].
> 3. if $f$ is bijective, it is a [[diffeomorphism]].